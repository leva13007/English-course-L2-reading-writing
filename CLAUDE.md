# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

A personal note-taking repository for an ESOL L2 (Level 2) English course running 23/02/2026 – 17/07/2026 at Cardiff and Vale College. Three classes per week, three teachers:

| Slot | Teacher | Format |
|------|---------|--------|
| Tuesday 17:45–20:45 | Gozde Erdogan | Offline, room 332 |
| Wednesday 17:45–19:45 | Jonathan Lecun | Online |
| Thursday 17:45–20:45 | Andrew Patterson | Offline, room 202 |

The owner is a Ukrainian speaker learning English. Notes mix English content with Ukrainian translations and personal observations.

## Tech stack

Pure Markdown, images (JPG/PNG), and PDFs. No build system, no tests, no dependencies. Git for version control. Vocabulary feeds into **Anki** (external flashcard app) — the `vocab.md` files use `- [ ]` checkboxes where `[x]` means "added to Anki."

## Folder structure pattern

```
{N}_{day}_{teacher}/YYYY-MM-DD/
  class.md          — class notes, topic, materials used
  hw.md             — homework task + due date + status emoji
  hw_solution.md    — my answer + teacher feedback + corrected version
  vocab.md          — lesson-specific vocabulary (rarely used; most vocab goes to root vocab.md)
  notes.md          — optional personal reflections / things to research
  attachments/      — screenshots, scans, Telegram photos, handout images
```

Session folders are named `YYYY-MM-DD` (ISO date). Images from class materials are often referenced inline in `class.md` using relative paths (e.g. `![p.60](../../resources/writing_booklet_pages/p60.jpg)`).

## Central trackers (cross-session files)

- **`homework.md`** — single table tracking all assignments across all teachers; rows link to individual `hw.md` files. Status: 🔴 not started · 🟡 in progress · 🟢 done.
- **`vocab.md`** (root) — unified vocabulary list for Anki, organised by teacher then by lesson date. Each entry has: word, definition, Ukrainian translation, Anki checkbox.

## Course resources

- `resources/L2 Reading Booklet.pdf` and `resources/L2 Writing Booklet.pdf` — the official course booklets.
- `resources/reading_booklet_pages/p01.jpg … p61.jpg` — each booklet page as an individual JPG so it can be embedded directly in Markdown notes.
- `resources/writing_booklet_pages/p01.jpg … p98.jpg` — same for the writing booklet.

When a homework task references "Reading Booklet p.19", the corresponding image is `resources/reading_booklet_pages/p19.jpg`.

## Templates

All templates are in `_templates/`. Copy the relevant template into the session folder and fill it in:

| Template | Purpose |
|----------|---------|
| `_templates/class.md` | Class notes skeleton |
| `_templates/hw.md` | Homework task with status field |
| `_templates/hw_solution.md` | Solution with task summary, my answer, and feedback sections |
| `_templates/vocab.md` | Per-lesson vocabulary with grammar/idioms sections |
| `_templates/notes.md` | Personal observations and research items |

## Workflow (from README)

1. Before class: copy `_templates/class.md` → `N_day_teacher/YYYY-MM-DD/class.md`
2. During/after class: fill in topic, notes, embedded images
3. Drop screenshots/scans into `YYYY-MM-DD/attachments/`
4. If homework assigned: copy `_templates/hw.md` → same folder + add row to `homework.md`
5. When doing homework: copy `_templates/hw_solution.md` → same folder
6. New words → root `vocab.md` under the teacher's section; mark `[x]` when added to Anki
7. Update status in `homework.md`: 🔴 → 🟡 → 🟢

## Key conventions

- Session folder dates use `YYYY-MM-DD` (some older folders under `_archive/` used `MM_DD` — that format is obsolete).
- `hw_solution.md` often contains multiple versions: "Version 1 — My First Attempt", "Version 2 — Corrected", "Version 3 — Optimal Model Answer". This pattern should be preserved when writing or editing solutions.
- Formal vs. informal register contrast is a recurring teaching pattern (Andrew's lessons especially). Tables comparing informal ↔ formal equivalents appear throughout `class.md` and `hw_solution.md` files.
- The `essays/` folder holds standalone writing assignments that span multiple lessons.
- `.env` stores the college student login — it is gitignored and should never be committed.
