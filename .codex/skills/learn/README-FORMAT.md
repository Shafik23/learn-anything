# Topic README.md Format

`README.md` is the front door for a topic. It should answer: why this topic exists, where to start, what comes next, and where the important files are.

## Template

```md
# {Topic}

{One sentence describing the learning workspace.}

## Mission

{1-3 sentences. The concrete learning goal and why it matters.}

Success looks like:

- {A specific, observable thing the learner will be able to do}
- {Another specific thing}

Constraints:

- {Learning preferences, safety context, scope limits, or important boundaries}

Start here:

- [Lesson 1: {Title}](./lessons/0001-title.md)
- [Reference: {Title}](./reference/title.md)

## Roadmap

- {Next concept or skill}
- {Later concept or skill}

## Files

- [sources.md](./sources.md)
- [progress.md](./progress.md)
- [reference/{file}.md](./reference/{file}.md)
- [lessons/{file}.md](./lessons/{file}.md)
```

## Rules

- Keep the mission in `README.md`; do not create a separate `MISSION.md`.
- Keep it readable on github.com.
- Update the lesson index and roadmap whenever the topic changes.
- Avoid private scratch notes in public topic READMEs.
