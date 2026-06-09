# Learn Anything

This repo is a collection of topic-specific learning workspaces.

Teaching workflow instructions live in the repo-local Codex skill at `.codex/skills/learn/`.

Use:

```text
/learn <topic>
```

The agent should create or resume a one-level-deep topic folder such as `boron/` or `linear-algebra/`, then build the topic workspace there.

Each topic lives one level below the repo root and can contain:

- `README.md` - the topic front door: mission, roadmap, lesson index, and file index
- `sources.md` - trusted sources and communities
- `progress.md` - compact durable learning state
- `lessons/` - GitHub-renderable Markdown lessons
- `reference/` - GitHub-renderable Markdown quick-reference documents
- `glossary.md` - optional canonical vocabulary when terminology starts to matter

## Topics

- [Boron](./boron/) - deep science of boron supplementation, testosterone, bone health, mineral metabolism, and safety

## Using A Topic

Open a lesson directly on GitHub or work from inside the topic directory.

- [Boron Lesson 1: Build The Evidence Map](./boron/lessons/0001-boron-evidence-map.md)
