---
name: learning-notes-generator
description: Use after teaching sessions or concept explanations to generate structured markdown notes for the user's knowledge base. Triggers include "create a note", "summarize what we learned", "generate documentation for this session", or "save this as a concept note". Produces searchable, Claude-friendly documentation that can be uploaded back for future reference.
---

# Learning Notes Generator

Transforms learning sessions into structured, searchable markdown notes optimized for revision and future Claude conversations.

## Core Principles

1. **Consistent Structure**: Every note follows the same template for easy scanning
2. **Plain English First**: No jargon in definitions - save technical terms for details
3. **Project-Connected**: Always include concrete examples from user's actual work
4. **Future-Proof**: Notes should make sense 6 months later without context
5. **Claude-Friendly**: Formatted so user can upload back to Claude for review/quiz

## Note Types

### Type 1: Concept Note
For core ideas, techniques, or theories (e.g., "embeddings", "RAG architecture", "attention mechanism")

### Type 2: Session Summary
For learning sessions covering multiple topics (e.g., "Week 3: Building RAG Systems")

### Type 3: Exercise Documentation
For hands-on work and implementations (e.g., "Exercise: Building a Query Classifier")

### Type 4: Decision Record
For architectural or approach decisions (e.g., "Why I Chose RAG Over Fine-tuning")

### Type 5: Quick Reference
For checklists, decision trees, or debugging guides (e.g., "RAG Debugging Checklist")

---

## Templates

### Template 1: Concept Note

```markdown
# [Concept Name]

**Created**: [Date]
**Related Concepts**: [Links to other notes, if applicable]
**Learning Phase**: [e.g., "Phase 1 - Module 1.2"]

---

## Plain English Definition

[One to two sentences explaining what this is without any jargon]

---

## The Problem It Solves

[Explain what problem existed before this concept, or what gap it fills]

**Status Quo**: [What people did before]
**Limitation**: [Why that wasn't good enough]
**Solution**: [How this concept addresses it]

---

## How It Works

[Step-by-step explanation in plain English]

1. [First key step or component]
2. [Second key step or component]
3. [Third key step or component]

[Add a simple diagram or flowchart if helpful - use ASCII art or mermaid]

---

## Concrete Example

[Specific example from the user's project with actual details]

**Scenario**: [Describe the use case]
**Implementation**: [Show how the concept applies]
**Result**: [What happened / what improved]

---

## When to Use This

✅ **Use when**:
- [Condition 1]
- [Condition 2]
- [Condition 3]

❌ **Don't use when**:
- [Condition 1]
- [Condition 2]
- [Condition 3]

---

## Common Pitfalls

**Pitfall 1: [Name]**
- What it is: [Description]
- How to avoid: [Solution]

**Pitfall 2: [Name]**
- What it is: [Description]
- How to avoid: [Solution]

---

## Key Tradeoffs

| Aspect | Benefit | Cost |
|--------|---------|------|
| [Aspect 1] | [What you gain] | [What you lose] |
| [Aspect 2] | [What you gain] | [What you lose] |

---

## Technical Details

[Optional section for deeper technical understanding - can skip for high-level concepts]

**Parameters/Configuration**:
- [Key parameter 1]: [What it does]
- [Key parameter 2]: [What it does]

**Under the Hood**:
- [How it actually works technically]

---

## Related Concepts

- **[Concept 1]** (`path/to/note.md`): [How it relates]
- **[Concept 2]** (`path/to/note.md`): [How it relates]
- **[Concept 3]** (`path/to/note.md`): [How it relates]

---

## Practice Questions

1. [Question that tests understanding of core concept]
2. [Question that tests application ability]
3. [Scenario-based question using user's project]

<details>
<summary>Answers</summary>

1. [Answer to question 1]
2. [Answer to question 2]
3. [Answer to question 3]

</details>

---

## Applied in My Project

**Where I used this**: 
[User fills this in]

**Results**:
[User fills this in]

**Lessons learned**:
[User fills this in]

---

## Resources

- [Link to documentation]
- [Tutorial or guide]
- [Relevant paper or article]

---

## Revision History

- [Date]: Initial note created
- [Date]: Updated with [what changed]
```

---

### Template 2: Session Summary

