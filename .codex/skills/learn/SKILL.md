---
name: learn
description: Teach the user a new skill or concept in this learn-anything repo.
disable-model-invocation: true
argument-hint: "What would you like to learn about?"
---

The user has asked to learn something. This is a stateful request: they intend to learn the topic over multiple sessions.

The primary invocation is:

```text
/learn <topic>
```

When the user invokes `/learn <topic>`, treat `<topic>` as the subject to create or resume.

## Repository Shape

Treat this repo as a collection of topic-specific teaching workspaces.

The repo root is the index. Each top-level topic directory is one teaching workspace:

- `./boron/`
- `./another-topic/`

When starting a new topic, create a new top-level directory using dash-case. Do not put a topic workspace directly at the repo root.

For `/learn <topic>`:

1. Convert `<topic>` into a dash-case slug.
   - `Boron` -> `boron`
   - `Linear Algebra` -> `linear-algebra`
   - `OpenAI API` -> `openai-api`
2. Create or resume `./<topic-slug>/`.
3. If the topic directory is new, initialize the standard workspace files and directories:
   - `README.md`
   - `overview.md`
   - `sources.md`
   - `reference/`
4. Update the root `README.md` topic list.
5. If the mission in `README.md` is missing or vague, ask the user why they want to learn the topic before writing topic pages.
6. If the mission is clear enough, create or update `overview.md`, then create any useful focused reference pages.

## Teaching Workspace

Within the active topic directory, learning state is captured in these files:

- `README.md`: the topic front door, mission, roadmap, page index, and file index. Use the format in [README-FORMAT.md](./README-FORMAT.md).
- `overview.md`: the direct explanation of the topic. Use the format in [OVERVIEW-FORMAT.md](./OVERVIEW-FORMAT.md).
- `sources.md`: trusted sources and communities. Use the format in [SOURCES-FORMAT.md](./SOURCES-FORMAT.md).
- `reference/*.md`: focused supporting pages and quick-reference documents.
- `glossary.md`: optional canonical vocabulary. Use the format in [GLOSSARY-FORMAT.md](./GLOSSARY-FORMAT.md).

The repo is primarily read on github.com, so Markdown is the primary output format. Do not create HTML unless the user explicitly asks for it.

## Philosophy

To learn deeply, the user needs three things:

- **Knowledge**, captured from high-quality, high-trust resources
- **Skills**, acquired through clear explanations, worked examples, and real-world application when useful
- **Wisdom**, developed by interacting with practitioners, communities, or real-world situations

Before `sources.md` is well populated, prioritize finding high-quality resources. Do not rely on parametric memory for health, legal, financial, fast-changing, or high-stakes topics.

Some topics need more skills than knowledge. Learning theoretical physics might be knowledge-heavy. Learning yoga, drawing, or negotiation might be practice-heavy.

## Topic Pages

The main unit is a readable topic page, not a quiz or formal lesson.

Use `overview.md` for the direct explanation of the topic. Use `reference/*.md` for focused supporting pages such as:

- `reference/core-map.md`
- `reference/evidence-map.md`
- `reference/dose-safety.md`
- `reference/key-terms.md`

Pages should be:

- directly tied to the mission in `README.md`
- in the user's zone of proximal development
- readable on github.com
- littered with links to high-trust sources where factual claims need support
- useful as standalone explanations

Use Markdown features that render well on GitHub:

- headings
- tables
- blockquotes
- fenced code blocks
- links

## The Mission

Every topic page should tie back to the mission in the topic `README.md`: the concrete reason the user is interested in the topic.

If the user is unclear about the mission, or the topic `README.md` has a missing or weak mission, first ask why they want to learn the topic. A bad mission makes pages too abstract and prevents good sequencing.

Revise the `README.md` mission and roadmap when the user's goal changes.

## Zone Of Proximal Development

Each page should challenge the learner just enough.

If the user names an exact thing they want to learn, focus there. If they do not, determine the next page by:

- reading the mission and roadmap in `README.md`
- reviewing existing topic and reference pages
- choosing the most relevant next skill or concept

If the user says they already know something important, reflect that in the `README.md` roadmap or the relevant topic page when useful.

## Acquiring Knowledge And Skills

Topic pages should explain concepts directly and clearly. Avoid exercises unless the user explicitly asks for them.

For high-trust knowledge:

- prefer primary sources, official docs, peer-reviewed papers, textbooks, or recognized expert resources
- keep `sources.md` curated and annotated
- remove shallow or misleading resources rather than accumulating links

Use worked examples when they clarify the subject. Do not add practice drills by default.

## Acquiring Wisdom

Wisdom comes from applying learning outside the page.

When the user asks a question that appears to require real-world judgment, answer as well as possible from evidence, then suggest an appropriate community, practitioner, or real-world feedback source.

Respect the user's preference if they do not want community involvement.

## Reference Documents

Create reference documents when reusable knowledge deserves its own focused page:

- syntax and snippets for programming
- algorithms and checklists for processes
- glossaries and terminology
- exercise routines or skill drills
- conceptual maps

Reference documents should be compressed and easy to scan on github.com. Name them with clear slugs, such as `dose-safety.md` or `hormone-terms.md`.
