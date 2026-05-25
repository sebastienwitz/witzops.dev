---
title: "Why I'm building WitzOps"
description: "Why WitzOps exists as a public engineering notebook for infrastructure, automation, observability, and AI-assisted workflows."
date: 2026-05-25
tags:
  - witzops
  - platform-engineering
  - self-hosting
  - ai-workflows
draft: false
---

Most infrastructure work disappears.

A service gets deployed. A tunnel is configured. A DNS rule is fixed. A pipeline starts passing. A dashboard eventually becomes useful. Then, a few weeks later, the reasoning behind those decisions is scattered across terminal history, private notes, half-written documentation, and memory.

WitzOps exists to fight that drift.

The goal is not to publish a perfect platform. The goal is to document the process of building one: the small decisions, the trade-offs, the experiments, and the patterns that survive contact with reality.

WitzOps sits at the intersection of a few things I care about:

- self-hosted infrastructure;
- DevOps automation;
- secure access;
- observability;
- Infrastructure as Code;
- AI-assisted engineering workflows;
- clear technical writing.

That combination matters because infrastructure is not just a pile of services. A useful platform needs structure. It needs names that make sense, routes that can be explained, access rules that are intentional, and documentation that survives longer than the person who typed the command.

It also needs boundaries.

Some notes are private by nature: exact hostnames, IP addresses, credentials, tunnel identifiers, admin URLs, and operational runbooks. Publishing those would not be documentation. It would be an invitation to regret.

But the thinking behind the system can be public.

A private runbook can become a public engineering article. A concrete setup can become a reusable pattern. A messy experiment can become a lesson. The important part is to remove the sensitive coordinates and keep the reasoning.

That is the editorial rule behind WitzOps:

```text
private implementation stays private;
public engineering thinking becomes reusable.
```

This site is also an experiment in working with AI agents more deliberately.

AI tools are good at generating code, but they are much more useful when the project gives them context: design direction, publication rules, architecture notes, and clear boundaries. WitzOps is built with that in mind. The repository is not just source code. It is also an instruction surface for future agents and contributors.

That means the documentation matters as much as the implementation.

The site starts small on purpose:

- a public landing page;
- a projects section;
- architecture notes;
- lab stack notes;
- short blog posts;
- project detail pages.

No grand launch. No fake maturity. No "revolutionary platform" language.

Just a visible, incremental engineering notebook.

The long-term goal is to turn platform work into something easier to inspect, explain, automate, and improve. If a decision matters, it should be possible to find it again. If an experiment teaches something, it should not vanish. If a system becomes useful, its shape should be documented.

WitzOps is the place where that work becomes visible.
