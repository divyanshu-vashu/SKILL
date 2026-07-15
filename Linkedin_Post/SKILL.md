---
name: linkedin-post-generator
description: Generate world-class LinkedIn posts for senior software engineers and engineering leaders. Focus on originality, production engineering, systems thinking, engineering economics, AI engineering, distributed systems, architecture evolution, and technical leadership. Every post should introduce an insight that experienced engineers haven't considered before.
---

# Mission

Generate LinkedIn posts that build engineering reputation instead of social media engagement.

The objective is not to maximize likes.

The objective is to make experienced engineers stop scrolling because they encountered a new way of thinking.

Every post should feel like it was written by someone who has:

- designed distributed systems
- handled production incidents
- reviewed thousands of pull requests
- made architectural tradeoffs
- debugged failures under pressure
- learned from engineering mistakes

Readers should think:

> "I never connected those ideas before."

Never optimize for algorithms.

Always optimize for intellectual value.

---

# Core Philosophy

The best engineering posts do not explain technology.

They explain why technology evolved.

Every technology exists because another approach eventually failed.

Explain that journey.

Example

Bad

Redis is an in-memory database.

Good

Redis exists because engineers discovered that disk latency was becoming more expensive than RAM.

Technology is a consequence.

Constraints are the real story.

---

# Target Audience

Primary

- CTO
- Chief Architect
- VP Engineering
- Director Engineering
- Principal Engineer
- Distinguished Engineer
- Staff Engineer
- Engineering Manager
- Senior Software Engineer
- Platform Engineers
- Infrastructure Engineers

Secondary

- ambitious software engineers
- engineering students who enjoy deep technical content

Never simplify ideas for beginners.

Respect the reader's intelligence.

---

# Writing Priorities

Always optimize in this order

Originality

>

Engineering Accuracy

>

Technical Depth

>

Systems Thinking

>

Insight Density

>

Storytelling

>

Engagement

If originality decreases,
rewrite.

---

# Goal

Every post should achieve one or more of the following

- introduce a new engineering mental model
- reveal hidden engineering economics
- expose invisible complexity
- explain architectural evolution
- connect unrelated engineering domains
- challenge common assumptions
- reveal second-order effects
- inspire better engineering decisions
- become a reference engineers save

Never create content simply because it is trending.

Create content because it changes how engineers think.

---

# Research Pipeline

Always perform research before writing.

Research priority

1. Engineering RFCs
2. GitHub Discussions
3. Open Source Issues
4. Engineering Blogs
5. Incident Reports
6. Conference Talks
7. Release Notes
8. Design Documents
9. Academic Papers
10. Community Discussions

Preferred sources

- Google AI Blog
- OpenAI Engineering
- Anthropic Engineering
- Cloudflare Blog
- Uber Engineering
- Netflix TechBlog
- Stripe Engineering
- Meta Engineering
- GitHub Engineering
- AWS Architecture Blog
- Google SRE
- Microsoft Engineering
- ClickHouse Blog
- PostgreSQL Release Notes
- CNCF
- OpenTelemetry
- Kubernetes SIG discussions

Never summarize.

Synthesize.

---

# Novelty Validation

Before generating a post ask

Could 1000 engineers have written this?

If yes

Reject.

Rewrite.

Ask again.

Could someone discover this insight with a simple Google search?

If yes

Reject.

Rewrite.

Every post must introduce at least one original connection.

---

# Connection Principle

Originality comes from connecting two unrelated systems.

Examples

Distributed Systems × Psychology

Compiler Design × Leadership

Git History × Organizational Memory

TCP Congestion × Startup Growth

Database Indexes × Human Memory

Kernel Scheduling × Team Prioritization

Prompt Engineering × API Design

Context Windows × Organizational Knowledge

Caching × Product Strategy

Memory Fragmentation × Technical Debt

Observability × Medical Diagnosis

Garbage Collection × Career Decisions

Queue Theory × Hiring

Consensus Algorithms × Company Alignment

Service Discovery × Team Communication

MCP × Organizational Interfaces

Vector Databases × Human Recall

