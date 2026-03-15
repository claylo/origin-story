# origin-story

> The phase-zero plugin that asks whether this idea is your radioactive spider or just another bug bite.

——

## The Origin Story

In comics, the origin story isn’t one moment — it’s a sequence. For Spider-Man:

|Moment                |What Happens                                         |
|-———————|——————————————————|
|Spider bite           |The idea strikes — you can’t control this            |
|Wrestling match       |“Can I do something with this?” — testing the powers |
|Sidestepping the thief|“What’s the easy path?” — the choice that defines you|
|Uncle Ben’s death     |“Does this matter enough to commit?” — the calling   |
|Becoming Spider-Man   |**Ship it** — the hero’s journey begins              |

Skip any phase and you’re not Spider-Man. You’re just a guy who got bit.

**origin-story** walks you through the full sequence. Not just “is this viable?” but “is this *yours*?”

When the answer is yes, hand off to superpowers. When it’s no, you’ve spent 20-30 minutes instead of 3 months.

——

## The Problem

Developers, indie hackers, and builders have ideas constantly. Sometimes dry spells, sometimes a flood. The pattern is always the same:

1. Idea strikes
1. Jump straight to code
1. Weeks or months later: “wait, does this already exist?” or “who would pay for this?” or “why did I build this?”

The gap is **phase zero** — the 20-30 minutes that should happen *before* opening the editor. The goal:

- **Build / Don’t Build** recommendation with detailed reasoning
- If “build”: a spec detailed enough to hand off to implementation workflows
- If “don’t build”: clear reasoning so you can let go without regret

This isn’t about killing ideas. It’s about *choosing* the right ones.

——

## What Exists (And Why It’s Not This)

### Startup Validators

Tools like ValidatorAI, IdeaProof, DimeADozen, FounderTool.ai all exist. They share common traits:

- **VC goggles**: TAM/SAM/SOM, investor decks, “how big can this get?”
- **Output is pitch decks**, not implementation specs
- **Assume you’re building a startup** to raise money, not a tool to make a living

They ask the wrong questions for bootstrappers and indie builders.

### Developer Brainstorming Tools

Superpowers (obra/superpowers) is excellent. But it:

- **Assumes you’ve already decided to build**
- Starts at feature brainstorming, not viability
- No market research, no “does this exist?” check
- No monetization analysis

These two categories exist on separate islands. Nobody bridges “should I build?” with “here’s how to build it.”

**origin-story is that bridge.**

——

## The Reframe: VC vs. Bootstrapper

The existing tools optimize for the wrong thing.

|VC Validator Asks       |origin-story Asks                             |
|————————|-———————————————|
|Total Addressable Market|Who’s *already paying* for something adjacent?|
|Competitive moat        |Can I charge from day 1?                      |
|Growth trajectory       |Realistic revenue ceiling for solo/small team?|
|Investor-ready deck     |Pricing model that doesn’t require scale      |
|“How big can this get?” |“Can this make $10k-$50k/mo? How?”            |

**The “does this exist?” question gets a crucial follow-up:** “…and are they leaving money on the table I could pick up?”

### Monetization Taxonomy

Not all revenue is the same. The tool should explore:

- Open source + paid support/hosting
- Freemium SaaS
- One-time purchase / lifetime deal
- Dual licensing
- Productized service wrapper
- “Pay what you want” with anchoring
- License to vendors (sell to the platform, not the users)

——

## The Jobs/Ive Principle

> “You can’t build what users tell you they want. You have to envision what they need — which is often a couple of leaps away from what they’d tell you if you asked them.”

This is the **critical differentiator** that none of the existing tools address.

Most validation stops at:

- “Does this exist?” ✓
- “What do users say they want?” ✓

But Jobs/Ive-style thinking requires:

- Synthesizing *unstated* needs from adjacent frustrations
- Recognizing behaviors and workarounds people don’t identify as problems
- Making the leap from “what they’d ask for” to “what they actually need”

**This is its own phase** — not just research, but creative synthesis. The tool must facilitate this leap, not skip it.

### Prompts for the Leap

- “What are people doing *instead* of this, and why is that painful?”
- “What would they never think to ask for, but would love if it existed?”
- “What’s the friction they’ve normalized?”
- “What’s the behavior that signals unmet need?”
- “If this existed and worked perfectly, what would change?”

——

## The Workflow

### Phase 1: The Spider Bite (Idea Capture)

