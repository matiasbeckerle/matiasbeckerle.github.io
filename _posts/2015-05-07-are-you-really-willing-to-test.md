---
layout: default
title: Are you really willing to test?
tags : [unit testing, development, tips]
---

If the answer is **no** then you should leave it. Don't writing tests is preferable than writing bad tests because you start to lose trust in the code when you discover the first one *not-so-successful-test*.

Another bad thing about unit testing is when you don't keep it updated. That's wrong because everyone in your team or even you start to get lazy. The testing start to fall little by little.

There is a lot to say about unit testing but I'm not deep qualified in the matter to talk about it. I prefer to leave you with some questions to identify bad unit tests:

- It takes a lot of time? A unit test should run really fast. Maybe you're not faking everything. Integration test is coming to my mind.
- You have to execute the tests in a particular order? Sounds like a dependency.
- Running tests individually (or isolated) to achieve greenlight? Could be a particular one messing with your setup.
