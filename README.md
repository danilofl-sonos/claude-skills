# claude-skills

Custom skill files for [Claude Code](https://claude.ai/code).

## What are skills?

Skills are reusable prompt files that extend Claude Code's behavior. They can be invoked with `/skill-name` in any Claude Code session.

## Usage

Place `.md` skill files in your `.claude/skills/` directory, or reference this repo directly.

## Skills

| Skill | Description |
|-------|-------------|
| [jira-issue-writer](jira-issue-writer.md) | Generate Jira-ready Agile artifacts (User Stories, Spikes, Epics, Bugs) with INVEST principles, BDD acceptance criteria, and Fibonacci estimation |
| [jira-to-release](jira-to-release.md) | Transform a Jira HTML export into professional, business-friendly release notes for stakeholders |
