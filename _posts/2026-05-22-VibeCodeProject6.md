---
title: Vide Code Series. Part 6. 
date: 2026-05-22 14:15 
categories: [Projects, Vibe Coding, Learning Tools]
tags: [Vibe Coding, Cybersecurity, JavaScript, Gamification]
author: Shawn
pin: true
image: assets/img/title_images/Project_VibeRSZ.jpeg
---

# Vibe Coding Project: Powered Mind Map, lightweight

Yes, it's true, I skipped 5 - because it turned into a small passion project as I help my son work on a game which he was inspired to make while watching me work. 
He hijacked my app-a-day project but I love it and 
It will be added later once he gives the all clear - he's the captain for now. 

A quick mind-mapping tool. 
Admittedly, a lot of lessons learned on this one. 
1. AI codes far better when using iteration. You can't just ask for it make a change, you have to re-upload the code and ask for incremental changes. Despite quality of prompt; hope for the best but prepare for the worst. 
2. If you do attempt to simply "request modifications" the AI will hallucinate (sooner or later depending on complexity) and derail the entire mission.
3. This app took about 37 iterations to complete and tune - still not perfect but that was never the goal. 

## [View the live demo here](https://shawnldonahue.github.io/Project_Vibe_V/).

## AI Generated Summary of My Prompt
```bash
Powered Mind Map – User Requirements Summary
Single-file HTML mind map application that runs entirely in the browser
Polished, interactive, best-effort implementation
Structured hierarchical mind map (true parent → child relationships)
Nodes are not free-floating and do not drift
No spring / physics chaos (stable, deterministic layout)
Nodes spawn in valid positions (no overlapping on creation)
Root node is visible on load (not offscreen)
Clear visual connections between nodes (parent → child links)
Ability to:
Select a node
Add child nodes to the selected node
Edit node labels
Collapse / expand branches
Layout behaves like a tree, but still feels animated and alive
Zoom and pan support so large maps remain usable
Visual style:
Dark background
Clean, readable text
High contrast nodes and links
State persistence:
Save mind map state
Reload saved state
Designed to feel like a real mind-mapping tool, not a demo or toy
Browser-only (no backend, no build step, no frameworks beyond JS libs)
```