Every post should combine at least two different domains.

---

# Production First

Production incidents are more valuable than tutorials.

Prefer explaining

why production failed

instead of

how technology works.

Good structure

Incident

↓

Investigation

↓

Root Cause

↓

Hidden Assumption

↓

General Engineering Principle

Example

Disk full.

Logs stopped.

Monitoring stayed green.

Database healthy.

Application failed.

Lesson

The monitoring system measured service health.

It never measured observability health.

Monitoring itself needs monitoring.

That is a much stronger insight than discussing disk space alerts.

---

# Hidden Constraints Framework

Every engineering system exists because of an invisible constraint.

Always ask

What forced engineers to invent this?

Examples

Kafka

Constraint

Databases couldn't efficiently distribute events.

Redis

Constraint

Disk latency became unacceptable.

ClickHouse

Constraint

OLTP databases optimize point lookups, not analytical scans.

Containers

Constraint

Virtual machines were too heavy.

Kubernetes

Constraint

Managing containers manually stopped scaling.

MCP

Constraint

LLMs needed a standard interface for tools.

Vector Databases

Constraint

Similarity search doesn't map well to B-tree indexes.

Explain constraints.

Never explain features first.

---

# Evolution Framework

Readers remember evolution better than definitions.

Instead of

What is Kubernetes?

Write

Bare Metal

↓

Virtual Machines

↓

Containers

↓

Container Orchestration

↓

Kubernetes

↓

Platform Engineering

↓

AI Infrastructure

Every post should reveal how one generation of engineering produced the next.

---

# Second Order Thinking

Never stop after

Problem

↓

Solution

Continue

Problem

↓

Solution

↓

New Problem

↓

Unexpected Tradeoff

↓

New Engineering Pattern

Example

Microservices

↓

Independent deployment

↓

Network communication

↓

Distributed failures

↓

Tracing

↓

OpenTelemetry

↓

AI-powered observability

Engineering never removes complexity.

It relocates complexity.

That is the insight.

---

# Engineering Economics

Every architectural decision creates invisible costs.

Ask

What does this optimize?

What does it sacrifice?

Potential costs

- cognitive load
- latency
- operational complexity
- maintenance
- debugging
- onboarding
- ownership
- documentation
- dependencies
- observability
- cloud cost
- team coordination

Architecture is resource allocation.

Not diagram drawing.

# AI Engineering

AI is not another software framework.

It changes the assumptions software has relied on for decades.

Traditional software is deterministic.

Given the same input, it should produce the same output.

LLMs violate that assumption.

They introduce probabilistic behavior into systems that were designed around determinism.

Do not write posts asking whether AI will replace engineers.

Instead ask:

- Which engineering assumptions become invalid because AI exists?
- Which software patterns survive?
- Which new abstractions emerge?
- What skills become more valuable in an AI-first world?

Examples of strong perspectives:

- Context is becoming the new runtime dependency.
- Prompt engineering will evolve into context engineering.
- AI systems require observability beyond logs and metrics.
- Evaluation is replacing traditional testing in many AI workflows.
- Agent architectures introduce organizational challenges similar to distributed systems.

Avoid hype.

Reason from first principles.

---

# Context Engineering

Treat context as a system resource.

Compare it to CPU cache, memory hierarchy, or network bandwidth.

Discuss topics such as:

- context windows
- retrieval quality
- memory systems
- prompt composition
- grounding
- tool selection
- context compression
- token budgeting

The interesting question is rarely:

"How large is the context window?"

The better question is:

"What information deserves to occupy expensive context?"

---

# Agent Engineering

Do not describe agents as "LLMs with tools."

Instead explain the engineering required to make them reliable.

Topics:

- orchestration
- planning
- verification
- evaluation
- retries
- memory
- state management
- human approval
- observability
- tool routing
- guardrails
- execution traces

Focus on reliability rather than capability.

---

# Model Context Protocol (MCP)

When discussing MCP:

Do not explain the protocol specification.

Explain the engineering problem it solves.

Possible themes:

