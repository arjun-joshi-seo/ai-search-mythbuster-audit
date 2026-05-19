---
name: ai-search-mythbuster-audit
description: >
  Analyzes any website page (product, service, blog, homepage,
  landing page, or any other page type) against Google's official
  AI Optimization Guide and debunked myths (AEO/GEO/chunking/LLMS.txt),
  as well as broader AI search landscape standards
  (Perplexity, ChatGPT, Gemini, Copilot).
---

# AI Search Mythbuster Audit

Analyzes any website page (product, service, blog, homepage, landing page, or any other page type) against Google's official AI Optimization Guide and debunked myths (AEO/GEO/chunking/LLMS.txt), as well as broader AI search landscape standards (Perplexity, ChatGPT, Gemini, Copilot).

---

## Use This Skill When

USE THIS SKILL whenever a user wants to:

- Audit a page URL or pasted content for AI search visibility
- Check if a page follows Google's latest AI optimization guidelines
- Get an SEO/GEO audit report with issues, fixes, action plan, and page score
- Analyze product pages, service pages, blog posts, homepages, landing pages, or any web page
- Identify what's a myth vs. what actually matters for generative AI search
- Get optimized rewrites of page content (when explicitly requested)
- Bulk-analyze multiple pages in one session

Trigger this skill even when the user says:

- "check my page for AI SEO"
- "will Google's AI show my page"
- "audit this URL for GEO"
- "is my content optimized for AI search"
- "review my product page for AI visibility"

or any variation of wanting to know how a page performs for generative AI search features.

Responds in the user's language.

Assumes advanced SEO/GEO knowledge — no hand-holding on terminology.

---

# Input Handling

## Accepting Input

### URL Input

Use web_fetch to retrieve the page content.

Extract:

- title
- meta description
- H1–H3 structure
- body text
- image alt tags
- internal/external links
- any schema markup present

### Pasted Content

Analyze the raw text/HTML directly.

### Bulk Input

Multiple URLs or multiple content blocks — process each one individually, then produce a Bulk Summary table at the end.

### Page Type Detection

Identify page type automatically:

- product
- service
- blog/article
- homepage
- landing page
- other

Adjust audit lens accordingly.

See:

```txt
references/page-type-guidance.md
```

---

## If URL Fetch Fails

Inform the user the URL couldn't be fetched and ask them to paste the page content directly.

---

# Analysis Framework

Analyze every page across three pillars.

Read:

```txt
references/analysis-framework.md
```

for full criteria and scoring rubrics.

---

# Pillar 1 — Google AI Optimization Guide Compliance

Based directly on Google's official guide (May 2025).

Key areas:

- Content uniqueness & non-commodity status
- First-hand expertise signals (E-E-A-T)
- Content organization (headings, paragraphs, structure)
- Image/video presence and optimization
- Technical crawlability & indexability
- Page experience (CWV, mobile, latency)
- Duplicate content issues
- Local/ecommerce structured data (where applicable)

---

# Pillar 2 — Myth Audit (What NOT to Do)

Flag if the page shows evidence of practices Google has officially debunked:

- LLMS.txt or AI-specific machine-readable files
- Artificial "chunking" of content for AI
- Keyword stuffing / long-tail variation farming
- Inauthentic third-party "mention" seeking
- Over-reliance on structured data as an AI ranking lever
- Rewriting content specifically for AI phrasing patterns
- AEO/GEO as a discipline separate from foundational SEO

---

# Pillar 3 — Cross-Platform AI Search Visibility

Evaluate for:

- Perplexity
- ChatGPT Search / Bing
- Gemini
- Copilot

General AI citation likelihood:

- Extractability
- Quotability
- Original data/stats
- Citation readiness

---

# Scoring System

Score each pillar out of 10.

Produce an Overall AI Visibility Score out of 100.

## Weighting

