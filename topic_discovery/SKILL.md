# engineering-topic-discovery â€” SKILL.md

---
name: engineering-topic-discovery
description: Research and rank technical content topics for senior engineers (Staff/Principal Engineers, EMs, Architects, SREs, Platform Engineers, CTOs) to write about â€” for LinkedIn, blogs, newsletters, or talks. Use this whenever the user asks for "topic ideas," "what should I write about," "content ideas," a "content calendar," help finding an "angle" on a technical subject, or wants to know what's trending/original/non-saturated in a specific engineering domain (distributed systems, platform engineering, SRE, AI infra, security, databases, etc.). Also trigger when the user gives you a category ("give me topics on Kubernetes") or a rough idea ("something about our migration") and wants it turned into validated, ranked, publication-ready topic candidates rather than a quick brainstorm list. Do not use this for writing the actual post/article â€” that's a separate task; this skill only discovers, researches, and ranks the topic itself.
---

# Engineering Topic Discovery

## Mission

Given a category, a rough idea, or a set of candidate topics, do what a sharp technical editor with real research resources would do: go find out what's actually happening in that space right now, generate topic candidates that are technically rigorous and *not* things everyone's already posted about, stress-test each one, and hand back a small ranked shortlist with the reasoning attached â€” not a brainstormed list of generic titles.

The bar for a topic to make the final list: a Staff or Principal Engineer should read the title and think "I hadn't thought about it that way" or "I need to read this" â€” not "I've seen this exact post fifty times."

## Core Principles

1. **Research before ideation, not after.** Don't generate topic titles from general knowledge and then go "check" them. Pull real, current material first â€” recent incidents, RFCs, changelogs, postmortems, conference talks, benchmark results â€” and let topics emerge from what's actually happening. Ideas grounded in a real source are categorically stronger than ideas grounded in a pattern-matched template.

2. **Original beats broad.** A topic that's obvious enough to generate without research is probably obvious enough that a thousand other engineers have already written it. Prioritize specific, defensible, sometimes contrarian angles over safe, general ones.

3. **Every topic should teach a reusable mental model**, not just report a fact. "We migrated to Kafka" is a fact. "Why event ordering guarantees are usually the wrong thing to optimize for" is a mental model. Push every candidate toward the latter.

4. **Evidence over speculation.** Prefer topics backed by something concrete â€” a production incident, a real migration, a benchmark, an RFC, a postmortem â€” over topics that are just "hot take" commentary with nothing underneath them.

5. **Timing matters as much as quality.** A great topic that's timeless has less urgency than a great topic that's timely *because something just changed* (a new release, a widely-discussed outage, a shift in the ecosystem). Note timeliness explicitly.

6. **Show your work.** The output isn't just a list â€” it's a ranked list with scores, source grounding, and a stated reason each topic survived the quality gates. The user should be able to see *why* a topic ranked where it did.

## Supported Input Modes

Detect which mode the user is in from their message; ask only if genuinely ambiguous.

- **Category mode** â€” user gives a domain or technology ("platform engineering", "Postgres internals", "LLM inference costs"). Cast a wide research net across that domain.
- **Topic mode** â€” user gives one or more specific topic ideas and wants them validated, sharpened, and scored, not replaced wholesale.
- **Seed mode** â€” user gives a rough, underspecified idea ("something about our migration," "I want to write about the outage last week"). Expand it into several concrete angles before researching.
- **Mixed mode** â€” a combination, e.g. a category plus a constraint ("Kubernetes topics, but not another 'why we moved off X' post").

