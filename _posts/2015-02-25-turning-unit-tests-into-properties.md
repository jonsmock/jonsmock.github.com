---
layout:     post
title:      Turning unit tests into properties
date:       2015-02-25 15:15:00
summary:    Handy tips for getting over the property-based test learning curve.
categories: blog
---

Here's a tip for getting over the property-based testing "writer's block":
write a unit test and turn it *into* a property.

## An Example

Let's look at an example unit test you might write in the bowling kata, using
Clojure, clojure.test, and test.check. After your scoring function can total
up all the pins knocked down, you're likely to write a test like this:

```
(testing "Spares are worth 10 points"
  (is (= 10
         (score "1/000000000000000000"))))
```

We hardcoded the constant 1 here, but the fact that we knocked down *1* pin is
completely incidental to this example. What we're actually trying to convey is
that a spare means the rest of the 10 pins were knocked down.

Let's rewrite this as a property, step by step. First, we simply wrap the unit
test in our property testing framework. This basically accomplishes nothing
other than to run the unit test over and over (in this case, 100 times).

```
(defspec t-wrap-normal-test-up-as-property 100
  (for-all []
           (= 10
              (score "1/000000000000000000"))))
```

Notice we don't have anything in our for-all bindings. Our next step is to pull
out the specific inputs and replace them with generators. Sometimes this will
force us to make our assertion more general, as we will soon see.

```
(defspec t-extract-the-moving-parts 100
  (for-all [first-throw (gen/choose 0 9)]
           (= 10
              (score (str first-throw "/" "000000000000000000")))))
```

By extracting first-throw as a generator, our test will try lots of different
games and check they all return a score of 10! Congratulations, you wrote a
property! Notice this test captures what we said earlier, that any roll from 0
to 9 followed by a spare is worth 10 points.

Once you've gotten to this point, you'll probably have lots of ideas on how to
expand your property or write new ones. Let's change our property to also
include the fact that spares count the immediate next roll as part of the
frame's score:

```
(defspec t-expand-with-more-ideas 100
  (for-all [first-throw (gen/choose 0 9)
            throw-after (gen/choose 0 9)]
           (= (+ 10 throw-after throw-after)
              (score (str first-ball "/" throw-after "00000000000000000")))))
```

We're getting a lot of mileage out of one simple property, and we're getting
a more complete description of what a spare actually means.

Now you may ask if we can include strikes in our throw-after generator. Maybe!
Should this be part of the property or a corner-case unit test? There are tons
of deep testing questions here, but hopefully you're starting to get over the
initial learning curve.

Try the kata and see for yourself! Here's an interesting idea for exploration:
what happens when you replace a space with a strike? Can you say anything about
how the two scores relate? Try to write it as a property.

## Other Notes and Tips

When originally experimenting with this at work, I found a single unit test that
was conflating two properties. I didn't immediately recognize this due to all
the incidental setup details. As I replaced inputs with generators and
generalized the assertion, I found myself writing an `and`, which ultimately
could be separated into two properties. Not only did this result in less test
code but far more readable code.

All the usual unit testing caveats apply to property testing:

1. Pure code is easier to test than stateful code
2. More collaborators means more pain (listen to the pain!)
3. Removing things like db access will make things easier and faster

As you write more properties, you'll spend a lot more time writing generators
than you would writing single unit test's inputs. This is ok! Writing generators
will force you to ask problem domain questions, which only contributes to your
understanding of the problem. And, generators will actually be reusable across
properties, which isn't normally true for unit test inputs. For instance, a
bowling game generator could be used for several properties.

Reid Draper outlines three styles of property tests in [this
talk](https://www.youtube.com/watch?v=JMhNINPo__g). They're worth
repeating here:

1. Roundtrip
2. Trusted Implementation
3. Input/Output Relation

Roundtrip is when you have a way to transform some data and reverse the same
transformation. For instance, if we wrote a JSON parser and a JSON serializer,
we could write the following property:

```
(defspec t-roundtrip-json 100
  (for-all [data json-data-gen]
           (= data
              (parse (serialize data)))))
```

When we have a trusted implementation, we can test our version against the
trusted one. For instance, we could check our score function result against one
that we already knew to be correct:

```
(defspec t-trusted-implementation-score 100
  (for-all [game bowling-game-gen]
           (= (trusted/score game)
              (our/score game))))
```

Finding a good input-output relationship is the art of property testing.
Essentially you're looking for two different ways to calculate the same thing.
One example was hinted at above where we could replace all spares with strikes
and compare the resulting scores. Here are some other examples:

```
(defspec t-reversing-relationship-1 100
  (for-all [col (gen/not-empty collection-gen)]
           (= (first col)
              (last (reverse col)))))

(defspec t-reversing-relationship-2 100
  (for-all [col collection-gen]
           (= col
              (reverse (reverse col)))))

(defspec t-reversing-relationship-3 100
  (for-all [col-a collection-gen
            col-b collection-gen]
           (= (reverse (concat col-a col-b))
              (concat (reverse col-b) (reverse col-a)))))
```

Now go have fun, and find some bugs!
