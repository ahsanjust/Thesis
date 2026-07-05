# Meetings Directory

## Purpose
Organize all supervisor meetings chronologically. Each meeting has its own dated folder containing agenda, notes, and action items.

## Structure

Each meeting folder follows this pattern: `YYYY-MM-DD/`

```
meetings/
└── 2026-06-30/              # First meeting
    ├── agenda.md           # Prepared before meeting
    ├── notes.md            # Written during/after meeting
    └── action_items.md     # Tasks from meeting

└── 2026-07-07/              # Second meeting
    ├── agenda.md
    ├── notes.md
    └── action_items.md
```

## Meeting Workflow

1. **Before Meeting (Day -1)**
   - Create new folder: `mkdir -p meetings/YYYY-MM-DD/`
   - Copy template files from `/templates/`
   - Complete agenda.md
   - Mark completed action items from previous meeting

2. **During Meeting**
   - Take notes in notes.md
   - Document decisions and feedback
   - Note any new ideas or concerns

3. **After Meeting (Day +1)**
   - Finalize notes.md within 24 hours
   - Update action_items.md with new tasks
   - Commit all changes to git
   - Update PROJECT_STATUS.md

## File Templates

- `agenda.md` - List topics, questions, progress updates
- `notes.md` - Meeting minutes, decisions, feedback
- `action_items.md` - Tasks with deadlines and owners

**See**: `/templates/meeting_*` for templates

---
**Created**: 2026-07-02
