---
title: Vide Code Series. Part 7. 
date: 2026-05-23  
categories: [Projects, Vibe Coding, Learning Tools]
tags: [Vibe Coding, crossfit, hiit, emom, JavaScript, Gamification]
author: Shawn
pin: true
image: assets/img/title_images/Project_VibeRSZ.jpeg
---
# Vibe Coding Project: EMOM Timer

Day 4 of vibe coding a new application every day or until I run out of ideas.

Today, something bubbled up from my memory banks, a good emom timer. 
There are millions of them out there, I can only imagine, but I wanted one to suit my own needs. 
A simple, large clock with a countdown timer to get started. 
Select number of rounds. 
A few different color options. 
A large button to start, pause or reset - because shaky and sweaty hands dont always cooperate. 
Audible alerts to avoid having to "watch the clock"

Iteration Count:
This took approximately 15 iterations to make it work as it does. I intend to put it to use next week and fine tune. 
Probably the most practical application I have pushed out yet. 

## [View the live demo here](https://shawnldonahue.github.io/Project_Vibe_VII/).

## AI Generated Summary of My Prompt

```bash
- Application: EMOM (Every Minute On the Minute) training timer clock

- Core UI layout:
  - Centered large digital clock display
  - Top status bar showing:
    - Current round status (READY / ROUND X / DONE)
    - Elapsed time tracker
  - Bottom control panel for configuration and theme selection

- Timer behavior:
  - Supports EMOM workout rounds based on user-selected count (5, 10, 15, 20)
  - Prep phase before EMOM begins (short countdown)
  - Each EMOM round runs on a fixed 60-second interval
  - Automatic round progression
  - Audio cues:
    - Beep near end of work interval
    - Whistle on transitions
    - Buzzer on completion

- Controls:
  - Start / Pause button:
    - Toggles timer execution
    - Changes label dynamically (START / PAUSE)
  - Reset button:
    - Resets full state (rounds, timer, elapsed time, phase)

- Visual design requirements:
  - Neon / glowing fitness timer aesthetic
  - Clock uses large, bold digital typography
  - Glow effect uses text-shadow based on selected theme color
  - Theme affects entire visual identity of the clock

- Theme system:
  - User-selectable themes:
    - Green
    - Red
    - Orange
    - Cyan
    - Rainbow (animated cycling colors)
    - USA (animated red/white/blue cycle)
  - Theme selection dynamically updates:
    - Clock color/glow
    - Button border glow (must match clock glow color)

- Button design rules:
  - Start/Pause button:
    - Sized at 80% width relative to clock container
  - Reset button:
    - Positioned directly under Start/Pause
    - Sized at half the width of Start/Pause button
  - Both buttons:
    - Must visually inherit or match clock glow color
    - Border glow must dynamically reflect selected theme

- Interaction requirements:
  - No disruption of existing timer logic when adding UI changes
  - Minimal structural changes allowed when modifying styling
  - Design changes must not alter timer state machine behavior

- Overall intent:
  - High-visibility functional workout timer
  - Fast interaction during training
  - Strong visual feedback tied to workout state and theme selection
```