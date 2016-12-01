---
layout: page
title: Jon Smock - A Peek Inside SAT Solvers 
permalink: /sat-talk/
---

[Video coming!]

The goal of this talk was to introduce SAT solving, learn some cool algorithms, and get everyone excited about declarative programming. Go check
core.logic and rule engines as well!

## Wikipedia

Basic terminology:

- [Boolean Satisfiability (SAT)](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem)
- [Conjunctive Normal Form (CNF)](https://en.wikipedia.org/wiki/Conjunctive_normal_form)
- [Conflict-driven Clause Learning (CDCL)](https://en.wikipedia.org/wiki/Conflict-Driven_Clause_Learning)

Important Pieces from Propositional Logic:

- [Contraposition](https://en.wikipedia.org/wiki/Contraposition)
- [DeMorgan's Laws](https://en.wikipedia.org/wiki/De_Morgan%27s_laws)
- [Resolution (not mentioned in talk)](https://en.wikipedia.org/wiki/Resolution_(logic))

Random:

- [List of NP-Complete Problems](https://en.wikipedia.org/wiki/List_of_NP-complete_problems)
- [Undecidability vs. Semi-decidability](https://en.wikipedia.org/wiki/Undecidable_problem)
- [Discussion of SMT solving](https://en.wikipedia.org/wiki/Satisfiability_modulo_theories#SMT_solver_approaches)

## Videos

Videos taken from a SAT solving workshop between implementers and theorists:

- [Marijn Heule on how CDCL solvers work](http://www.birs.ca/events/2014/5-day-workshops/14w5101/videos/watch/201401200903-Heule.html)
- [Empirical study of SAT solver features (Features chart slide)](http://www.birs.ca/events/2014/5-day-workshops/14w5101/videos/watch/201401202003-Sakallah.html)
- [List of all videos from workshop](http://www.birs.ca/events/2014/5-day-workshops/14w5101/videos)

Discussion-related and general edification videos:

- [Advances in Automated Theorem Proving (Complexity class slide)](https://www.youtube.com/watch?v=unXzJEc3Pvk)
- [Tim Ewald - Clojure: Programming with Hand Tools](https://www.youtube.com/watch?v=ShEez0JkOFw)
- [Superoptimizing LLVM by John Regehr](https://www.youtube.com/watch?v=Ux0YnVEaI6A)
- [Random amazing interview with Will Byrd about logic, prolog, etc](https://www.infoq.com/interviews/byrd-relational-programming-minikanren)

??
# Similar talks to mine:
# 
# 
# Another talk where the first few minutes are similar to mine:
# (TODO: look at KLEE)
# Talks about separation of concerns (what / how)
# This talk talks about community structure (structure of the instance that helps it be tractable - similar to Will Byrd’s discussion)
# Interesting bit in the middle about conflict clauses - they make the assertion that high quality conflict clauses (the ones you want to keep) span very few communities
# Main talk is 16 minutes
# https://www.youtube.com/watch?v=AY2b54d-HSo
# 
# 
# - [Analyzing programs with Z3]
# Analyzing programs with Z3
# https://www.youtube.com/watch?v=ruNFcH-KibY
# Includes a quick talk about SAT and Z3 theories - unbounded ints, reals, bitvectors, floating point, arrays … (need to find all the ones)


## Papers

Summary papers that helped me learn about this stuff:

- [Cornell SAT Solvers overview](http://www.cs.cornell.edu/gomes/papers/satsolvers-kr-handbook.pdf)
- [Princeton overview of Clause Learning](https://www.cs.princeton.edu/courses/archive/fall13/cos402/readings/SAT_learning_clauses.pdf)

Papers introducing key techniques:

- [Chaff/zChaff introducing VSIDS and Two Watched Literals](https://www.princeton.edu/~chaff/publication/DAC2001v56.pdf)
- [GRASP introducing Clause Learning](http://eprints.soton.ac.uk/262031/1/jpms-iccad96.pdf)
- [Minimizing learned clauses](http://fmv.jku.at/papers/SoerenssonBiere-SAT09.pdf)
- [Blocked Clause Elimination](http://fmv.jku.at/papers/jarvisalobiereheule-tacas10.pdf) (a pre-processing techinque that I didn't discuss)

Other papers:

- [Cube and Conquer](https://arxiv.org/pdf/1605.00723v1.pdf) (very readable, covers basic SAT terminology, combines look-ahead solvers and CDCL solvers, 2 Tb unsat proof!)
- [SAT instance visualization](https://uwaterloo.ca/embedded-software-group/sites/ca.embedded-software-group/files/uploads/files/sat-satgraf.pdf) (the visualization I used in my slides)
- [More SAT instance visualization](http://cse-wiki.unl.edu/wiki/images/7/71/DPvis-Sinz.pdf)


## Miscellaneous

Parts directly used in my talk:

- [My Stackoverflow question about Declarative Programming](http://stackoverflow.com/questions/1238775/programming-languages-that-define-the-problem-instead-of-the-solution)
- [2016 SAT Competition](http://baldur.iti.kit.edu/sat-competition-2016/)
- [Sudoku in core.logic gist](https://gist.github.com/swannodette/3217582) by David Nolan (and [updated](https://gist.github.com/orb/5884956))
- [Sudoku problem in my talk](http://www.websudoku.com/?level=1&set_id=4817395213) (is Sudoku copyrightable? I have no idea, so I linked it)

Two more technical slideshows:

- [Slideshow from a talk about CryptoMiniSat](https://www.msoos.org/wordpress/wp-content/uploads/2016/07/seven_years.pdf) (a real life look at SAT solver implementation)
- [Slideshow of how SMT solvers work](http://www.open-do.org/wp-content/uploads/2010/06/SMT_provers.pdf)

Introduction to Z3 syntax (I used an example from here during the SMT section):

- [Intro to Z3 syntax](http://rise4fun.com/z3/tutorialcontent/guide)

## Design

I used Chunk, Raleway, and News Gothic MT for the text and Lucida Console for code samples.

- [Chunk font](https://www.theleagueofmoveabletype.com/chunk)
- [Raleway font](https://www.theleagueofmoveabletype.com/raleway)

I pulled the color palatte from [ColourLovers](http://www.colourlovers.com/palette/4327563/Gigi_Flower).

## Theme Music

This is only in my head, but the theme music for this talk is ["Binky" by Snarky Puppy](https://youtu.be/IE9I6NrE2S0?t=2m27s).
