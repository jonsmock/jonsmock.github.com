---
layout:     post
title:      First Speaking Experience
date:       2016-12-11 23:13:00
summary:    Who the heck let me give a talk already?
categories: blog
---

This (ridiculous) post is a mix of advice on preparing a talk and my experience
[as a speaker](https://www.youtube.com/watch?v=d76e4hV1iJY) at this year's
Clojure/conj. Hopefully writing this up helps anyone else that's curious about
presenting.

## Idea

Somehow last year's Conj really motivated me to do a talk. With no particular
idea in mind, my strategy was to learn something new and bring it back to the
community. I decided to start reading about various topics related to
declarative programming - (start of) Will Byrd's dissertation, core.logic,
rule engines, and solvers. We did already use clara-rules at work, and I tried
to dig up some of Fogus's old stuff about the rule engine he was building.

I also did the one thing I never do:  I took notes. I've always been an
atrocious student, which I regret for many reasons. But chief among them might
be that I never learned to take good notes. Regardless, I just started writing
stuff into a notebook.

Eventually I drilled down into SAT solving, and I got hooked on a few papers.
I found a [workshop](http://www.birs.ca/events/2014/5-day-workshops/14w5101/videos)
between theorists and implementors, where they had posted the videos. This
seemed like a pretty large area that we never touch on in Clojure-land. And hey,
if I really liked it, someone else probably would too. (Clojurians seem to be
practioners with an eye on research.)

If you're interested, I eventually turned my resources into [this](jonsmock.com/sat-talk).

## Preparation

Setting aside not being an expert on SAT solvers, this talk was probably one of
the easier types of talks to give. It's basically a book report. I didn't have
to build anything (although I had big dreams early on). I also reminded myself
over and over that it wasn't a keynote. I didn't have to blow anyone's minds;
I just had to teach and entertain. I'll let you decide if I succeeded.

When preparing, I basically followed the [SPJ school of paper writing](https://www.youtube.com/watch?v=g3dkRsTqdDA).
His advice is to start writing the paper *first* and let the paper drive the
research. If you apply this advice to preparing a talk, you would give the talk
before even submitting your abstract. I've heard that's exactly what Gary
Bernhardt does. When I submitted the abstract, I had a fleshed out, mostly
fact-checked outline. This helped me not to overpromise but still write a
proposal that I confidently could deliver on.

Once accepted, I moved my outline into Keynote. Again, I didn't "invent" here; I
just used Keynote. I created one slide per point, sometimes with only a title or
the point as a sentence in huge font. This was the first version of the talk
that I gave to someone else! (Well, at least we walked through it and explained
all the key concepts fully.) It was incredibly helpful to get this early read on
the material and my ability to explain things.

In general, I recommend showing or performing your talk for someone else at
least every two weeks. I noticed the longer I went without showing someone, the
more anxiety I felt about having a terrible talk, etc etc. Showing someone
instantly cures that and gives you actionable stuff to work on next.

I didn't work on things in any particular order. Generally my brain would
fixate on section for several days as I figured out a good way to explain it.
I also tried to *not* avoid weak sections for too long. Funny how working on
a weak section made that section better than the rest, turning other sections
into weak sections. Rinse and repeat.

As you start finishing sections of slides, practice those as you would give
the final talk. The first cut of my "Satisfiability" section was 17 minutes -
uh oh. It was good to get that information early, weeks before the rest of
the talk was "done."

I practiced my talk for my iPhone recorder app, which seemed to add just a
little pressure. (I even listened to one of those sessions once!) And, of
course, give the talk to other people, even if half of the talk is unfinished.
I ultimately gave my talk for a coworker, two friends, and my speaker mentor
(I'll come back to this shortly).

Learnings from showing people:

 - Others' general familiarity with topic
 - How to explain the ideas and diagrams
 - Starting with concrete problem works really well
 - What pieces to cut
 - What jokes were funny

My only other advice is to refactor/reorder/cut sections aggressively. Treat
the audience as the intelligent people they are. Try to keep the engaging
bits, and if a section drags, figure out why or cut it. At times this is
painful. I spent 1.5 hours animating a whole section on clause rewriting,
only to recognize that it dragged. I couldn't bear to delete it, so I put it
in my "slide graveyard," a section I created after my last slide. The only
section ever resurrected from the graveyard was the few slides on logic
notation. Having the slide graveyard freed me to delete, when I knew I had to.
I believe I have 80-90 slides in there now.

Some people might be wondering what the time commitment was. I honestly don't
know. I tried to keep track early on, but it made the whole thing feel like
work. The only thing I can estimate is the actual preparation during the two
months after talk acceptance. Based on my back of the napkin math, I spent about
60 hours working on slides and another 15 hours practicing. Maybe that seems
like a lot, but I thought of this as a mini-product. The original reading was
for myself anyway, and 75 hours to ship a product isn't so bad.

## Mentor

The Clojure/conj has an awesome speaker mentor program. If you're running a
conference, please copy this. If you want to speak, I highly recommend you take
advantage of this program.

Basically, if you opt-in, they will pair you with a speaker mentor for a one
hour online video chat. It was easy to setup, and my mentor was open to helping
me with any aspect of the talk. This is a chance to get help from an experienced
speaker, who doesn't know you and can give you honest, constructive feedback.

Here are just some of the notes from that meeting:

- I used the word "force" during unit propagation; the mentor suggested "infer"
- I had 1 and 0 on diagram/graph slides to save space; the mentor suggested T/F
- The mentor noted which phrased I used that were good and worth keeping
- The mentor commented on pacing and humor
- Red color on Intermission venn diagram slide; my original colors were not
  contrasty enough

These are small things perhaps, but I definitely notice the difference. But,
more than anything, the meeting gave me a huge boost in confidence.

Other bits of general advice from the mentor:

- Don't panic if you get stuck; nobody knows. Take a "dramatic pause" or a sip
  of water. It's fine. (I had probably 8+ of these moments...)
- Don't shy away from using language from the research literature. We want to
  learn something, not just be entertained. (I didn't show him the notation
  slides, but this comment prompted me to put them back in)
- Don't worry about "um"s and "uh"s.
- Try to enjoy the conference before your talk. It won't be easy, but try!

## Conference

[I'm going to omit names in non-speaker, non-organizer interactions. I assure
you I haven't forgotten your name! I just want to respect your privacy.]

Conferences have a total summer camp effect. This year did not disappoint! I met
a ton of new friends, met up with old friends, and filled my small notebook with
crazy ideas and board game references.

Immediately after my plane landed I got on the conference Slack and hooked up
with someone on my same plane. We met up and walked to the bus, where we met yet
another Conj'er. Of the two, one had literally just started programming months
before and the other had been doing high frequency trading and other stuff
in Java since 2000. I love that newcomers and experienced hands can comingle,
and everyone is welcome at the Conj.

At the hotel, I practiced a bit and got a bite to eat before meeting up with my
boss.

### Day 1

The phenomenal organizer, Lynn, recognized me in line and got me setup. I had
gotten to registration early so that I could check my slides before things
began. [Bill](https://www.youtube.com/watch?v=ipDhvd1NsmE) was also waiting to
check slides. Talking through our main points helped to put me in the right
mindset, and it was also reassuring that, yes, I have a talk that at least
someone is interested in.

[Paula kicked things off](https://www.youtube.com/watch?v=8rRzESy0X2k)
with a talk about logic, rules, datalog, and graph databases. I'm in the middle
of rewatching this talk, because while I'm a huge fan of rule engines, I fixated
on Paula. She looked confident and relatable, and it gave me a bit more courage.
By the time [Stu finished his talk](https://www.youtube.com/watch?v=oOON--g1PyU),
I felt pretty relaxed.

I hooked up with [Mike](https://www.youtube.com/watch?v=Q_k5MkZmd-o) and his
coworker for lunch. We had gotten together last year over lunch to talk about
clara-rules. Funny that we both independently submitted talks for this year's
Conj. After lunch I found a quiet place to put this finishing touches on
[my references page](http://jonsmock.com/sat-talk/).

In general, my advice to conference goers is not to worry too much about missing
talks. You're there with people; be with people. I definitely prioritize
continuing cool conversations over hitting everything that's happening on stage.
(Plus - seriously - how does the A/V team get those videos up so fast?)

To finish out the talks, Rich gave us a very nice rant about (not) breaking
code. The main point of the talk could be boiled down
[to the Growing Your Software slide](https://youtu.be/oyLBGkS5ICk?t=22m22s).
I definitely agree that as an industry, we are too quick to break our software,
which is completely inconsiderate of the consumers of that software.

My boss and I had an incredible dinner at [Chez Nous](http://cheznousaustin.com/),
before finishing the day with a couple well-done unsessions.

## Day 2

After the morning talks and hallway conversations, we found a group to go to
lunch with. I wanted something light, and Will Byrd's group sounded like they
were going somewhere for pizza - ok, close enough. When that place was closed,
we went [here](http://gourdoughs.com/) to get burgers on donuts. Yikes. It was
actually delicious, and more than the food, I really enjoyed the people we had
lunch with.

I think we got back late, and I hit the hotel room to go over my talk one more
time. I did it in 40 minutes flat, which was on par with just about every other
practice run I had done (maybe 10-15 times). The fastest I ever had given the
talk was to my speaker mentor, which came in at 38:30, and I had added the
logic notation slides after that. Welp, I clocked the real thing at 35:21. My
coworker playfully mocked me afterward for basically mic-dropping and not taking
questions with five minutes left - ha.

All the feedback after the talk really seemed positive. A small group of awesome
people stuck around to fistbump and shake my hand, which felt really good. It
was a little overwhelming, and I accidentally forgot some of their names until I
re-met them later - oops, sorry! Luckily I did re-meet them later and got their
names in my notepad.

After my talk I ended up in an incredible conversation with the organizer of the
after-party game (a game called Codenames). We hooked up with a few other people
for dinner at the conference hotel before the after-party.

## Day 3

The highlight of Day 3's talks for me was the [one on Barliman](https://www.youtube.com/watch?v=er_lLvkklsk).
I love relational programming, and program synthesis seems so cool to me. After
the talks and a hallway discussion, we ended up at [Fogo de Chao](https://fogodechao.com/)
with Greg and another engineer who does some interesting IoT stuff.

If you can stay the day after, I highly recommend it. My final destination is
a tiny airport with limited flights, so I had to stay the following day anyway.
But staying Saturday meant having that relaxing lunch, reviewing the Barliman
code by myself for a bit, and running into some people playing board games. A
group of us ended up shifting around a few different places, going out for fried
chicken, and playing one last Codenames game before bed.

## Retrospective

Overall, I'm extremely happy with my little speaking experiment. Now I know what
it feels like and what it takes, and it taught me that I *can* ship little side
projects if I focus myself properly.

What I think worked well about the talk:

- Using Keynote
- Starting with a concrete problem
- Clear title slides and outline
- No real bio slide or "Why me?" section (Personal taste maybe)
- Concise description of SAT problem and terminology for talk
- Stepping through the algorithms visually (I had code originally)
- Off-hand comments and asides were appropriate (and not too many)
- Trying my best to not downplay my "authority" or saying "I'm not an expert"
  *too* much (although I did address it a few times)
- Basically being myself, even if I am "performing" a bit
- Didn't try to seem smart
- Treated my audience as smart
- Didn't get hung up when I stumbled over words, which helped to maintain a good
  tempo and flow throughout
- SAT instance visualization slide

What would I do differently:

- Not sure if the SAT problem statement "hooked" the audience enough
- I should have waited an extra couple minutes to let people trickle in. I was
  worried about time, so I started exactly at 3:00. Several people commented
  that they came a tad late, so they missed the problem setup.
- Perhaps I could have recapped more, maybe very quickly at the end of sections
- Fact check more - I think I had a couple factual errors in the Discussion
  section. I should have found an actual SAT expert as a reviewer.
- Maybe I should have cut the complexity class venn diagram thing. While I think
  the "lowering complexity" point remains, what was on the slide was wrong, it
  turns out. I basically did this for myself anyway; I'm not sure it needed to
  be there.
- I may have made Restarts sound like a separate algorithm, when it really is
  just something incorporated into the CDCL algorithm.
- I looked up the definition of satisfy weeks before, but I decided not to do
  the dictionary definition slide. I thought that everyone else would or that it
  might come off as cliche. Looking at the definition actually did help me, so
  maybe it would have been worth including.
- Practice more. Some of the stops-and-starts or studders were during key
  explanations that I just didn't practice enough.
- Think of better words than "thing" and "awesome." You could probably make a
  drinking game out of my talk - ha. Being more articulate under pressure
  probably comes with experience, I imagine.
