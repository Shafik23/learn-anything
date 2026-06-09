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
3. If the topic directory is new, initialize the standard workspace files and directories.
4. Update the root `README.md` topic list.
5. If `MISSION.md` is missing or vague, ask the user why they want to learn the topic before writing lessons.
6. If the mission is clear enough, create the first Markdown lesson and any useful reference page.

## Teaching Workspace

Within the active topic directory, learning state is captured in these files:

- `MISSION.md`: why the user is learning this topic. Use the format in [MISSION-FORMAT.md](./MISSION-FORMAT.md).
- `RESOURCES.md`: trusted sources and communities. Use the format in [RESOURCES-FORMAT.md](./RESOURCES-FORMAT.md).
- `NOTES.md`: user preferences, teaching preferences, and working notes.
- `lessons/*.md`: GitHub-renderable Markdown lessons.
- `reference/*.md`: GitHub-renderable Markdown reference documents.
- `learning-records/*.md`: durable records of what the user has learned. Use the format in [LEARNING-RECORD-FORMAT.md](./LEARNING-RECORD-FORMAT.md).
- `GLOSSARY.md`: optional canonical vocabulary. Use the format in [GLOSSARY-FORMAT.md](./GLOSSARY-FORMAT.md).

The repo is primarily read on github.com, so Markdown is the primary output format. Do not create HTML lessons or HTML references unless the user explicitly asks for them.

## Philosophy

To learn deeply, the user needs three things:

- **Knowledge**, captured from high-quality, high-trust resources
- **Skills**, acquired through relevant lessons and exercises
- **Wisdom**, developed by interacting with practitioners, communities, or real-world situations

Before `RESOURCES.md` is well populated, prioritize finding high-quality resources. Do not rely on parametric memory for health, legal, financial, fast-changing, or high-stakes topics.

Some topics need more skills than knowledge. Learning theoretical physics might be knowledge-heavy. Learning yoga, drawing, or negotiation might be practice-heavy.

## Lessons

A lesson is the main unit of teaching. Each lesson is one self-contained Markdown file saved to `./lessons/` and named:

```text
0001-short-dash-case-title.md
```

Increment the number for each new lesson.

A lesson should teach **one thing only**. It should be completable quickly and give the user a tangible win that builds toward the mission.

Lessons should be:

- directly tied to the mission
- in the user's zone of proximal development
- readable on github.com
- littered with links to high-trust sources where factual claims need support
- designed around a feedback loop, such as practice questions with collapsible answers

Use Markdown features that render well on GitHub:

- headings
- tables
- blockquotes
- task lists
- fenced code blocks
- links
- `<details>` / `<summary>` for revealable answers

## The Mission

Every lesson should tie back to the mission: the concrete reason the user is interested in the topic.

If the user is unclear about the mission, or the topic's `MISSION.md` is missing or weak, first ask why they want to learn the topic. A bad mission makes lessons too abstract and prevents good sequencing.

Revise `MISSION.md` when the user's goal changes.

## Zone Of Proximal Development

Each lesson should challenge the learner just enough.

If the user names an exact thing they want to learn, focus there. If they do not, determine the next lesson by:

- reading `MISSION.md`
- reading `learning-records/`
- checking `NOTES.md`
- reviewing existing lessons and references
- choosing the most relevant next skill or concept

If the user says they already know something important, record that in `learning-records/` with the claimed depth.

## Acquiring Knowledge And Skills

Lessons should be designed around a skill or concept the user will practice. Teach only the knowledge needed for the practice.

For high-trust knowledge:

- prefer primary sources, official docs, peer-reviewed papers, textbooks, or recognized expert resources
- keep `RESOURCES.md` curated and annotated
- remove shallow or misleading resources rather than accumulating links

For practice:

- use short scenario questions
- use worked examples
- ask the user to classify, explain, calculate, decide, or critique
- provide answers in `<details>` blocks when the lesson is meant to be self-study on GitHub
- offer in-agent quizzes when live feedback is better than static answers

Each lesson should remind the user that they can ask follow-up questions.

## Acquiring Wisdom

Wisdom comes from applying learning outside the lesson.

When the user asks a question that appears to require real-world judgment, answer as well as possible from evidence, then suggest an appropriate community, practitioner, or real-world feedback source.

Respect the user's preference if they do not want community involvement.

## Reference Documents

Create reference documents when a lesson introduces reusable knowledge:

- syntax and snippets for programming
- algorithms and checklists for processes
- glossaries and terminology
- exercise routines or skill drills
- conceptual maps

Reference documents should be compressed and easy to scan on github.com. Name them:

```text
0001-short-dash-case-title.md
```

Increment the number for each new reference page.

## Learning Records

Learning records are not session logs. Write one only when something durable changes future teaching:

- the user demonstrated understanding of a non-trivial concept
- the user disclosed prior knowledge
- a misconception was corrected
- the mission shifted

Use concise records. Prefer one paragraph unless extra evidence or implications genuinely matter.

## `NOTES.md`

Record user preferences and durable working notes in `NOTES.md`, especially:

- preferred lesson style
- pacing preferences
- domain constraints
- recurring safety context
- stated dislikes

Do not use `NOTES.md` as a transcript.