Capture the raw idea. What struck you? Don’t refine it yet — just get it down.

```yaml
inputs:
  raw_idea: string
  context: “what prompted this?”
  initial_excitement: “what’s compelling about it?”
```

### Phase 2: The Wrestling Match (Landscape)

“Can I do something with this?” — testing against reality.

**Goal:** Find existing solutions, pricing models, user sentiment, gaps.

```yaml
research:
  existing_solutions:
    - name: string
      pricing: string
      sentiment: “loved | tolerated | hated”
      gaps: [string]
  
  pricing_models_in_space: [string]
  
  sentiment_signals:
    complaints: [string]
    workarounds: [string]
    requests: [string]
  
  competitive_density: “empty | sparse | crowded | saturated”
```

**Key questions:**

- Does this exist?
- If yes: What do people love/hate about existing solutions?
- If yes: What’s overpriced? Underserved? Missing?
- If no: Why not? (Might be a bad sign, might be opportunity)

### Phase 3: Sidestepping the Thief (Monetization & Fit)

“What’s the path to money, and does it fit who I am?”

**Goal:** Identify realistic revenue paths and filter by personal constraints.

```yaml
monetization:
  revenue_models:
    - model: string
      price_point: string
      who_pays: string
      day_one_viable: bool
  
  ceiling_estimate: “lifestyle | small business | scale potential”
  
  comparable_products:
    - name: string
      pricing: string
      evidence: “how we know they make money”

sales_motion_fit:
  requires_enterprise_sales: bool
  self_serve_viable: bool
  seo_surface_area: “what would people google?”
  word_of_mouth_potential: string
  name_stickiness: string
  time_to_trying: “minutes from discovery to running it”
```

**The Sales Motion Filter:**

Not all revenue paths work for all people. The best idea is worthless if the path to money requires being someone you’re not.

|Motion             |Questions                                                 |
|-——————|-———————————————————|
|Enterprise outbound|Can you do months of pipeline, SDRs, grinding?            |
|Self-serve SaaS    |Can you build the “2am discovery → trying in 5min” funnel?|
|Open source → paid |Can you build community?                                  |
|One-time purchase  |Can you handle burst marketing?                           |
|License to vendors |Can you get in the room with 3-4 decision makers?         |

**What Sells to Nerds:**

- 2am discovery → trying it in 5 minutes (self-serve is everything)
- SEO (nerds google their problems)
- Word of mouth (nerds tell nerds)
- Catchy names (nerds remember and share)
- Good docs, good DX (just *works*)

### Phase 4: Uncle Ben’s Death (The Calling)

“Does this matter enough to commit?”

**Goal:** The Jobs/Ive synthesis — finding the unstated need, making the creative leap.

```yaml
synthesis:
  unstated_needs:
    - observation: “what people do/say”
      unspoken: “what this reveals they actually need”
  
  normalized_friction: “pain people don’t even notice anymore”
  
  the_leap: “the insight that connects the dots”
  
  why_now: “what changed that makes this possible/necessary?”
  
  why_you: “what makes you suited to build this?”
```

**This is where the magic happens or doesn’t.** The tool facilitates the creative leap, not just research aggregation.

### Phase 5: The Verdict

**Goal:** Build / Don’t Build decision with detailed reasoning.

```yaml
verdict:
  decision: “build | don’t build | investigate further”
  confidence: “high | medium | low”
  
  reasoning:
    for_building:
      - string
    against_building:
      - string
    uncertainties:
      - string
  
  # If don’t build
  why_not:
    primary: string
    secondary: [string]
    what_would_change_this: string
  
  # If build
  next_steps:
    immediate: [string]
    before_code: [string]
```

### Phase 6: Becoming Spider-Man (Spec Handoff)

**Conditional on verdict = “build”**

**Goal:** Produce a spec detailed enough to hand off to superpowers or similar.

```yaml
spec:
  one_sentence: string
  
  core_value_prop: string
  
  who_is_this_for:
    primary: string
    secondary: [string]
  
  what_it_does:
    must_have: [string]
    nice_to_have: [string]
    not_this: [string]
  
  how_they_find_it:
    seo_keywords: [string]
    communities: [string]
    word_of_mouth_trigger: string
  
  revenue_model:
    primary: string
    pricing: string
    day_one_plan: string
  
  mvp_scope:
    what_ships_first: string
    what_waits: [string]
    success_signal: string
  
  handoff_to: “superpowers:brainstorm”
```

