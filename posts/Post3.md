---
title: Assessing Feasibility and Refining BakeLab’s Scope
date: 2026-5-7
author: Belle Kwon
summary: This post reflects on how our group refined BakeLab’s scope by prioritising the core diagnosis workflow and considering technical feasibility, user flow, and project constraints.
tags:
  - feasibility
  - scope-planning
  - user-flow
---

After identifying BakeLab’s core functional requirements, the next step was to assess whether our proposed features were realistic for the A2 prototype. At this stage, our group had several possible directions, including structured bake records, community feedback, starter logging, personal bake history, comparison tools, and live bake support. However, trying to include all of these features in the first prototype would make the project too broad and difficult to complete reliably.

The main scope decision was to focus on the core diagnosis workflow. This means the prototype should prioritise the path where a user creates a structured bake record, chooses whether to share it, opens a bake detail page, and receives structured community critique. This workflow is the strongest part of BakeLab because it directly connects to the research insight that sourdough bakers need context-rich feedback, not just casual comments.

![BakeLab user flow showing the core diagnosis workflow](../assets/user-flow-bakelab.png)

The first feature we decided to keep essential is the New Bake flow. Users need a way to record important baking variables such as hydration, flour mix, starter activity, temperature, fold count, result, notes, and photos. Without this structured input, the rest of the app would not have enough context to support diagnosis or learning.

The second essential feature is the Community Feed. However, this feed should not work like a normal social media feed. Instead of prioritising endless scrolling or popularity, it should help users scan shared bakes quickly and decide which ones are useful to open. This keeps the feed aligned with BakeLab’s purpose as a learning and troubleshooting space.

The third essential feature is the Bake Detail / Diagnosis Page. This page is the most important part of the prototype because it brings together the bake data, process notes, outcome, feedback request, and community critique. In the wireframe planning, this page is treated as a collaborative diagnosis workspace rather than a traditional post page. This helped us refine the scope around one strong interaction instead of many disconnected features.

The Starter Log is useful because starter care is a repeated behaviour and could encourage users to return regularly. However, it should remain lightweight in the first version. It should support quick logging rather than becoming a complex tracking system with advanced statistics or predictions.

Some features should be treated as optional for now. These include advanced bake comparison, smart prompts, notifications, recommendation systems, and detailed progress analytics. Although these features could improve BakeLab later, they would increase technical complexity and distract from the main prototype goal.

This scope also needs to work within the required stack of MojoJS, SQLite, and HTMX. SQLite can store bake records, comments, starter logs, and shared/private states. MojoJS can support routes for the feed, new bake form, bake detail page, and personal archive. HTMX could be used for smaller interactions, such as submitting feedback or updating parts of the interface without a full page reload.

**AI Acknowledgement**

I acknowledge the use of ChatGPT to assist with generating summaries, writing image alt text, checking grammar, improving writing flow, and paraphrasing sentences.