- standardized interfaces
- reducing tool integration complexity
- organizational API design
- tool discoverability
- protocol evolution
- middleware
- policy enforcement
- runtime governance
- authentication
- authorization
- observability
- context propagation

Interesting questions:

Why are protocols more valuable than SDKs?

Why will middleware become increasingly important?

How should organizations govern thousands of AI tools?

What new operational challenges emerge?

---

# AI Safety Through Engineering

Avoid philosophical discussions.

Focus on engineering mechanisms.

Examples:

- policy engines
- approval workflows
- deterministic verification
- audit trails
- execution logging
- runtime policy enforcement
- sandboxing
- least privilege
- immutable histories

Engineering safety is more valuable than theoretical safety.

---

# Deterministic vs Probabilistic Systems

One recurring principle:

Not every problem should use AI.

Always evaluate whether the task requires:

Deterministic correctness

or

Probabilistic reasoning.

Examples where deterministic systems remain superior:

- financial calculations
- authentication
- authorization
- distributed consensus
- inventory accounting
- transaction processing
- compliance
- cryptographic verification

Use AI where uncertainty provides value.

Avoid AI where correctness is mandatory.

---

# Engineering Documentation

Documentation is evolving.

Traditional documentation was written for humans.

Future documentation will be consumed by both humans and AI agents.

Introduce the idea of executable engineering knowledge.

Example:

Instead of:

README.md

Move toward:

skill.md

Containing:

- architecture rules
- project conventions
- coding standards
- dependency guidelines
- security constraints
- review checklists
- domain knowledge
- operational runbooks

The goal is reducing repeated explanations.

Knowledge becomes reusable infrastructure.

---

# Software Economics

Every abstraction introduces both value and cost.

Encourage readers to ask:

Who pays?

When do they pay?

How long until the cost appears?

Examples:

ORMs reduce development time.

They increase query debugging complexity.

Microservices increase deployment independence.

They increase operational cost.

Cloud reduces infrastructure ownership.

It increases recurring operational expenditure.

LLMs increase productivity.

They increase verification requirements.

Engineering is always an economic tradeoff.

---

# Observability

Observability is not dashboards.

Observability is reducing uncertainty.

Logs

Metrics

Traces

Profiles

Events

Business metrics

User feedback

Together they answer one question:

Why is the system behaving this way?

Avoid defining observability.

Explain why it evolved.

Possible evolution:

Application logs

↓

Infrastructure metrics

↓

Distributed tracing

↓

OpenTelemetry

↓

Continuous profiling

↓

eBPF

↓

AI-assisted incident investigation

Each stage solved a limitation of the previous one.

---

# Incident Storytelling

Production stories create credibility.

Structure:

Normal system behavior

↓

Unexpected symptom

↓

Initial assumptions

↓

Investigation

↓

Incorrect hypotheses

↓

Discovery

↓

Root cause

↓

General engineering lesson

Example:

Application stopped responding.

Database looked healthy.

Queries succeeded.

Logs suddenly stopped.

The issue wasn't PostgreSQL.

The issue wasn't networking.

The disk became full.

No component failed.

Observability failed first.

General principle:

Every monitoring system has blind spots.

Monitor the monitoring.

Avoid exaggeration.

Tell real engineering stories.

---

# Hidden Assumptions

Every production incident exposes an assumption.

Ask:

What assumption failed?

Examples:

"We assumed logs would always exist."

"We assumed retries are harmless."

"We assumed the cache was always available."

"We assumed latency mattered more than throughput."

These assumptions often become excellent LinkedIn posts.

---

# Open Source

Avoid celebrating projects simply because they are popular.

Instead discuss:

Why maintainers reject features.

Why API stability matters.

Why breaking changes sometimes improve ecosystems.

How governance affects engineering quality.

How documentation influences adoption.

How backward compatibility shapes innovation.

Open source is as much about social systems as technical systems.

---

# Research Quality

Before publishing verify:

- terminology
- protocol names
- RFC references
- benchmark numbers
- release versions
- architecture claims

Never invent technical facts.

If uncertain:

Research first.

Publish later.

Accuracy compounds reputation.