——

## The Calibration Layer

### The Problem: Systematic Bias

Some builders have a known, systematic bias toward underestimating willingness to pay. Symptoms:

- “Why would anyone pay for this? They could just build it themselves.”
- Personally pays for tools all the time, but can’t imagine others doing the same
- Sees solutions so clearly that they seem obvious, therefore “worthless”
- The curse of knowledge: can’t unsee what you know

**This bias is noise, not signal.** The tool must compensate.

### The Mashery Lesson

> “I kept asking ‘why would ANYONE pay $2,500/month for this? Why wouldn’t they just fucking build it themselves and be done?’ And then we made a lot of money.”

The curse of knowledge isn’t just “I could build this myself” — it’s “this is so obvious, surely no one would pay for it.”

But obvious to you ≠ obvious to the market.

People stuck in the problem don’t see the fix. They’d gladly pay someone to make the pain go away.

### Compensation Mechanism

The tool actively counterweights this bias:

```yaml
reality_check:
  # Find evidence, not opinions
  comparable_products_with_revenue:
    - name: string
      pricing: string
      evidence: “customers, funding, revenue signals”
  
  people_already_paying_for_adjacent:
    - what: string
      price: string
      who_pays: string
  
  # Capture the gut check but flag it
  gut_check: string
  gut_check_reliability: “calibrated | historically_pessimistic | historically_optimistic”
  
  # The self-test
  would_you_pay: bool
  at_what_price: string
  
  # Adjusted signal
  adjusted_assessment: string
```

### The Self-Check Question

> “Would *you* pay for this? At what price?”

Your own purchasing behavior is more reliable than your predictions about others. If the answer is “yes, I’d pay $X for this” — that’s actual signal.

——

## Why MCP Server

### The Orchestration Problem

The core issue with prompt-based discipline (like skills/SKILL.md files):

|Approach          |Reliability                                             |
|——————|———————————————————|
|Skills/SKILL.md   |Variable — loads instructions, *trusts* Claude to follow|
|Prompt engineering|Variable — sophisticated suggestions, still skippable   |
|**MCP server**    |Deterministic — **code enforces the state machine**     |

Superpowers works by “asking Claude nicely.” Claude sometimes decides to skip ahead. Skills are useful but hit a reliability ceiling.

### The MCP Advantage

An MCP server **enforces the workflow** rather than suggesting it:

```
User: “evaluate this idea: offline-first bookmark manager”

Server response:
  → Runs phase 1 (landscape research)
  → Returns: “Phase 1 complete. Found 7 existing tools.
              Call `proceed_to_phase_2` to continue or
              `get_landscape_details` to dive deeper.”
```

Claude *can’t* skip to the verdict because the server won’t expose that tool until prerequisites are met. The state machine lives in code, not in Claude’s context window.

### Benefits

1. **Reliability** — workflow progression is deterministic
1. **Portability** — same server works with Claude.ai, Claude Code, ChatGPT
1. **Hybrid potential** — also expose a skill for discoverability
1. **State management** — tracks progress, can resume, handles interruptions
1. **Output control** — server owns structured format; templates render it

### Tool Surface

```
start_evaluation(idea: string) → evaluation_id
get_status(eval_id) → current_phase, completion_state

# Phase 1: Landscape (Spider Bite → Wrestling Match)
run_landscape_research(eval_id) → triggers research
get_landscape_results(eval_id) → competitors, pricing, sentiment

# Phase 2: Monetization & Fit (Sidestepping the Thief)
run_monetization_analysis(eval_id) → triggers analysis
get_monetization_results(eval_id) → revenue_models, ceiling, fit

# Phase 3: Synthesis (Uncle Ben)
run_synthesis(eval_id) → triggers Jobs/Ive leap
get_synthesis_results(eval_id) → unstated_needs, the_leap

# Phase 4: Verdict
generate_verdict(eval_id) → build/don’t build + reasoning

# Phase 5: Spec (conditional on verdict=build)
generate_spec(eval_id) → handoff-ready design doc

# Output
export(eval_id, format: “yaml” | “json” | “markdown” | “typst”)
```

The server is the **“adult in the room”** — Claude provides research and synthesis intelligence, but the server keeps the process on track.

——

## Output Formats

The workflow produces a canonical structured representation. Templates render to whatever format is needed:

