---
title: "Managing Risk in Intelligent Transportation Systems (ITS): Borrowed Frameworks"
date: 2026-03-29
pin: true
categories: [Cybersecurity, Transportation, Risk Management]
tags: [ITS, OT Security, NIST, NERC CIP, HIPAA, CIS Controls]
image: assets/img/title_images/ITS-Borrowed-RMF-Improved_rsz.jpeg
author: Shawn
---


# Managing Risk in Intelligent Transportation Systems (ITS): Borrowed Frameworks, Real Control

Intelligent Transportation Systems (ITS) live in a strange in-between world.

They’re **not quite traditional IT**.  
They’re **not fully industrial control systems (ICS)**.  
And—importantly—they **don’t yet have a universally adopted control framework of their own**.

But risk still exists.  
And risk still has to be managed.

So how does risk *actually* get managed in ITS environments today?

The short answer: **by borrowing mature disciplines from adjacent regulated domains**—OT, energy, healthcare, and enterprise security—and applying them pragmatically to traffic systems, field devices, and control networks.

The longer answer is what this article is about.

---

## ITS Risk Reality (Before the Frameworks)

Most ITS environments share common traits:

- Long-lived field devices (10–20+ years)
- Safety-critical outcomes (human health and safety)
- Vendor-managed firmware and proprietary protocols
- Limited patch windows (or none at all)
- Flat or semi-flat networks by necessity
- Operational ownership outside traditional IT

Sound familiar?

It should—because this is **classic operational technology (OT)** risk, even if we don’t always call it that.

---

## The OT Anchor: NIST SP 800-82 (Rev. 3)

When ITS practitioners want a technically defensible place to stand, they usually land here:

**NIST Special Publication 800-82 Rev. 3 – *Guide to Operational Technology (OT) Security***.

This document does *not* care what your system controls; power, water, or traffic signals. It cares about **how control systems behave**.

Key OT principles that map cleanly to ITS:

### 1. Safety First, Availability Always
- Confidentiality is secondary
- Integrity and availability dominate risk decisions
- A failed signal cabinet is worse than leaked logs

### 2. Compensating Controls Over Patching
- Patch latency is expected
- Network segmentation, access control, and monitoring matter more than CVE velocity

### 3. Zones, Conduits, and Trust Boundaries
- Field devices ≠ Technical Management Center ≠ enterprise IT
- Logical separation matters even when physical separation is impossible

### 4. Vendor Dependency Is Assumed
- Risk management includes contract language, firmware lifecycle, and supportability
- “Vendor risk” is *operational risk*, not procurement trivia

In practice, many ITS programs quietly align their architectures to **800-82 concepts**, even if they don’t formally declare it.

---

## The Energy Sector Parallel: NERC / FERC CIP

If you want to see what happens when OT risk becomes regulated, look at the energy sector.

**NERC CIP** doesn’t define security *best practices*—it defines **minimum enforceable behaviors**.

The biggest lesson ITS borrows from CIP isn’t controls—it’s **governance discipline**:

- Asset classification matters
- Documentation *is* a control
- You don’t secure everything equally—and that’s okay

Even without regulation, many DOTs naturally drift toward **CIP-like thinking** when risk becomes operationally visible.

---

## The Enterprise Control Spine: NIST CSF + 800-53

Where OT guidance ends, enterprise security fills in the gaps.

- Identity and access management
- Logging and auditability
- Change management
- Policy enforcement
- Third-party risk workflows

While **800-53** is often “too heavy” to apply directly, its **control intent** translates cleanly when scoped properly.

In ITS, the trick is **control scaling**:
- One strong access control at the Technical Management Center is better than 30 weak ones in the field
- One authoritative asset inventory beats 10 spreadsheets nobody trusts

---

## The Quiet Similarity: HIPAA (Yes, Really)

Here’s where things get interesting.

While ITS has nothing to do with healthcare, the **HIPAA Security Rule** quietly mirrors how mature ITS programs already behave.

### Administrative Safeguards
- Risk analysis 
- Risk management 
- Workforce access control 
- Vendor accountability 

### Technical Safeguards
- Unique user identification 
- Access controls 
- Audit controls 
- Transmission security 

HIPAA never mandates *how* to implement controls—it mandates that you **demonstrate intent, assessment, and follow-through**.

That same model works remarkably well for ITS:
- Fewer prescriptive controls
- More documented decision-making
- Strong emphasis on “reasonable and appropriate”

In other words: **process maturity over checkbox security**.

---

## The Control Rosetta Stone: CIS Critical Security Controls

If NIST defines *what* and CIP enforces *how much*, the **CIS Critical Security Controls (v8)** explain *how to actually do the work*.

Why CIS maps well to ITS:

- Asset inventory (IT *and* OT)
- Secure configuration baselines
- Controlled use of administrative privileges
- Network monitoring and defense
- Incident response fundamentals

CIS works because it’s **operationally realistic**—especially when adapted:

- Field devices grouped by class, not individually managed
- Monitoring at aggregation points, not endpoints
- Controls prioritized by blast radius, not perfection

---

## So How Is ITS Risk *Really* Managed?

In practice, mature ITS risk programs:

1. **Classify systems by safety and operational impact**
2. **Borrow OT architecture principles from NIST 800-82**
3. **Adopt CIP-style governance discipline without regulatory weight**
4. **Use enterprise frameworks for identity, logging, and process**
5. **Treat vendors as long-term operational partners**
6. **Document risk decisions as deliberately as technical ones**

No single framework does this alone.

But together?  
They form a **defensible, auditable, and realistic risk posture**—even in the absence of ITS-specific controls.

---

## The Future: ITS-Specific Controls (Eventually)

ITS will likely get its own control framework someday. In fact, I Regularly meet with the people behind the scenes and work with them to do so.

Until then, the strongest programs won’t wait.

They’ll continue doing what works:
- Multidisciplinary risk management
- OT-aware engineering
- Enterprise-grade governance
- Safety-first security decisions

And when ITS-specific controls *do* arrive?

The organizations already operating this way won’t have much to change at all.

---

## References

- NIST SP 800-82 Rev. 3 – *Guide to Operational Technology (OT) Security*
- NIST SP 800-53 Rev. 5 – *Security and Privacy Controls*
- NIST Cybersecurity Framework (CSF) 2.0
- NERC CIP Reliability Standards
- HIPAA Security Rule (45 CFR Part 164)
- CIS Critical Security Controls v8

---