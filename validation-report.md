# Skill Validation Report

**Date:** 2026-06-11  
**Validator:** skill-creator v5.0.0 `quick_validate.py`  
**Scope:** All hosted SKILL.md files (excluding composio-skills)  
**Total:** 32 skills

---

## Results

### PASS — Script Confirmed (24)

| Skill |
|-------|
| artifacts-builder |
| brand-guidelines |
| canvas-design |
| competitive-ads-extractor |
| connect |
| connect-apps |
| content-research-writer |
| developer-growth-analysis |
| file-organizer |
| image-enhancer |
| internal-comms |
| invoice-organizer |
| lead-research-assistant |
| meeting-insights-analyzer |
| raffle-winner-picker |
| skill-creator |
| skill-share |
| tailored-resume-generator |
| template-skill |
| theme-factory |
| video-downloader |
| document-skills/docx |
| document-skills/pdf |
| document-skills/pptx |

### PASS — Manual Confirmed (8)

These reported errors due to a Windows cp1252/CRLF encoding bug in the validator script. Manual frontmatter inspection confirmed all are valid.

| Skill | Issue |
|-------|-------|
| changelog-generator | CRLF line endings |
| domain-name-brainstormer | CRLF line endings |
| langsmith-fetch | CRLF line endings |
| mcp-builder | CRLF line endings |
| slack-gif-creator | CRLF line endings |
| twitter-algorithm-optimizer | CRLF line endings |
| webapp-testing | CRLF line endings |
| document-skills/xlsx | CRLF line endings |

---

## Overall Verdict: PASS

All 32 skills have valid `name` (kebab-case) and `description` frontmatter meeting the Anthropic skill spec.

### Known Issue

`quick_validate.py` calls `Path.read_text()` without `encoding='utf-8'`, causing failures on Windows (defaults to cp1252) when files contain UTF-8 characters or CRLF line endings. Upstream fix: add `encoding='utf-8'` to `skill_md.read_text()` on line 22.
