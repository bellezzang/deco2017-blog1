---
title: Introducing Data, Structure, and Flow in BakeLab
date: 2026-05-15
author: Belle Kwon
summary: This post explains how BakeLab’s wireframes and user actions translate into database tables, relationships, and technical logic for the full-stack prototype.
tags:
  - data-structure
  - ERD
  - DDD
---

After refining BakeLab’s scope, the next step was to connect our interface decisions to the application’s data structure. This was important because BakeLab is not intended to be a static website. It needs to store user-generated bake records, display shared bakes in the community feed, support structured critique, and separate private records from public posts. Therefore, each visible part of the interface needs to connect to structured data.

![BakeLab data definition document showing how UI elements map to database fields](../assets/bakelab-ddd.png)

The central data object in BakeLab is the bake record. This is because most of the application experience depends on users creating, reviewing, sharing, and discussing bakes. In our database plan, the bakes table stores information such as title, hydration, flour mix, starter activity, room temperature, dough temperature, fold count, bake temperature, result, question, notes, photo URL, sharing status, and feedback types. These fields directly reflect the information users enter in the New Bake form and later view on the Bake Detail page.

The second important table is comments. In a normal social media app, comments might only store text. However, BakeLab needs more structured feedback because the goal is diagnosis, not casual conversation. For this reason, each comment includes a feedback type, such as crumb, oven spring, fermentation, starter, shaping, or general advice. It also includes a confidence level, so users can understand whether the feedback is a guess or based on stronger experience.

The users table connects each bake and comment to a person. Since BlaBla Corp already provides the basic login system, our group does not need to build full authentication from scratch. However, the application still needs to use the logged-in user’s ID to decide which bakes belong to them, which actions they can take, and how usernames appear across the interface.

The starter_logs table supports daily starter tracking. This table is separate from bakes because starter care can happen even when the user is not baking a loaf. It stores feeding time, rise percentage, notes, and the user who created the entry. This allows the Starter Log page to support quick repeated use without overcomplicating the main bake record.

A key structural decision is the use of public and private bake logic. The is_shared field controls whether a bake appears in the community feed. If a bake is saved privately, it remains in the user’s personal archive. If it is shared for feedback, it becomes visible to the community. This supports different user intentions without requiring two separate systems.

The ERD helped us clarify the main relationships: one user can create many bakes, one bake can receive many comments, one user can write many comments, and one user can create many starter log entries. These relationships show that BakeLab is built around repeated records and structured feedback, rather than disconnected posts.

![BakeLab ERD showing relationships between users, bakes, comments, and starter logs](../assets/erd-bakelab.png)

This planning also shows where SQL JOINs are needed. For example, the community feed needs to show bake information, the baker’s username, and the number of comments. Since these pieces of information come from different tables, JOINs are needed to reconstruct the full interface view. This connects our database design directly to what users see on screen.

Overall, this data planning helped our group confirm that BakeLab’s interface is technically grounded. The wireframes show what users need to see and do, while the ERD and DDD show how those actions can be stored, connected, and displayed. This makes the prototype more than a visual concept; it becomes a structured full-stack application plan.

**AI Acknowledgement**

I acknowledge the use of ChatGPT to assist with generating summaries, writing image alt text, checking grammar, improving writing flow, and paraphrasing sentences.
