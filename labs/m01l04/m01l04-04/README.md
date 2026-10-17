# m01l04-04 · One layer: a fail2ban jail

**Lesson:** [Defense-in-Depth & Security Control Categories](https://learnsome.tech/learn/cybersecurity-course/m01l04) (lesson 1.4, module 1: Core Security Principles) · Free  
**Check:** Read along

## Goal

You can sort any control by category and type under both the ISC2 and Security+ schemes, and test one layer of a real defence in depth design, a fail2ban jail, against an auth.log to find the attacks it misses.

## Files

- [`starter/jail.local`](starter/jail.local): the listing from the lesson
- [`check.json`](check.json): how `./check` runs and checks this lab

## Steps

1. Read `starter/jail.local` alongside the lesson.
2. Follow it the way the lesson builds it:
   - Lines 1–5: the three numbers
   - Lines 6–7: ignoreip
   - Lines 8–10: enables the S S H jail

## How to check

**Read along.** It is a listing to read alongside the lesson, not a program to run.

There is nothing to check: `./check m01l04-04` says so and moves on.

---

[Open the lesson on LearnSome.tech](https://learnsome.tech/learn/cybersecurity-course/m01l04) · [All labs of this lesson](../README.md) · [Course README](../../../README.md)
