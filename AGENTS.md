# Agent Instructions

This repo is a multi-topic learning workspace. Each top-level topic directory is its own teaching workspace.

All topic-specific learning content must live one level below the repo root, inside a topic directory such as `boron/`. Do not create topic-specific files like `sources.md`, `overview.md`, or `reference/` at the repo root. The root `README.md` is repo-wide only.

Use the repo-local `learn` skill at `.codex/skills/learn/` for teaching workflows in this repo.

The primary user workflow is `/learn <topic>`. Treat that as a command to create or resume `./<topic-slug>/`, where `<topic-slug>` is a dash-case version of the topic. If the folder does not exist, initialize the standard topic workspace one level below the repo root and update the root topic index.

## Structure

Topic directories should follow this layout:

- `README.md` - the topic front door: mission, roadmap, page index, and file index
- `overview.md` - the direct explanation of the topic
- `sources.md` - trusted sources and communities
- `reference/` - focused supporting pages and quick-reference documents
- `glossary.md` - optional canonical vocabulary when terminology starts to matter

The root `README.md` is the index of all topics.

## Teaching Rules

- Keep one topic per top-level directory.
- For `/learn <topic>`, create or resume exactly one top-level topic directory named with a dash-case slug.
- Store every topic workspace exactly one level deep from the repo root, for example `boron/README.md` and `boron/reference/core-map.md`.
- Leave the repo root for repo-wide files only, such as `README.md`, `AGENTS.md`, `CLAUDE.md`, and `.codex/`.
- Ground health, legal, financial, and fast-changing topics in current high-trust sources.
- Prefer direct explanatory pages over exercise formats unless the user explicitly asks for drills.
- Every topic should have an `overview.md` that explains the topic directly, separate from the learning plan in `README.md`.
- Topic pages should be readable directly on github.com. Use Markdown as the primary format.
- Create or update reference documents when reusable knowledge deserves a focused page.
- Do not give personalized medical advice. For supplement and health topics, frame decisions as questions for a qualified clinician or pharmacist when appropriate.

## File Conventions

- Name reference pages with clear slugs such as `reference/core-map.md` or `reference/dose-safety.md`.
- Prefer ASCII text unless an existing file clearly uses another character set.
- Keep root-level files for repo-wide guidance only.