| Pillar | Weight |
|---|---|
| Google compliance | 50 points |
| Myth/anti-pattern cleanliness | 20 points |
| Cross-platform AI visibility | 30 points |

---

# Score Bands

| Score | Grade | Meaning |
|---|---|---|
| 85–100 | A | Well-optimized for AI search |
| 70–84 | B | Solid foundation, minor gaps |
| 55–69 | C | Moderate issues, prioritize fixes |
| 40–54 | D | Significant gaps, needs rework |
| 0–39 | F | Critical failures, major overhaul needed |

---

# Output Format

## Single Page Audit

```md
## AI Visibility Audit — [Page Title / URL]

**Page Type**: [Detected type]
**Language**: [Detected language]

---

### Overall Score: [X/100] — Grade [A/B/C/D/F]

| Pillar | Score | Grade |
|--------|-------|-------|
| Google AI Optimization Compliance | X/50 | |
| Myth/Anti-Pattern Cleanliness | X/20 | |
| Cross-Platform AI Visibility | X/30 | |

---

### Pillar 1: Google AI Optimization Compliance [X/50]

#### ✅ What's Working

- [Specific positive finding with brief explanation]

#### ❌ Issues Found

For each issue:

- **Issue**: [Clear description]
- **Why it matters**: [Grounded in Google's guide]
- **Fix**: [Specific actionable recommendation]

---

### Pillar 2: Myth Audit [X/20]

#### Anti-patterns detected

- **[Anti-pattern name]**:
  [What was found on the page]
  → [Why this doesn't work per Google]

#### Clean

No debunked optimization practices detected.

---

### Pillar 3: Cross-Platform AI Visibility [X/30]

**Google AI Overviews**: [assessment]

**Perplexity**: [assessment]

**ChatGPT Search / Bing**: [assessment]

**Gemini**: [assessment]

**Copilot**: [assessment]

#### Key gaps for AI citation likelihood

- [Finding + fix]

---

### Priority Action Plan

#### 🔴 Critical (Do First)

1. [Action]

#### 🟡 Important (Do Next)

2. [Action]

#### 🟢 Nice to Have

3. [Action]

---

### Rewrite Offer

Want me to rewrite a specific section to address these issues?
Just say which section.
```

---

# Bulk Analysis Output

After individual audits, append:

```md
## Bulk Summary

| Page | Type | Score | Grade | Top Priority Issue |
|------|------|-------|-------|--------------------|
| [URL/name] | [type] | [X/100] | [A-F] | [Single most critical fix] |

**Recommended order of fixes across all pages**:
[prioritized list]
```

---

# Rewrite Mode

When the user explicitly asks for optimized content:

- Produce the rewritten version
- Add a "Changes Made" section
- Explain each edit and which audit issue it addresses
- Flag issues that cannot be fixed through rewriting alone

Do NOT proactively rewrite content unless asked.

---

# Multilingual Behavior

- Detect the language of the page content
- Respond in the same language the user wrote in
- If user writes in English but page is in another language, respond in English but note the page language
- Apply the same audit framework regardless of language

---

# Page-Type Specific Lenses

See:

```txt
references/page-type-guidance.md
```

## Product Pages

- Unique product descriptions
- Product schema
- Image quality
- Review signals
- Merchant Center alignment

## Service Pages

- E-E-A-T signals
- Geographic relevance
- First-hand expertise
- Case studies

## Blog/Articles

- Unique POV
- Author authority
- Original research/data
- Content depth

## Homepages

- Brand authority signals
- Clear content hierarchy
- Crawl efficiency

## Landing Pages

- Content substance
- Crawlability
- Snippet eligibility

---

# Key Principles

- AEO and GEO are not separate disciplines from foundational SEO
- Indexability is prerequisite
- Content substance outweighs AI tricks
- Never hallucinate scores
- Only flag issues identifiable from provided content

---

# Reference Files

```txt
references/analysis-framework.md
references/page-type-guidance.md
references/myth-registry.md
```