```markdown
# Session [NNN]: [Title]

**Session Number**: [NNN] (sequential, zero-padded)
**Date**: [Date]
**Duration**: [Time spent]
**Learning Phase**: [e.g., "Phase 1 - Module 1.2"]
**File**: `sessions/session-[NNN]-[topic-slug].md`

---

## Goals for This Session

- [Goal 1]
- [Goal 2]
- [Goal 3]

---

## Concepts Covered

### 1. [Concept Name]

**What it is**: [Brief plain English explanation]

**Key insight**: [The "aha" moment or main takeaway]

**Application**: [How it applies to user's project]

→ *Full notes*: `concepts/[concept-name].md`

### 2. [Concept Name]

[Same structure]

### 3. [Concept Name]

[Same structure]

---

## Hands-On Work

**What we built**:
[Description of exercise or implementation]

**Code/Files**:
- [File or directory path]
- [What's in it]

**Results**:
- [What worked]
- [What didn't work]
- [What surprised me]

---

## Key Takeaways

1. [Most important learning from session]
2. [Second most important learning]
3. [Third most important learning]

---

## Questions / Confusion

- [ ] [Unresolved question 1]
- [ ] [Unresolved question 2]
- [ ] [Thing I need to review]

---

## Next Steps

- [ ] [Action item 1]
- [ ] [Action item 2]
- [ ] [Homework before next session]

---

## Next Session Plan

**Session [N+1]**: [What will be covered next]
**Module**: [e.g., "Phase 1 - Module 1.3: Agentic Workflows"]
**Prerequisites**: [Anything to complete before next session]

---

## Connections Made

[How today's learning connects to previous sessions or concepts]

- Today's concept of [X] explains why [Y] works the way it does
- This connects to [previous concept] because [relationship]

---

## Personal Reflections

**What went well**:
[User's notes]

**What was challenging**:
[User's notes]

**Energy level**: [1-5]
**Confidence level**: [1-5]
```

---

### Template 3: Exercise Documentation

```markdown
# Exercise: [Title]

**Completed**: [Date]
**Time Spent**: [Duration]
**Related Concepts**: [Links to concept notes]
**Learning Phase**: [e.g., "Phase 1 - Module 1.2"]

---

## Objective

[What this exercise was meant to teach or achieve]

---

## The Task

[Clear description of what needed to be built/done]

**Requirements**:
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

---

## My Approach

[Explain the strategy taken]

**Why I chose this approach**:
[Reasoning]

---

## Implementation

**Code Location**: `path/to/code/`

**Key Files**:
- `file1.py`: [What it does]
- `file2.py`: [What it does]

**Architecture**:
```
[Simple diagram or flowchart of how it works]
```

---

## Code Highlights

**Most important pattern**:
```python
# Brief code snippet with explanation
```

**Interesting technique**:
```python
# Another snippet
```

---

## Results

**What worked**:
- [Success 1]
- [Success 2]

**What didn't work**:
- [Problem 1]: [Why it failed]
- [Problem 2]: [Why it failed]

**Metrics** (if applicable):
- Accuracy: [X%]
- Latency: [X ms]
- Cost: [$X]

---

## Debugging Stories

**Problem**: [Issue encountered]
**Hypothesis**: [What I thought was wrong]
**Investigation**: [What I tried]
**Solution**: [What actually fixed it]
**Learning**: [What I learned from this]

---

## Improvements Made

| Version | Change | Result |
|---------|--------|--------|
| v1 | [Initial approach] | [Outcome] |
| v2 | [Changed X to Y] | [Improved by Z] |
| v3 | [Final optimization] | [Final result] |

---

## Concepts Applied

- **[Concept 1]** (`concepts/concept1.md`): [How I used it]
- **[Concept 2]** (`concepts/concept2.md`): [How I used it]

---

## Lessons Learned

1. [Most important lesson]
2. [Second lesson]
3. [Third lesson]

**Would do differently next time**:
- [Change 1]
- [Change 2]

---

## Next Steps

- [ ] [How to improve this]
- [ ] [What to build on top of this]
- [ ] [Related exercise to try]
```

---

### Template 4: Decision Record

