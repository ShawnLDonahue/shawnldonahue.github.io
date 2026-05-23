---
title: Vide Code Series. Part 4. 
date: 2026-05-22 08:00
categories: [Projects, Vibe Coding, Learning Tools]
tags: [Vibe Coding, Cybersecurity, JavaScript, Gamification]
author: Shawn
pin: true
image: assets/img/title_images/Project_VibeRSZ.jpeg
---

# Vibe Coding Project: Cybersecurity Penetration Testing Tooling/Mapping
## [View the live demo here](https://shawnldonahue.github.io/Project_Vibe_IV/).

Just a quick simulator - non-functional - of an application that should effectively network map and provide open ports - while each open port is displayed with a commonly used tool related to further investigation. 
The goal is to allow an IP for scanning or simply a port. 

I think moving forward I will start tracking iterations. Some of these applications require dozens of iterations.

A future iteration of this would be converting to Python, making it functional, and run on Ubuntu.

## AI Generated Summary of My Prompt
```bash
* Build a single-page web application called **“Cyber Drilldown Simulator”** that can be hosted on GitHub Pages
* The UI should resemble a **desktop/security workstation application** with a top OS-style tray
* Top tray includes:

  * Centered app title in a clean font
  * Clock on the right
  * Buttons for **theme toggle (dark/light)** and **reset simulator**
  * Tray must remain consistently readable and not break when themes change
* Main UI uses a **dark granite background (or light theme equivalent)** with a professional SOC/dashboard feel
* Panels should represent a **drilldown workflow for reconnaissance**:

  * Input panel allows user to select **IP Scan or Port Scan**
  * User enters an IP or port and clicks **Scan**
* Simulated scan behavior:

  * UI shows a short “working” animation (fake scan process)
  * Generates realistic-looking Nmap-style output (open ports and services)
  * Uses randomized but plausible port/service combinations
* Data visualization structure:

  * Left column: Target / IP context
  * Middle column: Open ports (service exposure results)
  * Right column: Tool suggestions tied to each port/service
* Each port result:

  * Generates its own grouped “node”
  * Has a **unique color assigned per port**
  * That same color propagates to related tool suggestions and notes
* Tool suggestions:

  * Display real cybersecurity tools (e.g., nmap, gobuster, enum4linux, hydra, sslscan)
  * Include brief explanations of what each tool is used for
* Notes system:

  * Each tool has a textarea for analyst notes
  * Notes can be submitted via a button
  * Submitted notes generate a **new note card in a separate Notes column**
  * Note card color matches the originating port/tool group
* Remove visual connectors (no lines between elements)
* Replace graph-style relationships with **color-coded grouping instead of spatial linking**
* Ensure UI does NOT look like a spreadsheet; it should feel like an **investigation workspace**
* Include a persistent explanation note that results are color-coordinated for grouping and relationship tracking (simulation only)


```