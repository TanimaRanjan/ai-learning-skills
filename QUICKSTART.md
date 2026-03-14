# Quick Setup Guide

Get started with AI Learning Skills in 5 minutes.

## Step 1: Install Skills into Your Project

1. **First, install the ai-tutor skill** (required)
   ```bash
   # In your project directory
   mkdir -p .claude/skills/ai-tutor
   curl -o .claude/skills/ai-tutor/SKILL.md \
     https://raw.githubusercontent.com/ShawhinT/ai-tutor-skill/main/SKILL.md
   ```

2. **Then install these skills**
   ```bash
   # Clone and copy skill files
   git clone https://github.com/TanimaRanjan/ai-learning-skills.git /tmp/ai-learning-skills
   mkdir -p .claude/skills/ml-learning-journey .claude/skills/learning-notes-generator
   cp /tmp/ai-learning-skills/ml-learning-journey/SKILL.md .claude/skills/ml-learning-journey/
   cp /tmp/ai-learning-skills/learning-notes-generator/SKILL.md .claude/skills/learning-notes-generator/
   ```

That's it! The skills are now available when you run `claude` in your project directory.

## Step 2: Set Up Your Notes Folder (Optional but Recommended)

```bash
# Create folder structure in your project
mkdir -p concepts sessions exercises decisions quick-reference
```

## Step 3: Start Learning

Open Claude Code and say:

```
I want to learn about embeddings for my [describe your project] project
```

Claude will use the ML Learning Journey skill to teach you.

After learning, say:

```
Create a concept note for embeddings
```

Claude will generate a structured note. Save it to `concepts/embeddings.md`.

## Step 4: Review and Build

Later, when implementing:

1. Upload your concept notes to Claude
2. Ask for help with implementation
3. Claude will have context of what you learned

Example:
```
[Upload concepts/embeddings.md]

I'm implementing semantic search now. Help me choose the right embedding model.
```

## Tips for Success

**Start Small**: Don't try to learn everything at once. Pick one module and master it.

**Apply Immediately**: Build something with each concept you learn.

**Review Weekly**: Upload your notes and ask Claude to quiz you.

**Share with Team**: Your notes can help teammates learn too.

## Need Help?

- Check the [main README](README.md) for detailed docs
- See [example notes](examples/) to understand the format
- Open an [issue](https://github.com/TanimaRanjan/ai-learning-skills/issues) if stuck

---

**Next Steps:**
- Read the [full documentation](README.md)
- Check out [example notes](examples/)
- Start with [Module 1.1: Prompt Engineering](ml-learning-journey/SKILL.md)
