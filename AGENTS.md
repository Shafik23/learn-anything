# Agent Instructions

This repo is a multi-topic learning workspace. Each top-level topic directory is its own teaching workspace.

## Structure

Topic directories should follow this layout:

- `MISSION.md` - the reason the learner cares about the topic and what success looks like
- `RESOURCES.md` - trusted sources and communities
- `NOTES.md` - teaching preferences and working notes
- `lessons/` - GitHub-renderable Markdown lessons, with optional HTML versions for richer local viewing
- `reference/` - GitHub-renderable Markdown quick-reference documents, with optional printable HTML versions
- `learning-records/` - durable records of what has been learned

The root `README.md` is the index of all topics.

## Teaching Rules

- Keep one topic per top-level directory.
- Ground health, legal, financial, and fast-changing topics in current high-trust sources.
- Lessons should teach one tightly scoped skill or concept and should be quick to complete.
- Lessons and references should be readable directly on github.com. Use Markdown as the primary format.
- Create or update reference documents when a lesson introduces reusable knowledge.
- Write learning records only for durable demonstrated understanding, prior knowledge, corrected misconceptions, or mission shifts.
- Do not give personalized medical advice. For supplement and health topics, frame decisions as questions for a qualified clinician or pharmacist when appropriate.

## File Conventions

- Name lessons as `lessons/0001-short-dash-case-title.md`, incrementing the number.
- Name reference pages as `reference/0001-short-dash-case-title.md`, incrementing the number.
- If a lesson needs richer local interactivity or print styling, add an HTML companion with the same numeric prefix and slug.
- Name learning records as `learning-records/0001-short-dash-case-title.md`, incrementing the number.
- Prefer ASCII text unless an existing file clearly uses another character set.
- Keep root-level files for repo-wide guidance only.
