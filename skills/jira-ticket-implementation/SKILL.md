---
name: jira-ticket-implementation
description: Use when implementing a JIRA ticket, working from a ticket reference like ABC-64 or DE-352, or when the user mentions a JIRA ticket to implement
---

# JIRA Ticket Implementation

## Overview

Structured workflow for implementing work from a JIRA ticket, typically involving design references and acceptance criteria.

**Core principle:** Read the ticket fully before writing code. Understand the acceptance criteria and design intent.

## When to Use

- User says "implement JIRA ticket X"
- User references a ticket ID (e.g., FGH-64, XY-352)
- User pastes ticket contents with implementation requirements

## Workflow

1. **Read the ticket** via `acli jira workitem view TICKET-ID`
2. **Review design references** — ask the user for Figma screenshots if mentioned
3. **Explore existing code** — find relevant files, patterns, and conventions
4. **Ensure the base branch is up to date** - avoid merge conflicts via git fetch/pull
5. **Set up branch** - the branch name usually takes the form of `ABC-123/branch-title`, aka the JIRA ticket ID, followed by a brief title.
6. **Implement** — follow project conventions and existing patterns
7. **Lint** — run project linters ( e.g. `composer run lint`, `npm run lint:js`, etc.)
8. **Test** — run test suite if available
9. **Commit** — when user approves, all commits begin with the JIRA ticket ID, e.g. `ABC-123: Implement feature`

## Reading JIRA Tickets

```bash
acli jira workitem view ABC-64
```

If the ticket references a design, ask the user to share Figma or screenshots before starting implementation. If acli is not present/authenticated/installed ask the user for an export of the ticket as a PDF.

## Implementation Checklist

- [ ] Read ticket and understand acceptance criteria
- [ ] Review Figma/design if referenced
- [ ] Check for existing patterns in codebase to follow
- [ ] Ensure main branch is up to date with remote
- [ ] Set up feature branch
- [ ] Implement using project conventions
- [ ] Run linters (check project for available lint commands)
- [ ] Run tests if available
- [ ] Wait for user approval before committing

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Starting implementation without reading the full ticket | Always read ticket first |
| Guessing design details | Ask for Figma screenshots |
| Ignoring existing code patterns | Explore neighbouring files first |
| Committing without user approval | Always wait for explicit approval |
| Skipping lint step | Run all available linters before declaring done |
