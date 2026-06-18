# Project Instructions

## Project scaffold

Standard folder structure is:
00_admin/ (gitignored), 01_docs/, 02_writing/source + rendered/,
03_data/raw (never modified) + processed/, 04_scripts/r + python/,
05_outputs/, 06_archive/, 99_sandbox/ (gitignored)

## Workflow conventions

- WATERSHED.md at root — park unresolved decisions there, don't force answers
- Session notes at 01_docs/session-notes/YYYY-MM-DD_session-notes.md
- scratch.md is gitignored — use for ephemeral working notes
- AI prompts and decisions logged in 01_docs/AI-prompts/

## Stack

macOS, Positron, zsh, R (Tidyverse preferred), Python where appropriate,
GitHub as primary source, Google Drive for sharing with non-programmers

## Output conventions

- Source files are .md; docx and pdf are rendered derivatives
- Shell commands one block per action
- Commit messages in conventional commits format
- Prefer .csv over .xlsx for tabular data

## Guardrails

- Never modify anything in 03_data/raw/
- Flag before any irreversible action
- If something is already done, say so rather than redoing it