Always confirm (briefly, inline â€” don't stop to ask unless truly ambiguous) the target audience level and platform if it changes what "good" looks like â€” a LinkedIn post and a conference talk have different bars for depth and length. Default assumption if unstated: a senior technical audience on LinkedIn or a technical blog.

## Research Workflow

Work through these stages in order. Don't skip the research stages to jump to ideation â€” that's the most common failure mode of this task.

```
1. Determine input mode (category / topic / seed / mixed)
2. Expand scope â€” list the sub-domains, adjacent technologies, and
   recent developments worth checking for this category
3. Collect fresh research (see Research Source Priority below)
4. Extract engineering signals â€” incidents, RFCs, benchmarks,
   postmortems, architecture decisions, changelogs, real debates
5. Identify what's actually trending vs. just recurring noise
5.5 Apply the Trend Detection Framework and classify every emerging signal.
6. Generate candidate topics grounded in what was found
7. Expand: for each strong candidate, find 1-2 related/adjacent angles
8. Check for cross-domain connections (topics that bridge two fields
   read as more original than single-domain topics)
9. Check each candidate against what's already saturated on LinkedIn/
   engineering blogs â€” discard or sharpen anything oversaturated
10. Score every surviving candidate (see references/scoring-and-ranking.md)
11. Rank and select the shortlist
12. Run the self-review quality gates on the finalists
13. Produce the final ranked report
```

For the full detail on stages 2â€“9 (how to expand scope, detect trends, detect saturation, find cross-domain angles), read `references/research-and-discovery.md` before starting a category-mode or seed-mode request â€” it has the concrete techniques and search patterns, not just the workflow labels.


## Cross-Domain Discovery Framework

For every shortlisted topic generate at least three unexpected intersections.

Examples:

Database × AI

Compiler × Security

Observability × Economics

Caching × Human Memory

Kernel Scheduling × Team Prioritization

Queue Theory × Psychology

Storage Engines × Organization Design

Rank each intersection by:

- Originality
- Technical validity
- Mental model quality
- Discussion potential

Prefer at least one cross-domain topic in the final shortlist.

## Research Source Priority

Search and pull from real, current sources â€” this skill lives or dies on whether the research underneath it is real. Prioritize, roughly in this order:

1. Primary engineering sources: postmortems/incident reports, RFCs and design docs, official changelogs and release notes, conference talks (recent, e.g. current-year conferences), engineering blogs from companies actually operating the systems in question.
2. Second-order but still credible: well-regarded independent engineering newsletters, GitHub issues/discussions on major projects showing real friction points, benchmark repositories.
3. Signal-of-discourse sources (use to check saturation and sentiment, not as primary evidence): what's actively being discussed on LinkedIn/HN/engineering Twitter right now, so you know what's already been said and what hasn't.

Weight recency heavily â€” something that changed in the last few weeks is worth more than a well-known but static fact, because timeliness is one of the scored dimensions. Don't fabricate or half-remember sources; if you can't verify a specific claim (a number, an incident, a quote) with a real search result, don't present it as fact â€” either search harder or soften it to a general trend statement.


## Trend Detection Framework

For every discovered topic classify it as:

- Emerging
- Accelerating
- Mature
- Saturated
- Declining

Determine this using:

- Recent releases
- RFCs
- Incident reports
- GitHub activity
- Conference talks
- Hiring trends
- Open-source adoption
- Company migrations

Reject trends driven purely by hype.

## Signal vs. Noise Filter

Before promoting a topic verify:

- Is this solving a real production problem?
- Is adoption increasing?
- Is this backed by engineering evidence?
- Is this merely marketing?
- Is discussion driven only by social media?
- Are multiple companies independently converging on this idea?

Discard hype-driven topics.


## Quality Gates (Self-Review Loop)

Before a topic appears in the final ranked output, it must be able to survive these questions. Run this explicitly, not implicitly â€” for each finalist, briefly check it against this list:

- Is this genuinely original, or a repackaged version of a post that's everywhere already?
- Does it teach a reusable mental model, not just report a fact?
- Is there real evidence from engineering practice underneath it (not just a vibe)?
- Has something changed recently enough to make this timely?
- Would a Staff/Principal Engineer actually stop scrolling for this?
- Can it spark real technical disagreement or discussion, not just nodding along?
- Is there a compelling, specific production story behind it (an incident, a number, a decision)?
- Does it connect more than one engineering discipline, where relevant?
- Would this still be worth reading a year from now â€” or is its value purely this week?

A topic that fails several of these should be cut or reworked, not included with a caveat. It's better to hand back four topics that all clear the bar than ten where six are filler.

For the full scoring rubric (numeric scoring engine, lifecycle classification, audience mapping, content longevity, confidence scoring) read `references/scoring-and-ranking.md`.

## Contrarian Angle Discovery

Ask:

- Which engineering assumption is now outdated?

- Which best practice fails at scale?

- Which optimization receives too much attention?

- Which abstraction hides important costs?

- Which "rule" should experienced engineers challenge?

Prefer evidence-backed contrarian perspectives.



## Output

Produce a ranked shortlist (typically 5â€“10 topics for category/seed mode; all submitted topics, re-ranked, for topic-validation mode). For each topic include:

- **Title** â€” the actual working title/angle, specific enough to write from directly
- **The mental model** â€” one sentence: what does this actually teach the reader
- **Why now** â€” the specific, real thing that makes this timely (cite what changed)
- **Evidence base** â€” what real source(s) ground this (incident, RFC, benchmark, etc.)
- **Audience fit** â€” which senior engineering roles this lands best with
- **Lifecycle stage** â€” Emerging / Growing / Mature / Saturated / Declining
- **Longevity** â€” Evergreen / Trend / News / Long-term Strategic
- **Series potential** â€” standalone, or could this seed a multi-part series
- **Score + one-line rationale** â€” see the scoring reference for the rubric

Close with a short **Research Backlog**: promising leads that came up during research but weren't strong enough (yet) to make the shortlist â€” things worth revisiting once more evidence exists. This is what turns a one-off run into a reusable content pipeline for the user.

Keep the actual written output scannable â€” this is a research report, not the scoring reference document. Don't dump the full rubric math into the user-facing answer; show the score and the one-line reason it landed there.

## Topic Gap Analysis

After producing the ranked shortlist, analyze the user's overall content portfolio.

Identify:

- Overrepresented domains
- Missing engineering disciplines
- Missing senior-level topics
- Missing systems knowledge
- Missing infrastructure topics

Recommend a balanced long-term publishing strategy.

Example:

Current Focus

✓ AI

✓ MCP

✓ Agents

Missing

• Platform Engineering

• Databases

• Reliability

• Networking

Recommendation

Reduce AI-only topics.

Increase systems and infrastructure content.

## Recommendation Engine

For each selected topic recommend one action:

- Publish immediately

- Monitor

- Research further

- Wait for adoption

- Pair with an incident

- Expand into a series

- Save for conference talk

- Build benchmark before publishing


## Failure Modes to Avoid

- **Ideation without research.** Producing a list of topic titles that read like they came from general knowledge of "what engineers write about" rather than from anything actually found this session. If you haven't run searches, you haven't done this task.
- **Breadth over depth.** Twenty generic topics is worse than six sharp ones. Cut ruthlessly.
- **Treating trending-on-social as the same thing as timely-and-real.** A topic that's viral because of hype isn't automatically a good topic â€” check whether there's a genuine engineering shift underneath the noise (see Signal vs. Noise Filter in the reference doc).
- **Skipping saturation checks.** A technically great topic that's been written 200 times this year on LinkedIn is not original, no matter how well it's grounded. Always check before finalizing.
- **Fabricating specificity.** Inventing a plausible-sounding incident, number, or company example to make a topic sound more grounded than the research actually supports. If it's not verified, say so or generalize the claim.
- **Ignoring the audience mismatch.** A deeply niche kernel-internals topic pitched as "great for engineering managers" (or vice versa) undermines the whole point of audience mapping.