---
title: Vide Code Series. Part 1. 
date: 2026-05-19
categories: [Projects, Cybersecurity, Learning Tools]
tags: [Linux, Ubuntu, Terminal, Vibe Coding, JavaScript, Gamification, Cybersecurity Training]
author: Shawn
pin: true
image: assets/img/title_images/Project_VibeRSZ.jpeg
---

# Vibe Coding Project: Ubuntu Terminal Speedrun Trainer

A lightweight, browser-based Linux command game designed to rebuild terminal muscle memory—fast, simple, and intentionally minimal in complexity.

## [View the live demo here](https://shawnldonahue.github.io/Project_Vibe_I/).

Note: Discovered it's not mobile-friendly. Input issue. 
Next time.
Onward and upward. 

Note 2: Moving to a new hosting repo soon. Hosting inside of the Chirpy blog page breaks a lot. 
---

## Author Commentary

I wanted to test out some vibe coding and provided ChatGPT with the following prompt:

```bash
Vibe Code Project: A game like program that will run a user through a series of basic Ubuntu Terminal commands. The purpose is to act like a speedrun of commands for users who might forget them and are jumping into the terminal after a long break. The commands should cover everything from time, directory navigation, creating / renaming / moving files, etc. The program will ask a user to enter the command do "X" purpose and then correct them if they are wrong. The system should ask 10 random questions from a pool of maybe 100. If the user fails below 60% then they are given 10 more questions. IF they score above 60%, they are congratulated. This should be a VERY simple program. IT should EASILY be hosted on a raspberry pi or ubuntu web page. the interactive area should appear as a terminal with "AmnesiaFree@UbuntuMachine"
```
That's it. Extremely simple.

So, then I hosted it to a page here on my github. 

I intend to build more elaborate projects in the near future and then start finding ways to evaluate them from a security posture or break them deliberately.

Below is the remainder of the article, following my own input procedures and written by AI. 

## What “Vibe Coding” Actually Means

“Vibe coding” isn’t a formal software development methodology. It’s more of a working style or mindset.

Instead of starting with strict architecture, detailed planning documents, or layered system design, you begin with intent and iterate quickly:

> “I want to build something that does this… now let’s make it real.”

It emphasizes rapid prototyping, intuition-driven development, and continuous refinement. The goal is momentum over perfection in the early stages.

Different developers approach it differently:

- Some use it for structured rapid prototyping
- Some treat it as experimental, creative development
- Others use it as a way to explore ideas before formalizing them

All approaches are valid depending on the goal, but the common thread is speed and iteration.

---

## The Hidden Risk of Vibe Coding

Speed is useful, but it introduces tradeoffs.

### Technical Debt
Quick builds often result in:
- Unstructured logic
- Tight coupling of features
- Difficulty scaling or refactoring later

### Security Considerations
Even simple web-based tools can introduce risk when deployed publicly:
- Unvalidated input assumptions
- Overexposed functionality when moving from local to public hosting
- Copy-paste logic without security review

This project avoids those issues by design. It does not execute system commands. It only compares user input as plain text.

### False Sense of Completion
If it works, it can feel finished. In reality, working code is not always maintainable or production-ready code.

Vibe coding works best when paired with later cleanup and review.

---

## Project Overview: Ubuntu Terminal Speedrun Trainer

This project is a browser-based Linux command training game designed to reinforce command-line fluency through repetition and recall.

Think of it as:

> A terminal simulation that tests your memory under light pressure, without requiring an actual shell.

---

## Core Concept

The system presents users with randomized Linux command prompts such as:

- file navigation
- file creation and deletion
- system inspection
- process management
- permissions and package handling

Users respond by typing the correct command.

Example:
“Show current directory” → `pwd`

---

## Game Flow

### 1. Question Selection
- A pool of approximately 100 Linux command questions
- Each session randomly selects 10 questions

### 2. User Input
- The user enters commands into a terminal-style interface
- The session identity is displayed as:
  `AmnesiaFree@UbuntuMachine`

### 3. Validation
- Input is normalized and compared against expected answers
- Immediate feedback is provided:
  - Correct
  - Incorrect with correct answer shown

### 4. Scoring System
- Score is calculated out of 10
- Passing threshold:
  - 60 percent or higher results in success
  - Below 60 percent triggers another randomized training round

---

## Why This Works

This project leverages core learning principles:

- Active recall improves retention more than passive reading
- Randomization reduces memorization bias
- Immediate feedback reinforces learning loops
- Repetition builds procedural memory over time

It is essentially a lightweight spaced-repetition system disguised as a terminal game.

---

## Architecture and Simplicity

The design intentionally avoids unnecessary complexity:

- No backend
- No database
- No authentication system
- No frameworks

It consists of:

- HTML for structure
- CSS for terminal styling
- JavaScript for logic and scoring

This makes it easy to deploy on:
- Raspberry Pi
- Ubuntu web servers
- Static hosting platforms
- GitHub Pages or similar services

---

## Security Considerations

Even simple applications benefit from security awareness:

- User input is never executed as a system command
- All validation occurs in-browser
- No external system access is required or exposed
- The application remains a simulation environment only

This keeps the tool safe by design, even when publicly hosted.

---

## Try It Yourself

The live version of this project is available here:

https://shawnldonahue.github.io/project/

If the page does not immediately show the trainer, scroll to the top of the page.

---

## Future Expansion Ideas

This project can evolve into:

- Timed Linux command speedrun mode
- SOC or incident response simulation drills
- Adaptive difficulty based on weak areas
- Multiplayer training sessions
- AI-assisted hint system for guided learning

---

## Final Thoughts

Not every project needs to be complex, scalable, or production-grade.

Some tools are most valuable when they are simple, focused, and immediately useful.

This project is one of those—a lightweight terminal trainer designed to reinforce forgotten knowledge and rebuild confidence with Linux command fundamentals.