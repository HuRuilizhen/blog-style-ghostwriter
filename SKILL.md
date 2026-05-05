---
name: blog-style-ghostwriter
description: Draft Jekyll-compatible technical blog posts in an existing structured engineering-blog voice from fragmented notes, bullet points, screenshots, references, partial outlines, or rough ideas. Use when Codex needs to imitate the writing style of a technical blog repository, expand scattered material into a structured long-form post, preserve a lecture-note or technical-explainer tone, or produce post metadata, table of contents, section hierarchy, and optional bilingual EN/ZH passages.
---

# Blog Style Ghostwriter

Read [references/style-profile.md](references/style-profile.md) before drafting.

## Workflow

1. Identify the article type from the material.
   - Default to a technical explainer or lecture-note style post.
   - Switch to a setup/log style only if the notes are clearly experiential and tool-oriented.
   - Keep bilingual EN/ZH only when the source material, audience, or prior post pattern strongly suggests it.
2. Extract the minimum viable structure from fragments.
   - Topic and thesis: what problem the post explains.
   - Reader promise: what the reader will understand or build after reading.
   - Evidence: code, formulas, diagrams, screenshots, examples, references.
   - Section candidates: definitions, mechanisms, comparisons, procedures, examples, caveats, conclusion.
3. Fill gaps conservatively.
   - Infer connective explanations and transitions when they are obvious from the topic.
   - Do not invent specific dates, benchmarks, APIs, course numbers, company names, or claims that require evidence.
   - If important facts are missing, keep the prose general or insert a clear placeholder for later completion.
4. Produce a Jekyll post skeleton.
   - Include frontmatter with `layout`, `title`, `description`, `date`, `feature_image`, and `tags` when the user asks for a ready-to-publish post.
   - Add `<!--more-->` after the opening section.
   - Add `## Table of Contents` for medium or long posts.
   - When updating an existing post, if headings are added, removed, or renamed, verify and update the Table of Contents accordingly.
   - Use `---` between major sections when it matches the house style.
5. Write in the author's blog voice.
   - Prefer calm, explanatory, lecture-like prose.
   - Define terms before using them deeply.
   - Move from concept to mechanism to example to tradeoff.
   - Use emphasis sparingly to mark key ideas.
6. Finish with closure.
   - Add a concise `# Conclusion` when the topic benefits from synthesis.
   - Add `Related Posts / Websites 👇` only when the user provides or requests references.

## Drafting Rules

- Open with one short paragraph that defines the topic, why it matters, and what the post will cover.
- Prefer explicit section hierarchy over freeform narration.
- Use lists, tables, formulas, and code blocks when they clarify structure.
- Keep paragraphs dense but readable; do not drift into diary-style reflection unless the source notes are explicitly personal.
- Preserve minor grammar quirks only lightly. Mimic the overall voice and rhythm, not the mistakes.
- When writing bilingual sections, present the English explanation first and the Chinese explanation second.
- When the input is highly fragmented, create a clean outline first internally, then expand it into prose.

## Image Handling

- Treat images as optional supporting evidence, not required output.
- Do not insert any image by default.
- Insert images only when the user explicitly asks for image placement, provides image assets, or requests a publish-ready post that clearly depends on visuals.
- When a publish-ready Jekyll post needs inline images, prefer the existing include pattern:

```liquid
{% include image_caption.html imageurl="/images/..." title="..." caption="..." %}
```

- Prefer image paths under `/images/` with short kebab-case or existing repository naming conventions.
- Use `feature_image` in frontmatter only when the user provides or approves a cover image.
- Generate `title` and `caption` in the same plain, descriptive style used in the blog:
  - `title`: short noun phrase naming what the reader sees
  - `caption`: similar to the title, often lowercase or lightly simplified
  - Avoid clickbait, abstract metaphors, or overly polished marketing language
- Use the surrounding paragraph to explain why the image matters before or immediately after inserting it.
- If the user provides an image without explanation, infer only what is directly visible and useful for the topic.
- Use images to support a paragraph, not to replace missing reasoning.
- When inferring prose from an image, describe observable structure, labels, relationships, or workflow cues; do not invent benchmarks, hidden mechanisms, or unstated intent.
- If the image path or filename is missing, leave a clear placeholder instead of fabricating one.

## Output Modes

- For `outline` requests, return frontmatter suggestions plus a section outline and key talking points.
- For `draft` requests, return a complete markdown post.
- For `polish` requests, keep the user's ideas and structure but rewrite in the house style.
- For `continue` requests, match the surrounding section depth and heading pattern before adding new content.

## Quality Check

- Verify that the opening paragraph states scope clearly.
- Verify that headings are specific, not generic filler.
- Verify that the Table of Contents still matches the current heading structure when the post includes one.
- Verify that each major section either defines, compares, explains, or demonstrates something concrete.
- Verify that code, formulas, and tables are introduced by text instead of appearing abruptly.
- Verify that unsupported hard facts are not fabricated.
- Verify that the result sounds like a technical blog post, not a marketing article or chat response.
