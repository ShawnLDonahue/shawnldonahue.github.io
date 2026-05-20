---
title: Vide Code Series. Part 2. 
date: 2026-05-19
categories: [Projects, Cybersecurity, Learning Tools]
tags: [SecOps, Vibe Coding, JavaScript, Gamification, Cybersecurity Training]
author: Shawn
pin: true
image: assets/img/title_images/Project_VibeRSZ.jpeg
---

# Vibe Coding Project: SecOps Dashboard 

A lightweight, straightforward dashboard for team collaboration. 
Currently there is no persistance and so the page resets with each visit. 

## [View the live demo here](https://shawnldonahue.github.io/Project_Vibe_II/).

## AI Generated Summary of My Prompt

```bash
Project_Vibe II — Security Ops Dashboard Requirements

Core Concept
- Create a project called "Project_Vibe II"
- Build a pure HTML-based security operations dashboard
- Intended as a vibe-coded prototype (no backend / no persistence)
- All data resets on refresh or page exit (acceptable and expected behavior)

UI / Design Requirements
- Dashboard should look professional and operational
- Styled like a security operations / SOC-style dashboard
- Must feel:
  - Technology-focused
  - Clean and modern
  - Maintains professional appearance suitable for real-world use

Core Dashboard Panels

1. Active Projects Panel
- Displays a list of currently running projects
- Items should be:
  - Editable inline
  - Removable
  - Dynamically addable

2. Backlog / To-Do Panel
- Displays projects/tasks not yet started
- Supports:
  - Editable entries
  - Add/remove functionality
- Represents future work queue

3. Documentation / Knowledge Panel
- Contains links to key security documentation
- Examples include:
  - Incident Response Plans (IRP)
  - Security policies
  - Runbooks
  - Playbooks
- Labels can be cleaned up for clarity and professionalism

Team Availability Panel (Top Priority Panel)
- Positioned at the top of the dashboard for quick visibility
- Includes five predefined roles:
  - Manager
  - Senior
  - Junior
  - Contractor I
  - Contractor II

Availability Status Requirements
Each employee row must include:
- Employee name
- Status indicator light:
  - Green = Available
  - Red = Do Not Disturb / Busy states
- Timestamp field:
  - Shows last time availability changed
  - Displayed to the left of status controls

Interaction Requirements
- Each employee row must include a dropdown selector with standard reasons:
  - Lunch
  - Break
  - Personal
  - DND
  - Meeting
  - Focus
  - Project
- Changing dropdown must:
  - Update status light (green/red)
  - Update timestamp automatically
- Column headers must be clearly labeled

Functional Requirements
- Fully interactive in-browser
- No backend or storage layer
- No persistence across refresh (intentional limitation)
- All updates happen instantly via client-side JavaScript

```