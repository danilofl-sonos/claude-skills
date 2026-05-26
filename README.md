# claude-skills

Custom skill files for [Claude Code](https://claude.ai/code).

## What are skills?

Skills are reusable prompt files that extend Claude Code's behavior. They can be invoked with `/skill-name` in any Claude Code session.

## Usage

Place `.md` skill files in your `.claude/skills/` directory, or reference this repo directly.

## Skills

| Skill | Description |
|-------|-------------|
| [AL-jira-issue-writer](AL-jira-issue-writer.md) | Generate Jira-ready Agile artifacts (User Stories, Spikes, Epics, Bugs) with INVEST principles, BDD acceptance criteria, and Fibonacci estimation |
| [AL-jira-release-notes](AL-jira-release-notes.md) | Transform a Jira HTML export into professional, business-friendly release notes for stakeholders |
| [AL-jira-sprint-capacity](AL-jira-sprint-capacity.md) | Calculate the [X][Y] sprint capacity label from team members, OTO days, and split-team fractions |
| [UX-design-partner](UX-design-partner.md) | Senior UX design partner for creating designs, critiquing interfaces, auditing usability, and planning user flows |
