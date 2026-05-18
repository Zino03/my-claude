# CLAUDE.md

## Project Overview
This repository provides automation tools for setting up and managing frontend projects with Claude Code.

## Stack
- Shell script (`setup.sh`) for project initialization
- Claude Code slash commands (`.claude/commands/`)

## Commands
- `bash setup.sh` — Run interactive project setup
- `/setup <project-name>` — Set up a new React + Vite + TypeScript + Tailwind project
- `/review` — Run automated code review on current changes

## Project Structure
```
claude-config/
├── setup.sh                      # Project setup script
├── CLAUDE.md                     # This file
├── .claude/
│   └── commands/
│       ├── setup.md              # /setup slash command
│       └── review.md             # /review slash command
└── README.md
```

## Conventions
- Slash command files go in `.claude/commands/` as `.md` files
- All instructions and comments are written in English