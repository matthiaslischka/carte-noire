---
title: Creative Test Ignoring
layout: post
---

**Summary:** A short list of different ways of ignoring unit tests that I came across so far. Just for fun - no serious content.


I love tests. I love to have them around and most of the time I love to write them. I also love legacy code. I think there is a special beauty in polishing up old, well-aged, sometimes unloved code. Sadly, these two things don’t always go as smoothly hand in hand as one would wish.
One pattern that usually can be found in old legacy applications is the "*pattern of ignored unit tests*". Sad little tests that vegetate with a ``ignore`` flag and add no benefit at all. Recently I came across some other, more creative ways of ignoring unit tests that I want to share with you. Here is what I've found so far. This list is not made-up.

## The many ways of ignoring tests

- ignore flag on method
- ignore flag on class
- commented out test
- exclude test file from project but do not delete it
- only the assert commented out (yap, thats a nice one)
- deleted the assert
- ignore flag & commented out assert (because just in case)
- do not compile the whole test project
- set test file build action from `Compile` to `Content`
- **extra challenge:** combine as many as possible - because fu*k you unit tests:
  - ignore flag on class *and* method
  - comment out assert
  - set build action to `Content`

## Final thoughts

I tried to find some brilliantly witty words about *when* and *how* to ignore tests but ended up getting lost. There is just too much to consider and every project, every team and every developer is different. For now, I just want to conclude with a personal rule of thumb:

*"Keep your tests well maintained and green or delete them completely. Everything else is just dead code and a burden."*