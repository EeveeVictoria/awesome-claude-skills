# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A curated collection of 1000+ Claude Skills. Two contribution types exist:

1. **External listings** — skills hosted elsewhere; contribute by adding a bullet to `README.md` only.
2. **Hosted skills** — skills living as folders in this repo (e.g., `changelog-generator/`, `skill-creator/`).

## Skill Structure

Every skill is a folder with a required `SKILL.md`:

```
skill-name/
├── SKILL.md          # Required: YAML frontmatter (name, description) + markdown instructions
├── scripts/          # Optional: executable helpers (Python/Bash)
├── references/       # Optional: documentation loaded on demand
└── assets/           # Optional: templates/images used in output
```

`SKILL.md` frontmatter must include `name` (kebab-case) and `description` (one sentence, third-person: "This skill should be used when...").

## PR Rules (enforced by CI)

The `label-ready-skill.yml` workflow validates every PR:

- **External listing PRs**: only `README.md` may change — no other files.
- New bullets must link to an **external URL** (not `composio.dev` or `anthropic.com`).
- No crypto/web3/blockchain/NFT keywords anywhere in added lines.
- New skills must be placed in **alphabetical order** within their category section.
- Changes must stay inside the `## Skills` … `## Getting Started` bounds of `README.md`.

## Contributing a Skill

### External listing (README-only PR)
1. Add a bullet under the correct category in `README.md`, alphabetically:
   ```markdown
   - [Skill Name](https://github.com/owner/repo) - One-sentence description. *By [@handle](https://github.com/handle)*
   ```
2. PR title: `Add [Skill Name] skill`
3. Branch: `add-skill-name`

### Hosted skill (new folder)
1. Create `skill-name/SKILL.md` using the template in `CONTRIBUTING.md`.
2. Add a relative-path bullet to `README.md` under the correct category.
3. Same PR title/branch conventions apply.

## README Structure

The `## Skills` section is the only area contributors may edit. Categories (e.g., `### Development & Code Tools`) contain alphabetical bullet lists. Everything before `## Skills` and after `## Getting Started` is locked by CI.

## No Build/Test Commands

This repo has no build step. The only automated check is the GitHub Actions PR validator (`.github/workflows/label-ready-skill.yml`), which runs Node.js inline and requires no local setup.
