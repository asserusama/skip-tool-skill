# Skip Tool Skill

Agent Skill for [Skip](https://skip.dev): dual-platform iOS and Android development with Swift and SwiftUI.

## What it does

- Guides getting started (new vs existing project, Skip install, `skip checkup`)
- Establishes mode: Skip Fuse (native) or Skip Lite (transpiled)
- References for CLI, modes, compiler directives, building, troubleshooting, porting
- SkipUI, SkipFoundation, and component reference (all content local; no web dependency)

## Install

### Option A: skills.sh (recommended)

```bash
npx skills add https://github.com/asserusama/skip-tool-skill --skill skip-tool
```

Then use the skill in your AI agent, for example: *Use the Skip tool skill and help me set up a new Skip project* or *Use the Skip tool skill and fix this build error*.

More info: [skills.sh](https://skills.sh).

### Option B: Claude Code plugin

**Personal use in Claude Code:**

Add the marketplace:

```
/plugin marketplace add asserusama/skip-tool-skill
```

Install the skill:

```
/plugin install skip-tool@skip-tool-skill
```

### Option C: Cursor (git clone)

**Personal (all projects):** Copy this folder to `~/.cursor/skills/skip-tool/`

```bash
git clone https://github.com/asserusama/skip-tool-skill.git ~/.cursor/skills/skip-tool
```

**Project:** Copy into your repo as `.cursor/skills/skip-tool/`

## Structure

- `SKILL.md` — Overview, workflow, core guidelines, quick reference, references list
- `references/` — Small, topic-specific files (getting-started, cli, modes, directives, building, troubleshooting, porting, modules, skip-ui, skip-foundation, components, component-*)

The agent reads only the reference file(s) needed for each request.

## License

Use and adapt as you like. Skip is by [skiptools](https://github.com/skiptools); this skill is unofficial.
