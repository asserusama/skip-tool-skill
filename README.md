# Skip Tool Skill

A Cursor Agent Skill for [Skip](https://skip.dev): dual-platform iOS and Android development with Swift and SwiftUI.

## What it does

- Guides getting started (new vs existing project, Skip install, `skip checkup`)
- Establishes mode: Skip Fuse (native) or Skip Lite (transpiled)
- References for CLI, modes, compiler directives, building, troubleshooting, porting
- SkipUI, SkipFoundation, and component reference (all content local; no web dependency)

## Install (Cursor)

**Personal (all projects):** Copy this folder to `~/.cursor/skills/skip-tool/`

```bash
git clone https://github.com/YOUR_USERNAME/skip-tool-skill.git ~/.cursor/skills/skip-tool
```

**Project:** Copy into your repo as `.cursor/skills/skip-tool/`

## Structure

- `SKILL.md` — Overview, workflow, core guidelines, quick reference, references list
- `references/` — Small, topic-specific files (getting-started, cli, modes, directives, building, troubleshooting, porting, modules, skip-ui, skip-foundation, components, component-*)

The agent reads only the reference file(s) needed for each request.

## License

Use and adapt as you like. Skip is by [skiptools](https://github.com/skiptools); this skill is unofficial.
