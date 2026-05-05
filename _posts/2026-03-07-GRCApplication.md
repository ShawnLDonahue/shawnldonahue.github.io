---
title: "Building Up and Deploying Out Free GRC Eramba"
date: 2026-03-07
pin: true #this allows you to pin the post at the top
categories: [cybersecurity, ai, homelab]
tags: [GRC, Eramba, home-lab, Ubuntu, Docker  ]
image: assets/img/title_images/GRCatHome_2.jpeg
author: Shawn
---


## Introduction

When organizations talk about improving governance, risk, and compliance (GRC), the conversation often stalls before it even begins.

Spreadsheets multiply, ownership becomes unclear, and any attempt to introduce a dedicated platform immediately triggers red tape: security reviews, architecture approvals, procurement processes, and stakeholder alignment meetings.

That friction is exactly why I chose to deploy *Eramba's Community Edition* quietly at home first.

Not as a shortcut—but as a way to truly understand the platform before ever proposing it inside an enterprise environment.

---

## The Problem With “Trying It Out” at Work

On paper, spinning up a test instance in an enterprise environment sounds reasonable. In reality, it rarely is.

Even a “simple” proof-of-concept can require:
- server provisioning requests  
- firewall and network approvals  
- security architecture reviews  
- documentation and change management  

By the time access is granted, momentum is gone and the evaluation is shallow at best.

Worse, enterprise environments are the *worst* place to learn a new platform:
- experimentation feels risky  
- mistakes feel permanent  
- iteration is slow  

For a foundational system like GRC, that approach almost guarantees failure.

---

## Why a Home Deployment Makes Sense

Deploying Eramba at home removed friction immediately:
- no approval cycles  
- no time pressure  
- no fear of breaking something “important”  
- complete freedom to explore  

Most importantly, it allowed me to learn Eramba **as designed**, not as constrained by existing enterprise systems.

This wasn’t about bypassing controls—it was about understanding them first.

---

## Standing Up the Environment (What I Actually Did)

The deployment followed a realistic, intentional process using Eramba’s own documentation—not shortcuts or vendor demos.

### Step 1: Base Operating System

The host system was:
- **Ubuntu 24.04 LTS**
- minimal install
- isolated from any enterprise network

This ensured a clean, modern baseline and eliminated variables caused by legacy OS versions.

---

### Step 2: Initial Docker Deployment

Eramba was deployed using Docker, following official guidance.

Early on, it became clear that:
- a single `docker run` approach was insufficient  
- service dependencies needed orchestration  
- persistence and restarts would become painful without structure  

This led to an important realization.

---

### Step 3: Transition to Docker Compose

To properly manage:
- the Eramba application  
- its database backend  
- networking and persistence  

I transitioned the deployment to **Docker Compose**.

This immediately improved:
-- startup ordering  
- configuration clarity  
- long-term maintainability  

This is exactly the kind of lesson that’s expensive to learn in production and trivial to learn at home.

---

### Step 4: Validating the Application

Once the stack was stable:
- application access was validated  
- services were monitored during restarts  
- configuration assumptions were tested  

Small issues surfaced quickly:
- dependency expectations  
- configuration nuances  
- documentation gaps that only appear outside managed environments  

These are the problems you *want* to encounter early.

---
### Step 5: Pop Open a Browser and Check Out Local Host

Easy peasy, lemon squeezy. 

![Login Splash Success!](/assets/img/title_images/SLDEramba.png)


---

## Modeling GRC Without Spreadsheets

Rather than importing anything, I started manually.

I:
- defined a small set of example risks  
- mapped basic controls  
- linked policies intentionally  

This exposed a critical difference between spreadsheets and a GRC platform:

> Spreadsheets tolerate ambiguity. Eramba does not.

Fields require ownership. Relationships must make sense. Gaps become visible immediately.

---

## Why Eramba Forces Better Discipline

In spreadsheets:
- risks live in isolation  
- controls are duplicated  
- ownership is implied  
- evidence is scattered  

In Eramba:
- risks link to controls  
- controls link to policies  
- policies align to frameworks  
- ownership is explicit  

What used to be tribal knowledge becomes traceable and defensible.

---

## The Real Challenges (And Why They Matter)

The home deployment was not frictionless—and that’s the point.

The hardest parts were:
- understanding Eramba’s opinionated data model  
- resisting the urge to recreate spreadsheets digitally  
- learning what *not* to model  
- accepting that structure requires discipline  

These lessons are painful in enterprise environments.
At home, they are safe.

---

## Why This Matters Before Enterprise Adoption

By the time Eramba is proposed in an organization:
- architecture questions are already answered  
- deployment pitfalls are understood  
- value can be demonstrated clearly  
- adoption risks are reduced  

The conversation changes from:
> “Can we try this?”

to:
> “Here’s how this works—and why it’s better.”

---

## The Bigger Lesson

This experience reinforced a broader truth about security tooling:

> The best way to introduce structure is to understand it deeply before asking others to adopt it.

Home deployments are not shortcuts.
They are rehearsal spaces.

They enable:
- safe experimentation  
- better design decisions  
- stronger justification  
- smoother enterprise rollouts  

---

## Closing Thoughts

Deploying Eramba at home wasn’t about avoiding governance.
It was about respecting it.

By learning the platform independently—using real documentation, real deployment methods, and real constraints—I gained the clarity needed to evaluate it honestly.

That preparation is what ultimately helps organizations move beyond spreadsheets and toward sustainable, defensible security programs.