- **YAML** — raw structured data
- **YAML + schema** — validated against a JSON schema
- **Markdown** — human-readable report
- **Typst PDF** — polished document
- **JSON** — for programmatic consumption

The format is chosen at export time, not baked into the workflow.

——

## Integration with Superpowers

origin-story is **phase zero**:

```
idea → [origin-story] → build? 
                          ↓
                         yes → /superpowers:brainstorm
                          ↓
                         /superpowers:write-plan
                          ↓
                         /superpowers:execute-plan
```

When origin-story says “build,” the spec it produces is designed to feed directly into superpowers’ brainstorming phase. The handoff should be seamless.

When origin-story says “don’t build,” you’ve spent 20-30 minutes instead of weeks or months. You can let go cleanly and move to the next idea.

——

## The Spider-Man Test

At the end of the workflow, ask:

> Is this idea your radioactive spider — the thing that transforms you?
> 
> Or is it just another bug bite?

Not every idea is your origin story. The ones that are deserve your full commitment. The ones that aren’t deserve a clean “no” so you can find the one that is.

——

## Research Backend

The research phases need web search. Rather than hardcoding a single provider, origin-story uses a pluggable backend with graceful fallback.

### Architecture

```yaml
research_backend:
  default: claude_web_search
  
  enhanced:
    - provider: perplexity
      env_key: PERPLEXITY_API_KEY
      models:
        fast: sonar          # quick factual lookups
        deep: sonar-pro      # synthesis, sentiment, deep research
    
    - provider: tavily
      env_key: TAVILY_API_KEY
      
    - provider: exa
      env_key: EXA_API_KEY
  
  selection: “best available”  # use enhanced if key present, else default
```

### Behavior

1. On startup, check which API keys are present in environment
1. Use the best available backend for each query type
1. Fall back gracefully if a provider fails
1. Never require an external key — Claude’s native search is always the baseline

### Query Routing

Different query types might benefit from different backends:

|Query Type                   |Best Backend        |Fallback                 |
|——————————|———————|-————————|
|“Does X exist?”              |Any                 |claude_web_search        |
|Competitor pricing           |Perplexity sonar    |claude_web_search        |
|Sentiment mining (Reddit, HN)|Perplexity sonar-pro|claude_web_search + fetch|
|Revenue evidence             |Perplexity sonar-pro|claude_web_search        |
|Deep landscape scan          |Exa or Perplexity   |claude_web_search        |

### Why This Matters

Without enhanced backend:

```
web_search → 10 results with snippets
fetch each → 10 pages of raw content
Claude synthesizes → burns tokens on HTML/noise
```

With Perplexity/Tavily:

```
structured query → pre-synthesized answer with citations
(optionally) fetch specific citations for verification
```

Better signal-to-noise. Fewer tokens. Faster results.

### Cost Consideration

Enhanced backends aren’t free (~$5/1000 queries for Perplexity sonar). But for a 20-30 minute workflow that saves you from building the wrong thing for 3 months? That’s lunch money.

Users who want the enhancement bring their own keys. Users who don’t still get a working tool.

——

## Open Questions

1. **Where does the AI run?** MCP server calls Claude API internally? Or server structures/enforces while client-side Claude does the thinking?
1. **Persistence** — where do evaluations live? SQLite? Flat files? Git-tracked YAML?
1. **The synthesis phase** — how to structure prompts that actually facilitate the creative leap vs. generating plausible-sounding filler?
1. **Calibration customization** — how do users indicate their own biases so the tool can compensate?
1. **Batch mode** — how to efficiently triage a backlog of 30 ideas?

——

## Summary

**origin-story** is the phase-zero plugin that answers “should I build this?” before superpowers answers “how do I build this?”

It walks through the full origin sequence:

- Spider bite (idea capture)
- Wrestling match (landscape research)
- Sidestepping the thief (monetization & fit)
- Uncle Ben’s death (the Jobs/Ive leap)
- Becoming Spider-Man (spec handoff)

Implemented as an MCP server for reliability — code enforces the workflow, not prompt suggestions.

Outputs structured data that renders to multiple formats.

Includes a calibration layer to compensate for systematic biases in evaluating ideas.

When it says “build,” you have confidence and a spec.
When it says “don’t build,” you have clarity and closure.

Either way, you’ve spent 20-30 minutes instead of 3 months building the wrong thing.