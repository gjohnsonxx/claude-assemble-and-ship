# qa-kit

A small Claude Code plugin that bundles two QA-focused helpers: a command for
summarizing branch changes, and a subagent for reviewing them.

## What's included

### Command: `/qa-kit:summarize-changes`

Summarizes the changes on the current branch — lists each touched file with a
one-line description, formatted to paste straight into a pull-request
description.

### Subagent: `code-reviewer`

Reviews recently changed code for bugs, missing error handling, and unclear
names. Returns a short list grouped by severity (high, medium, low), with the
file and a one-sentence fix for each item. Claude reaches for this agent
automatically when asked to review recent changes.

## Usage

Load the plugin from the repo root:

```
claude --plugin-dir .
```

Run the command:

```
/qa-kit:summarize-changes
```

Trigger the subagent by asking Claude to review your recent changes — it will
invoke `code-reviewer`.

After editing plugin files, reload with `/reload-plugins`.
