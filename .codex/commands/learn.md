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
   - Never create nested topic workspaces like `./science/boron/`; use exactly one top-level topic directory.
3. If the directory is new, initialize:
   - `README.md`
   - `overview.md`
   - `sources.md`
   - `reference/`
4. If the mission in `README.md` is missing or vague, ask the user why they want to learn the topic before writing topic pages.
5. If the mission is clear enough, create or update `overview.md`, then create any useful focused reference pages.
6. Update the root `README.md` topic index when adding a new topic.
7. Keep all topic pages as Markdown. Do not create HTML.

Use high-trust sources for factual claims, especially for health, legal, financial, technical, or fast-changing topics.
