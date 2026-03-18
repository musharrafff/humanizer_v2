# Humanizer v2

A Claude Code skill that makes AI-assisted writing sound like a person wrote it. Not by running a checklist of patterns to remove, but by teaching the model how good writers actually think.

## What this is

Most "humanizer" tools strip AI tells: the em dashes, the rule of three, the "in today's rapidly evolving landscape." That's necessary but insufficient. You end up with writing that doesn't sound like AI but also doesn't sound like anyone.

Humanizer v2 works differently. It encodes a writing philosophy: commit to a point of view, lead with concrete detail, build narrative tension, and close on something specific. The skill doesn't just clean up drafts. It changes how the model approaches writing in the first place.

## Install

Clone into your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/musharrafff/humanizer_v2.git ~/.claude/skills/humanizer
```

Or copy the skill file directly:

```bash
mkdir -p ~/.claude/skills/humanizer
cp SKILL.md ~/.claude/skills/humanizer/
```

## Usage

Ask Claude to humanize text, or just write with the skill active:

```
Humanize this: [paste text]
```

```
Write a post about [topic] — make it sound human
```

The skill also activates on triggers like "rewrite this," "this sounds like AI," or "draft this in my voice."

## How it works

The skill operates on four principles:

**Concrete beats abstract.** "The user experience has improved significantly" is nothing. "In 2021, moving funds between chains took six manual steps and assumed you already had gas tokens on the destination" is something. Vague writing isn't just weak, it's boring.

**The first sentence is everything.** If it doesn't make the reader lean in, the rest is wasted. A good opener either creates a question the piece answers or states something specific enough that continuing feels necessary.

**Narrative over information.** A list of facts is not writing. A list of facts connected by a thread of reasoning, leading somewhere the reader didn't expect, is.

**Perspective is not optional.** A data point sitting alone is a number. A data point with a "which tells you..." attached to it is a post.

## What it catches

The skill identifies and rewrites nine categories of AI voice killers:

| Pattern | What it looks like |
|---|---|
| Significance inflation | "marks a pivotal moment in the evolution of..." |
| Rule of three | "fast, cheap, and secure" |
| Thrilled-to-announce energy | "We're excited to share..." |
| Corporate vagueness | "leveraging our ecosystem's synergies" |
| The -ing tack-on | "...enabling new possibilities, fostering adoption" |
| Litotes | "not unlike," "not without merit" |
| Vague attribution | "Industry observers note..." |
| Listicle brain | Bullet points where prose should be |
| Generic conclusions | "The future looks bright" |

Plus format-level AI tells: em dash overuse (the skill enforces zero), bold/emoji spam, Title Case headings, sycophantic openers, and cutoff disclaimers.

## Format-aware

The skill adapts its approach based on what you're writing:

- **Short-form posts** — First line is the post. One idea. No "hot take:" prefixes.
- **Threads** — Hook in tweet one, each post advances the idea, last post lands with finality.
- **Long-form** — Open on tension, not conclusion. Paragraphs develop one idea fully. Subheadings describe, don't perform.
- **Newsletters** — Subject line conveys a fact or creates genuine curiosity. Register between sharp blog post and warm personal message.

## Before and after

**Before (AI-generated):**

> AI-assisted coding serves as an enduring testament to the transformative potential of large language models, marking a pivotal moment in the evolution of software development. In today's rapidly evolving technological landscape, these groundbreaking tools are reshaping how engineers ideate, iterate, and deliver, underscoring their vital role in modern workflows.
>
> At its core, the value proposition is clear: streamlining processes, enhancing collaboration, and fostering alignment. It's not just about autocomplete; it's about unlocking creativity at scale.

**After (humanized):**

> AI coding assistants can speed up the boring parts of the job. They're great at boilerplate: config files and the little glue code you don't want to write. They can also help you sketch a test, but you still have to read it.
>
> The dangerous part is how confident the suggestions look. I've accepted code that compiled and passed lint, then discovered later it missed the point because I stopped paying attention.
>
> If you treat it like autocomplete and review every line, it's useful. If you use it to avoid thinking, it will help you ship bugs faster.

## Writing influences

The skill's voice principles draw from how specific writers operate:

- **Paul Graham** — Abstract claim followed by concrete example within two sentences. Short words. Treats the reader as smart but busy.
- **Morgan Housel** — Opens with a small story that seems unrelated, then snaps it into focus. Writes to learn, not to report.
- **Lyn Alden** — Shows her work. Uses data, forms opinions about what it means, doesn't perform neutrality.
- **Cobie** — Says the thing people are thinking but not saying. No hedging, no softening.

These aren't templates. They're proof that committing to a perspective works across very different subjects and styles.

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — Pattern detection foundation
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) — Ongoing documentation of AI writing patterns

## Version history

- **2.2** — Zero em dash policy, litotes ban, final audit pass with second rewrite
- **2.1** — Voice killer definitions expanded, format-specific guidance added
- **2.0** — Complete rewrite: philosophy-driven approach replacing pattern checklist
- **1.0** — Initial release based on Wikipedia pattern matching

## License

MIT
