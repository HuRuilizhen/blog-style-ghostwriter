# Style Profile

## Core Shape

Model the author's posts as structured technical explainers with a lecture-note backbone.

- Start with a concise setup paragraph that defines the topic and previews coverage.
- Use `<!--more-->` immediately after the opening block.
- Add `## Table of Contents` for most substantial posts.
- Break large topics into major `#` sections separated by `---`.
- Use `##` for concrete subtopics such as definitions, mechanisms, comparisons, or steps.
- End with `# Conclusion` or `Related Posts / Websites 👇` when appropriate.

## Voice

- Sound explanatory, composed, and instructional.
- Prefer "In this post, we will explore..." or equivalent preview framing.
- Define terms early: "Before we start, let's define..."
- Explain from first principles before jumping to code or APIs.
- Use moderate emphasis with bold text for key concepts.
- Favor clarity over terseness; slightly repetitive reinforcement is acceptable.

## Typical Section Patterns

### Concept / course-note posts

1. Opening definition and scope
2. Notations or prerequisites when needed
3. Major conceptual sections
4. Mechanisms, examples, or formulas
5. Comparison / caveat / application
6. Conclusion or related links

### Engineering / tooling posts

1. Personal or practical motivation
2. Table of contents
3. Sequential setup steps
4. Commands and screenshots
5. Optional tips / caveats
6. Related links

## Content Reconstruction Heuristics

When the source material is fragmented, reconstruct in this order:

1. State the main problem.
2. Group fragments into 3-6 sections.
3. Turn nouns into headings and bullets into explanatory paragraphs.
4. Insert bridge sentences between sections.
5. Convert raw facts into comparisons, definitions, or procedures.

If a fragment suggests one of these common moves, use it:

- Definition fragment -> create a short conceptual subsection.
- Mechanism fragment -> explain workflow step by step.
- Two competing ideas -> create a comparison section or table.
- Code fragment -> add surrounding explanation, purpose, and caveats.
- Screenshot or diagram -> refer to it after explaining why it matters.

## Bilingual Mode

Use bilingual EN/ZH passages only when the user asks for it or the source material clearly matches older bilingual posts.

- Keep the English paragraph first.
- Follow with a Chinese paragraph that mirrors the same idea rather than introducing new claims.
- Use bilingual headings only when the user already provides them or the post is explicitly interview/teaching oriented.

## Formatting Cues

- Use markdown tables for crisp comparisons and summaries.
- Use fenced code blocks with language tags.
- Use inline code for APIs, commands, variables, and terminology.
- Use math only when the topic genuinely benefits from formal notation.
- Use image includes only when the target environment is the same Jekyll blog and the user wants publish-ready markdown.

## Image Conventions

- Default to no inline images unless the user explicitly asks for them.
- When inserting inline images for this blog style, prefer:

```liquid
{% include image_caption.html imageurl="/images/..." title="..." caption="..." %}
```

- Keep image filenames and paths simple and descriptive under `/images/`.
- Write image `title` as a short descriptive phrase, usually in title case.
- Write image `caption` as a short plain description, often mirroring the title with lighter casing.
- Explain the diagram or screenshot in prose before or after the include; do not drop raw images into the draft without framing.
- If only the image is available, infer section text from visible labels, layout, arrows, code, or UI states, but avoid claims that are not directly supported by the image.

## Avoid

- Do not write like a generic AI article with motivational filler.
- Do not overuse rhetorical questions.
- Do not add fake anecdotes or fabricated benchmarks.
- Do not force a conclusion if the article naturally ends with references or a final section.
- Do not make the prose too polished or corporate; keep some directness and classroom-note texture.
- Do not invent image filenames, image semantics, or technical conclusions that are not visible.

## Ready-to-Publish Frontmatter Template

```yaml
---
layout: post
title: "..."
description: "..."
date: YYYY-MM-DD
feature_image: ...
tags: ['tag-1', 'tag-2']
---
```

## Default Prompting Pattern

When invoked, aim to produce one of these:

- A complete markdown draft ready for `_posts/`
- A detailed outline with missing-information markers
- A style-preserving rewrite of the user's rough draft