```markdown
# Decision: [Decision Title]

**Date**: [Date]
**Status**: [Decided / Under Review / Superseded]
**Context**: [Project or feature this applies to]

---

## The Question

[What decision needed to be made]

---

## Options Considered

### Option 1: [Name]

**Description**: [What this approach entails]

**Pros**:
- [Benefit 1]
- [Benefit 2]
- [Benefit 3]

**Cons**:
- [Drawback 1]
- [Drawback 2]
- [Drawback 3]

**Estimated Cost**: [Time/Money/Complexity]

### Option 2: [Name]

[Same structure]

### Option 3: [Name]

[Same structure]

---

## Decision

**Chose**: [Which option]

**Reasoning**:
[Detailed explanation of why this was chosen over alternatives]

**Key factors**:
1. [Most important factor]
2. [Second most important factor]
3. [Third most important factor]

---

## Tradeoffs Accepted

[What we gave up by choosing this option]

- [Tradeoff 1]: [Why it's acceptable]
- [Tradeoff 2]: [Why it's acceptable]

---

## Implementation Plan

1. [First step]
2. [Second step]
3. [Third step]

**Timeline**: [Expected duration]

---

## Success Metrics

How we'll know this decision was right:
- [Metric 1]: [Target]
- [Metric 2]: [Target]
- [Metric 3]: [Target]

---

## Review Date

[When to revisit this decision]: [Date]

**What might change our mind**:
- [Condition 1]
- [Condition 2]

---

## Related Concepts

- [Concept that informed this decision]: `path/to/note.md`

---

## Updates

- [Date]: [What changed and why]
```

---

### Template 5: Quick Reference

```markdown
# Quick Reference: [Title]

**Last Updated**: [Date]
**Use Case**: [When to pull out this reference]

---

## Checklist: [Name]

Use this when [scenario]:

- [ ] [Step 1]
- [ ] [Step 2]
- [ ] [Step 3]
- [ ] [Step 4]

---

## Decision Tree: [Name]

```
Is [condition A] true?
├─ Yes → [Action 1]
│   └─ Is [sub-condition] true?
│       ├─ Yes → [Action 2]
│       └─ No → [Action 3]
└─ No → [Action 4]
    └─ Is [other condition] true?
        ├─ Yes → [Action 5]
        └─ No → [Action 6]
```

---

## Common Commands

**[Task Name]**:
```bash
# Command with explanation
command --flag value
```

**[Another Task]**:
```python
# Python snippet
code_example()
```

---

## Debugging Guide

**Problem**: [Common issue]
**Check**:
1. [First thing to verify]
2. [Second thing to verify]
3. [Third thing to verify]

**Problem**: [Another common issue]
**Check**:
[Same structure]

---

## Parameter Reference

| Parameter | Default | Range | Effect |
|-----------|---------|-------|--------|
| [param1] | [value] | [range] | [what it does] |
| [param2] | [value] | [range] | [what it does] |

---

## Common Patterns

**Pattern 1: [Name]**
```
[Code or pseudocode]
```
Use when: [Scenario]

**Pattern 2: [Name]**
```
[Code or pseudocode]
```
Use when: [Scenario]
```

---

## Note Generation Guidelines

### When User Says: "Create a note" or "Summarize this session"

1. **Determine Note Type**:
   - Single concept discussed → Concept Note
   - Multiple topics in one session → Session Summary
   - Built/implemented something → Exercise Documentation
   - Made architectural decision → Decision Record
   - Need quick lookup → Quick Reference

2. **Gather Information**:
   - Review the conversation for key points
   - Identify concrete examples from user's project
   - Note any code snippets or implementations
   - Extract key decisions or tradeoffs
   - Identify connections to previous learning

3. **Generate the Note**:
   - Use the appropriate template
   - Fill in all sections with relevant information
   - Use plain English in definitions
   - Include specific details (numbers, names, real examples)
   - Add practice questions that test understanding
   - Leave "Applied in My Project" section for user to fill

4. **Suggest File Path**:
   - Concept notes → `concepts/[concept-name].md`
   - Session summaries → `sessions/session-[NNN]-[topic].md` (zero-padded, sequential — check existing files to determine next number)
   - Exercises → `exercises/[date]-[name]/README.md`
   - Decisions → `decisions/[date]-[decision].md`
   - Quick refs → `quick-reference/[topic].md`

