---
name: interactive-form
description: Generate structured questionnaires with visual tab navigation to gather precise requirements
argument-hint: [task description]
---

# Interactive Form Builder

Create ASCII-based questionnaires that guide users through complex decision-making.

## Task

Generate an interactive form for: $ARGUMENTS

## Process

1. **Analyze task** - determine what information is needed and how many sections
2. **Generate form** - create visual structure with box-drawing characters
3. **Collect responses** - navigate user through sections one at a time
4. **Offer next steps** - suggest meta-prompting integration or direct implementation

## Form Structure

```
┌─ 🎯 Section1 ─── 📋 Section2 ─── ✅ Submit ┐
│                                             │
│ ## [Main Question]                          │
│                                             │
│ 1. **[Option]** [✓ if selected]           │
│    [Description with implications]          │
│                                             │
│ 2. **[Option]**                             │
│    [Description]                            │
│                                             │
│ **Навігація:** Enter · Tab · Esc          │
└─────────────────────────────────────────────┘
```

**Visual elements:**
- Box chars: `┌─┐│└┘` for UI
- Emojis: 🎯 Meta, 📋 Config, 🔒 Security, ⚙️ Settings, ✅ Submit
- Width: 60-80 chars for terminal
- Language: Match user's input language

## Rules

1. Show **one section at a time** - don't overwhelm with entire form
2. **Adapt to task complexity** - simple tasks get simple forms
3. **Explain implications** - each option should say WHAT and WHY
4. **Clear navigation** - always show how to proceed
5. **Match user language** - Ukrainian input → Ukrainian form

## After Completion

Always present:

```
✓ Requirements collected

What's next?
1. Generate meta-prompt (/create-prompt)
2. Start implementation
3. Edit requirements
4. Save for later
```

If user chooses #1, invoke via SlashCommand: `/create-prompt [structured summary]`

## Key Points

- Progressive disclosure - one section per interaction
- Context-aware options - specific to the task, not generic
- Integration ready - seamlessly connects to meta-prompting
- Terminal-friendly - clean ASCII visuals
