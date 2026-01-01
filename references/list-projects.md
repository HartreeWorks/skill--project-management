---
description: Show all projects from the central index
---

# /list-projects

Display all projects from `~/Documents/projects/projects.yaml` in a formatted table.

## Flow

### Step 1: Read projects index
Read `~/Documents/projects/projects.yaml`

If file doesn't exist or is empty, display:
```
No projects found.
Use /new-project to create your first project.
```

### Step 2: Display projects table

Format output as:
```
═══════════════════════════════════════════════════════════
Projects
═══════════════════════════════════════════════════════════

Folder                          │ Type     │ Status
────────────────────────────────┼──────────┼─────────
2025-09-website-redesign        │ client   │ active
2025-10-side-project            │ personal │ active
2025-06-old-client              │ client   │ archived

═══════════════════════════════════════════════════════════
Location: ~/Documents/projects/

To work on a project:
  cd ~/Documents/projects/{folder}
```

### Formatting notes

- Sort by folder name (which sorts chronologically due to YYYY-MM prefix)
- Show archived projects at the end or with visual distinction
- If many projects, consider grouping by status (active first, then archived)
- Truncate very long folder names if needed

## Arguments

Optional filter argument:
- `/list-projects active` - Show only active projects
- `/list-projects archived` - Show only archived projects
- `/list-projects client` - Show only client projects
- `/list-projects personal` - Show only personal projects
- `/list-projects planning` - Show only planning projects
