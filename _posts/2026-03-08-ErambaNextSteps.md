---
title: "Eramba Next Steps: Building a Practical Risk Management Pilot (Before Anyone Calls It ‘Just Another Tool’)"
date: 2026-03-08
pin: true #this allows you to pin the post at the top
categories: [cybersecurity, grc, risk-management]
tags: [eramba, third-party-risk, dot, governance, homelab, strategy]
image: assets/img/title_images/GRCatHome_2.jpeg
author: Shawn
---

## Scope First — Because Everything Dies Without It

Before touching a single configuration screen, define what this actually is:

This is not an “Eramba implementation.”

This is a **controlled pilot for risk and third-party management in a small DOT-style environment**, where:
- vendors are many
- documentation lives in spreadsheets
- risk decisions are often “tribal knowledge with a signature”

The goal is simple:

> Prove whether structured GRC actually reduces chaos—or just formalizes it.

If it doesn’t improve clarity over spreadsheets, it gets cut. No emotional attachment.

---

## Step 1: Understand What Eramba Actually Is (Not What You Assume It Is)

Spend time in the documentation for *Eramba* before doing anything else.

Focus areas:
- Risk module structure (not just UI, but data relationships)
- Control framework mapping
- Third-party/vendor risk logic
- Evidence handling model
- Workflow and ownership model

Do not start by “clicking around.”

Start by understanding:

> What assumptions does Eramba make about how organizations think about risk?

Because it makes a lot of them.

Some helpful early realization:
- This is not a spreadsheet replacement
- This is a *forced structure system*
- If your data is messy, it will expose you immediately

Good. That’s the point.

---

## Step 2: Define the Pilot Environment (Keep It Small Enough to Control)

This is where most GRC efforts go to die—trying to model the entire organization on day one.

Don’t.

Instead, scope like this:

### Pilot Environment (DOT-style slice)
- 5–10 vendors max
- 10–15 risks total
- 10–20 controls
- 2–3 internal business processes
- 1 regulatory lens (don’t stack everything yet)

Example vendor categories:
- SaaS productivity tool
- Infrastructure vendor
- Managed service provider
- Traffic/transportation system vendor
- Data storage provider

If you can’t explain each vendor’s risk in one sentence, it doesn’t belong in the pilot yet.

---

## Step 3: Map the Real Third-Party Risk Flow (Not the Paper Version)

In a small DOT environment, third-party risk usually looks like this:

1. Vendor gets introduced through operations or engineering
2. Security gets looped in late (or not at all)
3. Questionnaire gets filled out as a formality
4. Spreadsheet gets updated if someone remembers
5. Contract is signed
6. Everyone assumes “risk is handled”

That is the baseline you are replacing.

Now map it in Eramba:

- Vendor → Asset relationship
- Vendor → Risk association
- Vendor → Control mapping
- Vendor → Review cycle (recurring, not one-and-done)
- Vendor → Evidence tracking

The key shift:

> Vendors are not entries. They are living risk entities.

If it doesn’t behave like something you continuously manage, you’ve already failed the model.

---

## Step 4: Identify Dependencies Before You Deploy Anything Serious

Before scaling beyond a lab instance, identify what Eramba actually needs to function properly.

At minimum, expect:

### Technical dependencies
- Ubuntu Server baseline (tested cleanly on 24.04 LTS)
- Docker runtime environment
- Docker Compose orchestration layer (this is not optional in real deployments)
- Persistent storage planning (don’t ignore this—GRC data is relational and stateful)
- Database backend (MariaDB/PostgreSQL depending on deployment pattern)

### Operational dependencies
- Defined risk taxonomy (or everything becomes noise)
- Named ownership model (no “team-owned” risks)
- Vendor inventory source (even if it starts as a spreadsheet import)
- Review cadence (quarterly at minimum for pilot realism)

If these don’t exist, Eramba won’t fix it—it will just document the chaos more precisely.

---

## Step 5: Build the Minimum Viable Risk Model

Do not over-engineer this.

Start with:

### Risk model
- Risk ID
- Description (plain English, not policy language)
- Impact (financial / operational / reputational)
- Likelihood (keep it simple at first)
- Owner (must be a person, not a group)

### Control model
- Control name
- What it actually does (not what policy says it does)
- Mapping to at least one risk
- Evidence source (even if manually attached at first)

### Vendor model
- Vendor name
- Service provided
- Data touched (be honest here)
- Criticality (low/medium/high—not 12-tier nonsense)

If you can’t explain the relationship between these three in a whiteboard session, the model is too complex.

---

## Step 6: Introduce Third-Party Risk as the First Real Use Case

Start here intentionally.

Why?

Because third-party risk:
- forces external accountability
- exposes gaps in ownership
- reveals how weak spreadsheet tracking really is
- makes “we assume they’re secure” unacceptable

In a DOT-style environment, this is where reality hits:

- vendors touch operational systems
- outages are public-facing
- contracts don’t always reflect actual exposure

This is where Eramba earns its keep—or doesn’t.

---

## Step 7: Expect the First Friction Points (They’re the Real Value)

Early friction is not failure. It is calibration.

Expect:
- confusion around how risks link to controls
- discomfort with forced structure
- realization that “we don’t actually know who owns this”
- gaps in vendor documentation you thought existed

This is where most people quietly revert back to spreadsheets.

Don’t.

This is the system telling you the truth.

---

## Step 8: Success Criteria (Keep It Brutal and Simple)

This pilot is successful if:

- I can trace a vendor → risk → control → evidence path in under 2 minutes
- ownership is explicit, not assumed
- third-party risk reviews become repeatable, not memory-dependent
- spreadsheets are no longer required for core tracking

If those aren’t true, the system is not ready for production use.

No politics involved.

Just signal vs noise.

---

## Closing Thought

This is not about implementing a tool.

It’s about answering a more uncomfortable question:

> Can structured GRC survive contact with a real operational environment without collapsing back into spreadsheets?

Eramba is just the instrument.

The real work is deciding whether discipline scales—or if chaos is just more comfortable.