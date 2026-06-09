# /learn

Use the repo-local `learn` skill in `.codex/skills/learn/`.

Invocation:

```text
/learn <topic>
```

`<topic>` is the subject the user wants to learn.

## Behavior

1. Convert `<topic>` into a dash-case topic slug.
   - Examples: `Boron` -> `boron`; `Linear Algebra` -> `linear-algebra`; `OpenAI API` -> `openai-api`.
2. Create or resume the topic workspace at `./<topic-slug>/`.
   - Never create topic files at the repo root.
   - Never nest topic work deeper than one top-level topic directory.
3. If the directory is new, initialize:
   - `MISSION.md`
   - `RESOURCES.md`
   - `NOTES.md`
   - `lessons/`
   - `reference/`
   - `learning-records/`
   - `README.md`
4. If the mission is missing or vague, ask the user why they want to learn the topic before writing lessons.
5. If the mission is clear enough, create the first GitHub-renderable Markdown lesson and any useful reference page.
6. Update the root `README.md` topic index when adding a new topic.
7. Keep lessons and references as Markdown. Do not create HTML.

Use high-trust sources for factual claims, especially for health, legal, financial, technical, or fast-changing topics.
