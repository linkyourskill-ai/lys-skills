# LinkYourSkill Skills

> Agent Skills for [Claude Code](https://docs.claude.com/en/docs/claude-code) and other agents — by [LinkYourSkill](https://github.com/linkyourskill-ai).

`lys-skills` is a collection of reusable [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills): self-contained folders, each anchored by a `SKILL.md`, that teach an AI agent how to do one thing well. Drop a skill into your agent's skills directory and it becomes available on demand.

## Skills

| Skill | What it does |
|---|---|
| [`lys-teach`](./lys-teach) | Turns the current directory into a **stateful teaching workspace**. The agent grounds every lesson in your real-world *mission*, gathers high-trust resources, and produces beautiful, self-contained HTML lessons — built on the **LinkYourSkill Design System** ("Dark Cosmic"). It tracks what you've learned across sessions via learning records and a glossary, and balances knowledge, skills, and wisdom. |

### `lys-teach` at a glance

- **Mission-grounded** — every lesson traces back to *why* you want to learn the topic (`MISSION.md`).
- **High-trust knowledge** — sourced from curated resources (`RESOURCES.md`), never from parametric guesses.
- **Durable skills** — interactive quizzes and tasks designed for storage strength: retrieval practice, spacing, interleaving.
- **Stateful across sessions** — learning records (`./learning-records/`) and a `GLOSSARY.md` track your zone of proximal development.
- **Beautiful by default** — lessons and reference docs ship the bundled [LinkYourSkill Design System](./lys-teach/design-system) (tokens, the Inter typeface, glass cards on a cosmic backdrop, the violet brand gradient, ready-made teaching components).

## Installation

Clone the repo and copy any skill into your agent's skills directory.

**Claude Code** — personal (all projects) or project-scoped:

```sh
git clone https://github.com/linkyourskill-ai/lys-skills.git

# Personal: available in every project
cp -R lys-skills/lys-teach ~/.claude/skills/lys-teach

# Or project-scoped: shared with your repo
cp -R lys-skills/lys-teach /path/to/your/project/.claude/skills/lys-teach
```

Then in Claude Code, invoke it:

```
/lys-teach What would you like to learn about?
```

## Repository layout

```
lys-skills/
  lys-teach/                   ← the teaching skill
    SKILL.md                   ← skill definition and instructions
    MISSION-FORMAT.md          ← format guides for the workspace state files
    RESOURCES-FORMAT.md
    LEARNING-RECORD-FORMAT.md
    GLOSSARY-FORMAT.md
    design-system/             ← the bundled LinkYourSkill Design System ("Dark Cosmic")
      lessons.css              ← the one stylesheet every lesson links
      lesson-template.html     ← copy this to start a lesson
      quiz.js                  ← zero-dependency retrieval-practice quiz widget
      tokens/ components/ foundations/ ui_kits/ assets/
      DESIGN-SYSTEM.md         ← full design-system guide
  LICENSE
  README.md
```

## About LinkYourSkill

[LinkYourSkill](https://github.com/linkyourskill-ai) is the AI-to-Human task-execution platform: when an AI agent hits the limits of what it can do digitally, it delegates physical, real-world tasks to verified human **Skillanbieter** through LinkYourSkill. It is German-first and EU/DSGVO-compliant. The design system bundled in `lys-teach` is the brand foundation for that product.

## Contributing

Each new skill is a top-level directory with its own `SKILL.md`. Keep skills self-contained, reuse the design system where visuals are involved, and follow the brand voice documented in [`lys-teach/design-system/DESIGN-SYSTEM.md`](./lys-teach/design-system/DESIGN-SYSTEM.md).

## License

[MIT](./LICENSE) © LinkYourSkill