5. **Add Metadata**:
   - Date created
   - Learning phase/module
   - Related concepts with file paths
   - Links to code or other resources

### Format Requirements

**Plain English Definitions**:
- ❌ "Vector embeddings are dense numerical representations in continuous vector space"
- ✅ "Embeddings are numbers that capture the meaning of words or sentences, where similar meanings have similar numbers"

**Concrete Examples**:
- ❌ "You could use this for documents"
- ✅ "For our product catalog, we embedded 500 item descriptions. When a user asks 'lightweight running shoes', we find products with embedding numbers close to that query's numbers"

**Actionable Content**:
- Every section should be useful for future reference
- No filler or generic statements
- Specific enough to jog memory 6 months later

**Claude-Friendly**:
- Structured so user can upload back to Claude
- Practice questions Claude can use for quizzing
- Links that Claude can reference for context

### Special Handling

**If User Built Code**:
- Always create Exercise Documentation
- Include actual file paths
- Show key code snippets
- Document what worked and what didn't

**If Multiple Concepts**:
- Create Session Summary as main note
- Generate individual Concept Notes for each major topic
- Link them together

**If Decision Was Made**:
- Create Decision Record
- Document all options considered
- Be explicit about tradeoffs

**If User Seems Confused**:
- Focus on Plain English Definition section
- Add extra examples
- Create practice questions at multiple difficulty levels
- Suggest review checkpoints

### Response Format

When generating notes, respond with:

1. **Brief intro**: "I've created a [note type] for [topic]. Here's the structured note you can save:"

2. **The complete note** using appropriate template

3. **Suggested file path**: "Save this as: `[path/to/file.md]`"

4. **Optional next steps**:
   - "Want me to create separate concept notes for [X] and [Y]?"
   - "Should I generate practice questions for review?"
   - "Ready to quiz you on this to check understanding?"

### Integration with Other Skills

**With ml-learning-journey**:
- Auto-generate notes at end of each module
- Create session summaries after teaching sessions
- Document all exercises and implementations

**With ai-tutor**:
- After explaining concepts, offer to generate note
- Use same narrative structures in notes
- Maintain plain English focus

---

## Example Usage

**User**: "We just covered embeddings and RAG. Can you create a note for embeddings?"

**Claude**: 
"I've created a Concept Note for embeddings. Here's the structured note you can save:

[Full Concept Note following Template 1]

**Save this as**: `concepts/embeddings.md`

Want me to also create a concept note for RAG architecture, or a session summary covering both topics?"

---

**User**: "Summarize today's session"

**Claude**:
"I've created a Session Summary for today's learning on RAG systems. Here's the note:

[Full Session Summary following Template 2]

**Save this as**: `sessions/2024-02-15-rag-fundamentals.md`

I also noticed we covered embeddings and chunking strategies in depth. Want me to create separate concept notes for those?"

---

**User**: "Document the RAG implementation we just built"

**Claude**:
"I've created Exercise Documentation for your RAG implementation:

[Full Exercise Doc following Template 3]

**Save this as**: `exercises/2024-02-15-basic-rag/README.md`

I can also create a decision record for why you chose chunk size 500 if you want to document that choice."

---

## Quality Checks

Before delivering a note, verify:

- ✅ Plain English definition is jargon-free
- ✅ Concrete example uses user's actual project
- ✅ Practice questions test understanding, not memorization
- ✅ All sections are filled (no TODO placeholders)
- ✅ File path suggestion is clear
- ✅ Links to related concepts included
- ✅ Tradeoffs section shows both sides
- ✅ "Applied in My Project" section left for user
- ✅ Date and metadata included

---

## Advanced Features

### Cross-Referencing

When creating notes, automatically:
- Link to related concept notes
- Reference relevant exercises
- Connect to decision records
- Build knowledge graph over time

### Versioning

Notes can be updated:
- Add "Revision History" section
- Document what changed and why
- Keep old insights intact
- Show learning progression

### Review Prompts

Generate review materials:
- Spaced repetition schedule
- Practice question sets
- Concept maps showing relationships
- Progress tracking checklists
