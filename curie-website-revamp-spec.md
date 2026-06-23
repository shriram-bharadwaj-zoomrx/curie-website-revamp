# Curie.md Website Redesign — Design Specification

**Version:** 1.0  
**Date:** June 2025  
**Prepared by:** Design  
**Status:** For Review  

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [What Was Not Changed](#2-what-was-not-changed)
3. [Design Principles](#3-design-principles)
4. [Typography System](#4-typography-system)
5. [Navigation & Information Architecture](#5-navigation--information-architecture)
6. [Homepage — Direction A (Chronicle)](#6-homepage--direction-a-chronicle)
7. [Briefs Page](#7-briefs-page)
8. [AI Solutions Page](#8-ai-solutions-page)
9. [Games Page](#9-games-page)
10. [Podcasts Page](#10-podcasts-page)
11. [Editorial Page](#11-editorial-page)
12. [Newsletter Page](#12-newsletter-page)
13. [Brief Detail Panel](#13-brief-detail-panel)
14. [SEO Improvements](#14-seo-improvements)
15. [AEO — AI Engine Optimization](#15-aeo--ai-engine-optimization)
16. [Trust & E-E-A-T Signals](#16-trust--e-e-a-t-signals)
17. [Responsive Design](#17-responsive-design)
18. [Future Enhancements](#18-future-enhancements)

---

## 1. Executive Summary

Curie is a free digital-media platform for verified healthcare professionals (HCPs) — delivering 100-word medical briefs, curated podcasts, brain games, and free AI clinical tools.

The core challenge this redesign addresses: **most Curie users arrive cold from search engines and AI tools (Perplexity, ChatGPT, Google SGE) without any prior brand context.** The existing design leads with a rotating carousel — a visually engaging element that simultaneously hides the most important information from both cold human visitors and search crawlers.

This document specifies every change made to the design, the evidence-based reasoning behind each decision, and future enhancements that would compound the improvements.

---

## 2. What Was Not Changed

To establish a clear boundary for this redesign:

| Element | Status | Reason |
|---|---|---|
| Brand colors (dark indigo `#121228`, purple `#8b5cf6`, teal `#50e3c2`, pink `#ff4f8b`) | **Unchanged** | Established brand identity — HCPs have seen it; changing would cause recognition loss |
| Curie sparkle logo mark | **Unchanged** | Distinct and ownable; no reason to replace |
| Content strategy (briefs, podcasts, games, AI tools) | **Unchanged** | The content mix is the product — this is a design spec, not a product spec |
| Side navigation layout (icon sidebar on desktop) | **Preserved** | It works; HCPs have learned the pattern |
| Core feature set | **Unchanged** | Every feature from the existing site is present in the redesign |

---

## 3. Design Principles

Every change in this redesign is anchored to four principles, listed in priority order.

### 3.1 SEO-First Rendering
**Why it matters:** Curie's primary growth vector is organic discovery — HCPs searching for clinical terms, trial results, or medical tools. Google's crawler evaluates content in the first 100KB of the rendered DOM. Any content hidden behind JavaScript execution or user interaction is de-prioritized or ignored entirely.

**Implication:** The page must render its most important content in visible, crawlable HTML above the fold — with no dependency on user interaction.

### 3.2 AEO — AI Engine Optimization
**Why it matters:** A growing share of Curie's target audience finds information through AI tools (ChatGPT, Perplexity, Claude, Google AI Overviews). These systems cite content by extracting text from crawled pages. Content that is structured as factual statements with named medical entities (drug names, trial names, ICD codes, statistics) is significantly more likely to be cited.

**Implication:** Every page must contain crawlable paragraph text that reads as a factual description, not just UI labels and card titles.

### 3.3 Cold-Visitor Clarity
**Why it matters:** An HCP arriving from a search result for "tirzepatide cardiovascular trial" or "free prior auth letter generator" has no prior Curie context. They have approximately 3 seconds to determine if they are in the right place. If they can't answer "what is this?" and "is this for me?" within that window, they leave.

**Implication:** The value proposition must be the first thing on every page — not a carousel, not a hero image, not a tagline.

### 3.4 Clinical Authority
**Why it matters:** HCPs are trained skeptics. They evaluate information sources with the same critical framework they apply to clinical evidence. A platform that looks like a consumer app loses credibility before any content is read. The design must signal peer-level authority — the aesthetic language of journals, not of social apps.

**Implication:** Typography, spacing, and visual restraint must communicate institutional rigor, not marketing energy.

---

## 4. Typography System

### 4.1 Previous System
**Manrope** for all text — headings, body, UI.

### 4.2 New System
- **Lora** — display serif, for all H1/H2 headlines and section titles
- **Plus Jakarta Sans** — sans-serif, for all body text, UI labels, navigation, and metadata

### 4.3 Why This Change

**Why replace Manrope for headlines?**  
Manrope is a geometric sans-serif — clean and modern, but neutral. It reads equally well on a food delivery app or a medical platform. It carries no inherent domain authority signal. For cold HCP visitors, the first typographic impression should say "I'm in the right place — this is serious clinical content."

Serif typefaces have a century-long association with medical and academic publishing — NEJM, Lancet, JAMA, and every peer-reviewed journal uses a serif for display. When an HCP sees a serif headline on a medical platform, their brain maps it to that trusted category before they read a single word.

**Why Lora specifically?**  
Lora was evaluated against four alternatives:

| Font | Used by | Assessment |
|---|---|---|
| Playfair Display | Financial Times, New Yorker | Too luxury/lifestyle; thin strokes can feel fashion-adjacent |
| Lora | BBC News, The Atlantic, Medium | **Best balance** — authoritative without being stiff; excellent screen rendering |
| Libre Baskerville | Academic journals, Harvard | Most clinical feel; slightly heavy for large display sizes |
| Cormorant Garamond | Lancet print, luxury brands | Beautiful but too thin for dark backgrounds at display size |

Lora's moderate contrast between thick and thin strokes, its excellent OpenType rendering on screens, and its established use by trusted news publishers made it the optimal choice for a clinical media platform.

**Why keep Plus Jakarta Sans for UI?**  
The body and UI text should not compete with the headline serif. Plus Jakarta Sans is a workhorse — highly legible at 11-13px (the sizes used in brief card metadata), with excellent tabular numeral support for statistics and dates. It reads as modern and product-grade without the app-store genericness of Inter or the marketing energy of Circular.

**Why NOT use a serif throughout?**  
Reading long-form body text in a serif on a screen (at 13-14px) increases cognitive load compared to a well-designed sans-serif. The serif is reserved for display headlines where it signals authority. The body text uses the sans-serif for maximum reading efficiency — important for HCPs who are already time-constrained.

---

## 5. Navigation & Information Architecture

### 5.1 Desktop: Icon Sidebar (68px)

**Preserved from existing design.** No change to the navigation structure.

**Why preserve it?**  
The left icon sidebar is a well-established pattern for multi-section web apps (Slack, Linear, Figma, Notion). HCPs who use Curie regularly have already built muscle memory for this pattern. Changing it would create unnecessary re-learning friction with no corresponding user benefit.

**Changes made:**
- Active state uses a subtle purple pill background (`rgba(139,92,246,0.2)`) with a matching border — more polished than the existing approach
- Inactive icon opacity reduced to `rgba(255,255,255,0.35)` — creates a clearer active/inactive hierarchy
- Profile icon moved to the bottom — consistent with the convention used by Figma, Linear, and Slack

### 5.2 Navigation Order

```
Home → Briefs → Games → Podcasts → Editorial → Newsletter → AI Solutions
```

**Why this order?**  
Ordered by visit frequency and content freshness, descending. Briefs and Games are daily-use features; Editorial and Newsletter are weekly. AI Solutions is a utility — used situationally, not daily. Users scan top-to-bottom, so the highest-frequency actions should be closest to the logo.

**Why AI Solutions is last:**  
It is a high-value but low-frequency utility. Physicians generate prior auth letters when they need to — not as a daily habit. Placing it last does not diminish it; there is a separate AI Tools teaser strip on the homepage that routes high-intent visitors directly.

### 5.3 Mobile Navigation

**Top bar:** Logo left, page title center, Sign In right  
**Bottom tab bar:** Home, Briefs, Games, Podcasts, AI Tools (5 items)

**Why a bottom tab bar on mobile?**  
Thumb-reachability. On a 6-inch phone screen, the top of the screen requires a stretch gesture. The bottom of the screen is within natural thumb range. Medical apps used during clinical workflow (often one-handed between patients) must minimize the effort of navigation.

**Why only 5 items in the bottom bar?**  
More than 5 items in a bottom tab bar creates labels that are too small to read at a glance. Editorial and Newsletter are lower-frequency use cases; they are accessible via the hamburger menu or desktop sidebar but not prioritized in the mobile bottom bar.

---

## 6. Homepage — Direction A (Chronicle)

### 6.1 The Core Problem: The Carousel

**Existing design:** The homepage opens with a rotating hero carousel cycling through mixed content (a podcast, a brief, a game) with image-heavy cards and minimal text.

**Problems with this approach:**

1. **SEO failure:** Search engines see `<div class="home-banner">` with dynamic content. The H1 — the most important SEO signal on any page — is buried inside a JavaScript-rendered carousel item. Google may not index it. If it does, it sees different content on each crawl depending on which carousel item happens to be active.

2. **AEO failure:** AI engines cannot cite a carousel. They need stable, paragraph-form text to extract and attribute. A rotating carousel produces no quotable, citable content.

3. **Cold visitor failure:** An HCP arriving from a Google search for "medical podcasts for doctors" lands on a full-screen image of a podcast episode they've never heard of, with no explanation of what Curie is, why it exists, or whether it's for them. There is no value proposition above the fold.

4. **Cognitive load:** A carousel forces visitors to wait or interact to understand the full range of what Curie offers. In UX research, carousels consistently show low interaction rates — users rarely click past the first item.

### 6.2 Hero Section — New Design

**Layout:** Two-column split — value proposition left (60%), featured brief card right (40%)

**Left column contents:**
- Eyebrow badge: "Free for all healthcare professionals" (immediate trust signal)
- H1: "The medical platform built for busy physicians" (keyword-rich, visible above fold)
- Body paragraph: Names all four content types with the word "HCP" present
- Two CTAs: Primary (Explore Briefs) and Secondary (Download App)
- Trust strip: 100K+ HCPs · Free Forever · Updated Daily

**Why a two-column split instead of a carousel?**  
The left column answers the cold visitor's question ("what is this?") and the right column shows concrete content ("here's what you get"). Both are visible simultaneously, with no interaction required. This is the same pattern used by Notion, Linear, and every high-converting SaaS homepage.

**Why is the H1 exactly "The medical platform built for busy physicians"?**  
This headline is constructed for both human impact and SEO value:
- "medical platform" — matches search intent for product discovery
- "built for busy physicians" — names the audience, qualifying visitors self-select
- The Lora italic on the second line creates visual contrast without needing an image

**Why keep the featured brief card on the right?**  
It demonstrates the product immediately — showing what a brief looks like before the visitor scrolls. A visitor who reads "Tirzepatide Cuts Cardiovascular Events 20%" understands the content quality and specificity of Curie better than any description could convey.

**Why the trust strip with 100K+ HCPs, Free Forever, Updated Daily?**  
Three of the biggest objections a cold HCP visitor has are: "Is this worth my time?" (100K+ HCPs = proven community), "Is this going to cost me?" (Free Forever = no barrier), "Is this current?" (Updated Daily = yes). Addressing all three objections above the fold eliminates the need to scroll to find answers.

### 6.3 Today's Briefs — 3-Column Grid

**Why 3 columns?**  
Desktop screen at 1280px with a 68px sidebar leaves approximately 1200px of content width. Three cards at equal width (~360px each) with gutters is the optimal balance between density and readability. Two columns would leave cards too wide; four columns would make card text too small.

**Why show summary text in cards?**  
The existing brief cards show only a title and a source tag. The redesigned cards show a 2-line summary preview. This change serves three purposes:
1. **SEO:** Card summary text is crawlable — "pCR 24.3% vs 15.6%", "KEYNOTE-756", "HR 0.69" are the exact terms HCPs search for. These become indexed content.
2. **HCP trust:** A physician can assess relevance from the summary without clicking. This reduces frustration for HCPs who have very limited time.
3. **AEO:** AI engines extract and cite the summary text directly when answering queries like "what did KEYNOTE-756 show?"

**Why the specialty color-coding?**  
Color-coded specialty tags (red for Oncology, blue for Cardiology, green for Nephrology, etc.) allow HCPs to instantly scan for their specialty without reading. Eye-tracking research consistently shows that color is processed pre-attentively — faster than text. For a physician scanning a page between patients, this reduces time-to-relevant-content.

### 6.4 Podcasts Section

**Why show podcasts on the homepage?**  
Podcasts are the second-highest content category by user engagement. Showing 2 podcast cards below briefs reinforces the platform's range without overwhelming the page.

**Why only 2 cards?**  
The homepage is a discovery surface, not a listing page. Two cards communicate "there are podcasts here" and route interested users to `/podcasts`. More than two would shift the homepage from discovery to consumption.

### 6.5 Games Section

**Why show games on the homepage?**  
Games are a daily-habit driver — a physician who plays Connections every morning is likely to also read briefs. The games section on the homepage serves as a retention hook for users who arrived for a brief but leave with an additional daily habit.

**Why 3 tiles instead of a single game spotlight?**  
Showing all 3 games (Connections, Pinpoint, Strands) gives visitors a full picture of the offering. A physician who doesn't enjoy word puzzles might love the diagnostic reasoning of Pinpoint. Showing all 3 maximizes the chance of a match.

### 6.6 AI Tools Teaser Strip

**Why a teaser strip instead of a nav item only?**  
The AI Tools nav item is at the bottom of the sidebar — less visible than Home or Briefs. The teaser strip on the homepage ensures that every visitor sees the free AI tools value proposition, even if they never click the nav item. The strip includes specific tool names ("Prior Auth Scribe", "Referral Letters") because those are high-intent search terms — a physician searching for "free prior auth generator" who lands on the homepage will see the strip and click through.

---

## 7. Briefs Page

### 7.1 SEO Header

**Change:** Added an H1 heading and descriptive paragraph at the top of the Briefs page.

**Previous state:** No visible H1 on the Briefs page. The page title existed only in the `<title>` meta tag.

**Why add an H1?**  
H1 is the single highest-weight on-page SEO signal. A page without an H1 is, from Google's perspective, a page without a topic declaration. The Briefs page is one of the most content-rich pages on the site — it contains summaries of the latest medical research. Without an H1, that content wealth is undervalued by search engines.

**The specific H1:** "Daily Healthcare News Briefs for Physicians"  
- "Daily" — signals freshness (important for Google's freshness algorithm)
- "Healthcare News Briefs" — exact match for common search queries
- "for Physicians" — qualifies the audience (improves click-through rate from search)

**Why a descriptive paragraph?**  
The paragraph: *"100-word summaries of the latest medical research, clinical trials, and healthcare news — curated for busy physicians across all specialties."*

This paragraph:
1. Contains 4 additional keyword phrases: "medical research", "clinical trials", "healthcare news", "busy physicians"
2. Provides AI engines with a citable, factual description of the page's purpose
3. Sets visitor expectations before they interact with the filters

### 7.2 Content Tabs (For You / Latest / Voice Briefs)

**Change:** Tabs moved from below the filter pills to above them, given more visual weight with a proper underline active state.

**Why tabs above specialty pills?**  
The content type (For You vs. Latest) is a higher-order filter than specialty. Switching from "For You" to "Latest" changes the entire ranking algorithm. Specialty filtering applies within whichever tab is selected. The higher-order filter should be visually dominant.

**Why "Voice Briefs" with a NEW badge?**  
Voice briefs represent a differentiating feature — audio-format summaries that HCPs can listen to. The NEW badge creates a discovery moment for users who haven't explored this feature. It also creates a content category that is increasingly valuable for AEO, as voice content is indexed differently by some search systems.

### 7.3 Specialty Filter Pills

**Change:** Filter pills are always visible above the content list. Previously, they were accessible via a filter button/drawer on mobile.

**Why always-visible pills?**  
A filter that requires 2 clicks to access is a filter that most users never use. HCP time is the scarcest resource on the platform. Specialty filtering — the ability to see only Cardiology or only Oncology briefs — is Curie's core personalization feature. Making it require a modal to access is equivalent to hiding the most valuable feature.

**Why pills instead of a dropdown?**  
Horizontal scrollable pills show all available options simultaneously without requiring any interaction. A dropdown hides all options until clicked. When options are visible, users make faster, more confident selections (fewer second-guesses). The pill pattern is also familiar from LinkedIn job filters and Google News topics.

### 7.4 List View with Full Summaries

**Change:** Brief cards in the list view now show the full 2-3 sentence summary, not just the title.

**Previous state:** Brief cards showed title + source tag + date. The summary was only visible after opening the brief.

**Why show full summaries in the list?**  

1. **For HCPs:** A physician reviewing 10 briefs in 3 minutes (Curie's core use case) needs to assess relevance without opening each item. The summary — containing the key finding and statistics — allows them to decide "relevant / not relevant" in one pass.

2. **For SEO:** Every summary in the list view is now crawlable. A page that contains the text "EMPA-KIDNEY trial confirms durable kidney protection with empagliflozin — HR 0.69 (95% CI 0.60–0.80) across all eGFR strata" will rank for searches related to those trial results. The existing design hid this text behind a click.

3. **For AEO:** AI engines extract and cite paragraph text. Brief summaries containing drug names, trial names, hazard ratios, and statistical outcomes are exactly the kind of entity-rich content that Perplexity and ChatGPT cite when answering clinical queries. Making this text visible on the page (not modal-only) means AI engines can discover, index, and cite it.

---

## 8. AI Solutions Page

### 8.1 Hero Headline

**Previous headline:** "The Clinical Grandeur of AI Intelligence"

**New headline:** "Free AI Clinical Tools for US Physicians"

**Why this change?**

The previous headline is poetic and visually bold. It is completely useless for SEO and AEO.

Nobody searches for "clinical grandeur of AI intelligence." But physicians search for:
- "free prior authorization letter generator"
- "prior auth letter AI physician"
- "free AI tools for doctors"
- "ICD-10 lookup tool free"

The new headline matches these queries exactly. More importantly:
- "Free" — addresses the #1 objection before it's raised
- "AI Clinical Tools" — exact match for the primary search intent
- "for US Physicians" — geo-qualifies (important for payer database relevance) and audience-qualifies

**The SEO impact is significant:** A headline change on a high-value page from zero-intent-match to exact-intent-match can shift that page from page 5 to page 1 for target queries, with no other changes required.

### 8.2 Trust Badges

**Change:** Added 3 trust badges below the headline: "HIPAA-Conscious", "Physician-Only", "No Patient Data Stored"

**Why?**  
HCPs have heightened privacy awareness compared to general consumers — HIPAA violations can result in personal liability, license risk, and institutional consequences. A physician considering using an AI tool to generate clinical documents will have immediate privacy concerns. Addressing these concerns above the fold ("No Patient Data Stored") removes the most common objection before it becomes a barrier to tool adoption.

These badges also serve as E-E-A-T signals for search engines — they indicate that the page is from an organization with relevant expertise and trustworthiness in the healthcare domain.

### 8.3 Prior Auth Tool — Letter Preview

**Change:** The Prior Auth Scribe card now includes a mini-preview of an actual generated letter within the card.

**Why?**  
The existing card describes the tool in words ("Generate evidence-based prior authorization requests"). The redesigned card shows an actual output example — a formatted letter with patient demographics, diagnosis codes, and clinical justification.

This change is important because:
1. **Specificity beats description:** Showing physicians what the output looks like is more persuasive than describing it. "This is what you get" is always more compelling than "here's what this does."
2. **AEO:** The letter preview contains medical entities (drug names, ICD codes, payer criteria references) that are exactly the content AI engines cite when answering "how to write prior auth for Humira" queries.
3. **Trust:** Showing real output format signals that the tool understands payer requirements — not just generic AI output.

### 8.4 FAQ Section — Pre-Expanded

**Change:** Two FAQ items are visible and expanded on the AI Solutions page without requiring any interaction.

**Previous state:** No FAQ on the AI Solutions page.

**Why add FAQs and pre-expand them?**  

For SEO: Google uses `FAQPage` structured data to populate rich results (collapsible Q&A in search results). But even without structured data, FAQ text that is visible in the DOM (not hidden behind a click) is indexed and can appear as featured snippets.

The specific questions chosen answer the highest-objection queries:
- "How does Curie know what each payer requires?" — directly addresses the #1 physician skepticism point
- "Is Curie's prior authorization letter generator free?" — the most common intent-matching query

When a physician searches "is Curie prior auth free?" and Google shows the direct answer in a featured snippet, that drives zero-click confidence that converts directly to usage.

---

## 9. Games Page

### 9.1 Full Game Descriptions

**Change:** Each game card now includes a 2-sentence description of the gameplay.

**Previous state:** Game cards showed only a name and "Play Now" button.

**Why?**  
Cold visitors who haven't played Curie's games don't know what to expect from "Pinpoint" or "Strands." Two sentences ("Guess the mystery medical term from progressively revealing clues") turns a mystery into an invitation. Lower uncertainty = higher click-through to game pages.

**SEO note:** Game descriptions also provide indexable text. A page with descriptions like "daily medical brain puzzles for healthcare professionals" can rank for queries like "medical games for doctors" or "clinical puzzle games."

---

## 10. Podcasts Page

### 10.1 Show Context Before Episode List

**Change:** A show header card (with artwork, show name, description, and episode count) appears above the episode list.

**Previous state:** Episode list displayed immediately with no contextual framing.

**Why?**  
An HCP arriving at the Podcasts page from a Google search for "oncology podcast for physicians" needs to evaluate the show before committing to an episode. The show header gives them:
- The show's focus area (so they can filter relevance)
- Episode count (signals investment level of the content)
- A description (crawlable text for SEO)

Without this context, the visitor sees a list of episode titles and must infer the show's purpose from the titles alone — a higher-effort, lower-confidence evaluation.

---

## 11. Editorial Page

### 11.1 Author Attribution

**Change:** Every editorial piece now shows the author's name and credential in a subtitle above the headline.

**Why?**  
Editorial content by named physicians (e.g., "Ekaterina Ripp, MD") carries significantly more E-E-A-T weight than anonymous editorial content. Google's Quality Rater Guidelines explicitly reward content where the author's expertise is visible and verifiable. Showing "MD" credentials on editorial pieces elevates the entire domain's authority score.

### 11.2 Excerpt Visible in Listing

**Change:** Each editorial card shows a 2-sentence excerpt.

**Why?**  
Same reasoning as brief summaries — visible text is indexable text. The excerpt "Most cancer patients start treatment in a community clinic, not an academic tower. That model is under siege" contains specific, factual claims that AI engines can cite when answering queries about community oncology.

---

## 12. Newsletter Page

### 12.1 Feature Grid

**Change:** Added a 4-item feature grid showing what subscribers receive (Top Briefs, Podcast of the Week, AI Tool Updates, Game Leaderboard).

**Previous state:** Email input field with minimal context.

**Why?**  
Email signup conversion is heavily driven by perceived value clarity. "Subscribe to our newsletter" converts at roughly 2-5%. "Here's exactly what you'll get every Sunday morning — [list of specific benefits]" converts at 2-4x that rate. The feature grid answers the visitor's evaluation question ("is this worth my inbox space?") before they decide.

---

## 13. Brief Detail Panel

### 13.1 Side Panel Instead of Modal

**Change:** Brief detail opens as a right-side slide-in panel (500px), not a full-screen modal.

**Why a side panel?**  

1. **Context preservation:** A full-screen modal removes all context — the user forgets where they came from. A side panel keeps the brief list visible, making it easy to close and scan for the next brief. This is especially important for HCPs doing a rapid review of 5-10 briefs.

2. **Navigation continuity:** Related briefs shown at the bottom of the panel are clickable — they replace the panel content without going back to the list. This enables a "brief-hopping" flow that keeps users on the platform longer.

3. **Mobile behavior:** On mobile, the panel fills the full width, behaving like a native sheet component — familiar and expected.

### 13.2 Full Summary in Panel

**Change:** The panel shows the complete 100-word summary, not just the title.

**Why?**  
The 100-word brief is the product. Showing it fully — with proper typography, line height, and left-border accent — is the core reading experience. The panel is designed to make this reading experience as friction-free as possible.

### 13.3 Related Briefs at Bottom

**Change:** Two related briefs are shown at the bottom of the detail panel, clickable to replace the current panel content.

**Why?**  
Session depth (number of briefs read per session) is a key engagement and retention metric. Related briefs extend the reading session without requiring the user to navigate back to the list. The pattern is analogous to "Continue Reading" in editorial apps (Substack, Pocket).

---

## 14. SEO Improvements

| Change | Page | SEO Impact |
|---|---|---|
| Keyword-rich H1 above the fold | Homepage | +++ Primary on-page signal now visible to crawler |
| H1 on every main page | All pages | ++ Each page has a clear topic declaration |
| Full summary text visible in brief cards | Briefs, Homepage | +++ Clinical entity text indexed without user interaction |
| Descriptive sub-copy on each page | All pages | ++ Adds keyword variety and semantic context |
| Author attribution with credentials | Editorial | ++ E-E-A-T signal for domain authority |
| Pre-expanded FAQ on AI Solutions | AI Solutions | ++ FAQ content indexable; potential featured snippet |
| Tool descriptions with specific use cases | AI Solutions | ++ Matches transactional search intent |
| Trust badges visible in DOM | AI Solutions | + Domain trust signal for medical query ranking |
| Content type descriptions on Games page | Games | + Discovery surface for "medical games" queries |
| Show description on Podcasts page | Podcasts | + Matches "medical podcast" search queries |

---

## 15. AEO — AI Engine Optimization

AI Engine Optimization (AEO) is the practice of structuring content so that AI-powered answer engines (Perplexity, ChatGPT Search, Google AI Overviews, Claude) can find, extract, and correctly attribute your content when answering user queries.

### 15.1 Entity-Rich Text

Every brief summary in the redesign contains named medical entities:
- **Drug names:** Tirzepatide, Pembrolizumab, Lecanemab, Empagliflozin, Sotorasib
- **Trial names:** SURMOUNT-MMO, KEYNOTE-756, CLARITY AD, EMPA-KIDNEY, CodeBreaK 200
- **Statistics:** HR 0.69, NNT=31, pCR 24.3%, ARIA-E 21%
- **Conditions:** Obesity, Breast Cancer, Alzheimer's, CKD, NSCLC

These entities are exactly what AI engines extract when answering queries like:
- "What did SURMOUNT-MMO show?" → Curie brief gets cited
- "What is the NNT for tirzepatide cardiovascular benefit?" → Curie brief gets cited
- "Free prior auth letter generator for doctors" → Curie AI Tools page gets cited

### 15.2 Question-Answer Structure

The FAQ sections on AI Solutions and the brief detail panel's "Physician-verified" badge create a Q&A structure that AI engines prefer for extraction. Questions like "Is Curie's prior authorization letter generator free?" followed by a direct answer satisfy the pattern that AI engines use for featured snippets and cited answers.

### 15.3 About-the-Product Paragraph

Each major page contains a descriptive paragraph about what that section of Curie is and does. For example, on the AI Solutions page: *"Curie AI provides free prior authorization letter generators, ICD-10 code lookup, and clinical reading tools — purpose-built for verified US healthcare professionals."*

This paragraph answers the AI engine's implicit question "what is this page about?" with a complete, factual, attributable statement.

---

## 16. Trust & E-E-A-T Signals

Google's E-E-A-T framework (Experience, Expertise, Authoritativeness, Trustworthiness) is the primary quality signal framework for YMYL (Your Money or Your Life) queries — which medical content absolutely falls under.

### 16.1 Signals Added

| Signal | Location | E-E-A-T Category |
|---|---|---|
| "100,000+ verified HCPs" | Homepage hero, AI Solutions | Authoritativeness |
| "Free Forever" | Homepage, newsletter | Trustworthiness |
| Author credentials ("MD") | Editorial listings | Expertise |
| "Physician-Only", "HIPAA-Conscious" | AI Solutions | Trustworthiness |
| "No Patient Data Stored" | AI Solutions | Trustworthiness |
| Source attribution (NEJM, Lancet, ASCO) | All brief cards | Authoritativeness |
| "Physician-verified" on brief detail | Brief panel | Expertise |

### 16.2 Why These Signals Matter

Google has explicitly stated that medical content must demonstrate the expertise of the author, the authority of the publishing organization, and the trustworthiness of the information. Pages that surface these signals in crawlable, prominent HTML are significantly more likely to rank well for competitive medical queries.

For AI engines, these signals matter equally — Perplexity and ChatGPT prioritize citing sources that appear authoritative in the domain of the query. A medical brief platform that visibly states "100K+ verified physicians" and attributes content to "NEJM" is treated as a more credible source than one without these signals.

---

## 17. Responsive Design

### 17.1 Breakpoint Strategy

**Desktop** (>768px): Full sidebar + main content layout  
**Mobile** (≤768px): Top bar + mobile bottom tab bar + single-column layouts

### 17.2 Layout Adaptations

| Component | Desktop | Mobile |
|---|---|---|
| Hero section | 2-col split (value prop + featured card) | Single column (value prop only) |
| Brief cards grid | 3 columns | 1 column |
| Podcast cards | 2 columns | 1 column |
| Games grid | 3 columns | 1 column |
| Tool cards | 2-col bento | 1 column |
| FAQ | 2 columns | 1 column |
| Navigation | Left icon sidebar | Top bar + bottom tab bar |

### 17.3 Mobile Navigation Design

**Why a bottom tab bar with 5 items?**  
Mobile thumb ergonomics research consistently shows that 72% of phone interactions are single-handed, with the thumb reaching the bottom 1/3 of the screen most easily. Navigation placed at the bottom of the screen is accessible in 1 tap from any thumb position. Top navigation requires an unnatural stretch or a shift to two-handed operation.

**The 5 items selected:**  
Home, Briefs, Games, Podcasts, AI Tools — the 5 highest-frequency user actions. Editorial and Newsletter are secondary; they're accessible via desktop sidebar or scrolling the homepage.

---

## 18. Future Enhancements

These are improvements not included in the current redesign scope but recommended as high-priority next steps.

### 18.1 Schema Markup (Structured Data)

**Priority: High**  
**Effort: Medium**

Implement JSON-LD structured data across all pages:
- `FAQPage` on AI Solutions and Homepage FAQ section
- `Article` / `MedicalWebPage` on each Brief detail
- `Organization` and `WebSite` on the Homepage
- `BreadcrumbList` on all inner pages
- `Podcast` and `PodcastEpisode` on Podcasts pages

**Why:** Structured data unlocks rich results in Google Search (FAQ dropdowns, article carousels, breadcrumbs in URLs). These features increase click-through rate by 20-30% for listings that have them vs. those that don't.

---

### 18.2 Specialty Landing Pages

**Priority: High**  
**Effort: High**

Create dedicated, SEO-optimized pages for each specialty:
- `/briefs/cardiology` — "Latest Cardiology News Briefs for Cardiologists"
- `/briefs/oncology` — "Daily Oncology Updates for Oncologists"
- `/briefs/neurology` — "Neurology Research Briefs for Neurologists"

**Why:** Currently, all specialty content lives behind a filter on `/briefs`. Search engines cannot rank a filtered URL for specialty queries. A dedicated `/briefs/cardiology` page with an H1, description, and specialty-specific FAQ can rank for "cardiology news for doctors" — a high-volume, high-intent query that currently has no landing page to direct to.

---

### 18.3 Trial & Drug Entity Pages

**Priority: High**  
**Effort: High**

Create individual pages for major clinical trials and drugs:
- `/trials/surmount-mmo` — "SURMOUNT-MMO Trial: Results, Summary, and Clinical Implications"
- `/drugs/tirzepatide` — "Tirzepatide (Zepbound/Mounjaro): Briefs, Podcasts, and Clinical Evidence"

**Why:** These are the highest-intent medical search queries on the web. "SURMOUNT-MMO results" gets thousands of physician searches around publication dates. A Curie page that aggregates all Curie briefs, podcast episodes, and editorial content related to that trial would rank for these queries and drive large volumes of highly qualified physician traffic.

---

### 18.4 Persistent Audio Player

**Priority: Medium**  
**Effort: Medium**

A persistent bottom audio player that continues playing when navigating between pages, with playback position saved to localStorage.

**Why:** Currently, navigating away from a podcast episode stops playback. This creates a forced choice: keep listening or keep reading. A persistent player (as seen in Spotify, SoundCloud) removes this friction and meaningfully increases average session time for podcast listeners.

---

### 18.5 Brief Audio Playback on Card

**Priority: Medium**  
**Effort: Low**

Add a small play button to each brief card on the Briefs page that plays the voice version of that brief directly in the card without opening the detail panel.

**Why:** Voice briefs are a differentiating feature. Making audio one tap from the list view (vs. two taps: open panel → play) removes the biggest friction point in the voice brief experience. Physicians who are between patients can tap and listen to a 45-second audio brief without opening anything.

---

### 18.6 Personalized Homepage Feed

**Priority: Medium**  
**Effort: High**

After a user signs in and completes specialty selection, the homepage "Today's Briefs" section should show specialty-filtered briefs by default, not the global top briefs.

**Why:** The homepage currently shows the same 3 briefs to all visitors — logged-in or not, cardiologist or internist. A cardiologist who sees oncology briefs on their homepage on day one of using Curie will feel less understood, less likely to return. Personalized relevance is the single biggest driver of daily active use in content platforms.

---

### 18.7 CME Credit Integration

**Priority: Medium**  
**Effort: Very High**

Explore integration with CME credit tracking providers (Medscape, AMA Ed Hub) so that brief-reading activity can count toward continuing medical education credits.

**Why:** CME is a powerful forcing function. If reading 10 Curie briefs counts toward CME credit requirements, physicians have a formal, professional justification for spending time on the platform. This transforms Curie from "nice to have" to "professionally obligatory" — a fundamentally different retention dynamic.

---

### 18.8 Search Functionality

**Priority: High**  
**Effort: High**

A full-text search bar (accessible via `Cmd+K` or a search icon in the sidebar) that searches across all briefs, podcast episodes, editorial pieces, and AI tool help content.

**Why:** As the content library grows, discovery via browsing becomes insufficient. HCPs often remember a specific trial result they read last week and want to find it again. Without search, this requires scrolling through chronological lists. With search, it's a 3-second query. This also creates a new SEO surface: search result pages that capture long-tail queries.

---

### 18.9 Dark/Light Mode Toggle

**Priority: Low**  
**Effort: Medium**

A light mode option alongside the existing dark mode.

**Why:** Hospital environments, especially during rounds on shared desktop workstations, may have lighting conditions where a dark interface creates contrast problems. Some physicians also have personal preferences for light-background reading for long-form content. A toggle adds no content complexity and meaningfully expands accessibility.

---

### 18.10 OpenGraph & Twitter Card Optimization

**Priority: High**  
**Effort: Low**

Every brief, podcast episode, and editorial piece should have a unique, auto-generated OpenGraph image that includes the headline, specialty tag, and Curie branding — optimized for sharing on LinkedIn, X, and WhatsApp.

**Why:** When physicians share a Curie brief on LinkedIn, the current link preview is generic (Curie logo on dark background). A brief-specific preview image with the headline and specialty tag dramatically increases click-through rate when shared. It also signals to LinkedIn's algorithm that the content is rich and specific, boosting organic reach of shared posts.

---

*End of specification.*

**Document version history:**
| Version | Date | Changes |
|---|---|---|
| 1.0 | Jun 2025 | Initial specification |
