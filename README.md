# AI Learning Skills for Claude

> Transform your AI learning journey with structured curriculum and systematic knowledge capture

A collection of Claude skills designed to help developers learn AI/ML systematically while building real projects. Created by a frontend architect diving deep into AI development.

## 🎯 What This Is

Two powerful Claude skills that work together:

1. **ML Learning Journey** - A structured curriculum that guides you through AI/ML concepts progressively
2. **Learning Notes Generator** - Automatically creates searchable, revisable documentation of everything you learn

Instead of drowning in chat history, you build a searchable knowledge base that compounds over time.

## 🚀 Quick Start

### Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) installed
- A project you're building (learning works best when connected to real work)
- Git for version control (recommended but optional)
- **Required**: [ai-tutor skill](https://github.com/ShawhinT/ai-tutor-skill) - The ML Learning Journey uses this for concept explanations

### Installation

1. **Install the ai-tutor skill** (required dependency)
   ```bash
   # In your project directory
   mkdir -p .claude/skills/ai-tutor
   # Download SKILL.md from Shaw Talebi's repo
   curl -o .claude/skills/ai-tutor/SKILL.md \
     https://raw.githubusercontent.com/ShawhinT/ai-tutor-skill/main/SKILL.md
   ```

2. **Install the learning skills**
   ```bash
   # Clone this repo somewhere convenient
   git clone https://github.com/TanimaRanjan/ai-learning-skills.git /tmp/ai-learning-skills

   # Copy the skill files into your project
   mkdir -p .claude/skills/ml-learning-journey .claude/skills/learning-notes-generator
   cp /tmp/ai-learning-skills/ml-learning-journey/SKILL.md .claude/skills/ml-learning-journey/
   cp /tmp/ai-learning-skills/learning-notes-generator/SKILL.md .claude/skills/learning-notes-generator/
   ```

3. **Set up your learning notes repo** (recommended)
   ```bash
   mkdir -p concepts sessions exercises decisions quick-reference
   ```

Your project should now have:
```
your-project/
├── .claude/skills/
│   ├── ai-tutor/SKILL.md
│   ├── ml-learning-journey/SKILL.md
│   └── learning-notes-generator/SKILL.md
├── concepts/
├── sessions/
├── exercises/
├── decisions/
└── quick-reference/
```

### First Session

```
You: "I want to learn about embeddings for my [your project] project"

Claude: [Uses ML Learning Journey skill to teach you]

You: "Create a concept note for embeddings"

Claude: [Generates structured markdown note]

You: Save the note to concepts/embeddings.md
```

A week later:
```
You: [Upload concepts/embeddings.md to Claude]
"Quiz me on embeddings before I implement them"

Claude: [Uses your note to test understanding]
```

## 📚 What's Included

### ML Learning Journey Skill

A structured 24-week curriculum covering:

**Phase 1: LLM Foundations (Weeks 1-8)**
- Prompt Engineering Mastery
- RAG Architecture  
- Agentic Workflows
- Evaluation & Quality

**Phase 2: ML Fundamentals (Weeks 9-16)**
- Neural Networks Conceptually
- Transformers & Attention
- Fine-tuning vs RAG vs Prompting
- Model Evaluation Deep Dive

**Phase 3: Production ML Systems (Weeks 17-24)**
- LLM Observability
- Prompt Management & Testing
- Advanced RAG Patterns
- System Design for AI

**Key Features:**
- ✅ Adapts to your background (frontend, backend, data science, etc.)
- ✅ Socratic teaching method (asks questions, doesn't just give answers)
- ✅ Every concept connects to YOUR project
- ✅ Checks understanding before moving forward
- ✅ Adjusts pace based on your mastery

### Learning Notes Generator Skill

Transforms learning sessions into structured markdown notes with 5 templates:

**1. Concept Notes** - Core ideas (embeddings, RAG, transformers)
```markdown
# Embeddings

**Plain English Definition**: Numbers that capture meaning

**The Problem It Solves**: Computers understanding semantic similarity

**Concrete Example**: [From YOUR project]

**Practice Questions**: [For review]
```

**2. Session Summaries** - Multi-topic learning sessions

**3. Exercise Documentation** - Hands-on implementations with code

**4. Decision Records** - Architectural choices you make

**5. Quick References** - Checklists and debugging guides

**Key Features:**
- ✅ Consistent structure across all notes
- ✅ Plain English explanations (no unnecessary jargon)
- ✅ Examples from your actual project
- ✅ Practice questions for spaced repetition
- ✅ Links to related concepts
- ✅ Upload back to Claude for review/quizzing

## 💡 How It Works

### The Learning Loop

```
1. Learn Concept
   ↓
   [ML Learning Journey teaches with Socratic method]
   ↓
2. Generate Note
   ↓
   [Learning Notes Generator creates structured markdown]
   ↓
3. Apply to Project
   ↓
   [Build feature using what you learned]
   ↓
4. Document Application
   ↓
   [Update note with "Applied in My Project" section]
   ↓
5. Review Before Next Implementation
   ↓
   [Upload note to Claude for quiz/refresh]
   ↓
   Back to step 1
```

### Folder Structure

Your learning notes repo will look like:

```
ml-learning-notes/
├── concepts/
│   ├── embeddings.md
│   ├── rag-architecture.md
│   ├── prompt-engineering.md
│   └── transformers.md
├── sessions/
│   ├── 2024-02-01-intro-to-llms.md
│   └── 2024-02-15-rag-fundamentals.md
├── exercises/
│   ├── week-01-prompt-optimization/
│   │   ├── README.md
│   │   └── code/
│   └── week-02-basic-rag/
│       ├── README.md
│       └── code/
├── decisions/
│   └── 2024-02-20-why-rag-over-finetuning.md
└── quick-reference/
    ├── rag-debugging-checklist.md
    └── when-to-use-rag-vs-finetune.md
```

## 🎓 Learning Paths

### For Frontend Engineers
Start with LLM Foundations → focus on practical API usage → gradually build ML intuition

### For Backend Engineers  
Start with system design aspects → dive into RAG architecture → explore production patterns

### For Data Scientists
Skip basics → focus on production ML → explore LLM-specific patterns

### For Product Managers
High-level overview → decision frameworks → evaluation strategies

The skills adapt to your background automatically.

## 📖 Example Usage

### Learning a New Concept

```
You: "Let's start Module 1.2 on RAG architecture"

Claude: [Teaches RAG using Status Quo → Problem → Solution]
        [Shows concrete example from your project]
        [Asks you questions to build understanding]

You: "Create a concept note for RAG"

Claude: [Generates structured note with practice questions]

You: Save to concepts/rag-architecture.md
```

### Building Something

```
You: [Upload concepts/embeddings.md + concepts/rag-architecture.md]
     "I'm implementing retrieval for my project. Help me choose chunk size"

Claude: [Has context of what you learned]
        [Guides implementation based on your notes]

You: "Document this decision"

Claude: [Creates decision record explaining choice]

You: Save to decisions/2024-02-20-chunk-size-500.md
```

### Review Before Interview

```
You: [Upload all concept notes from concepts/]
     "Quiz me on LLM fundamentals for my interview tomorrow"

Claude: [Uses practice questions from your notes]
        [Tests understanding across concepts]
        [Identifies gaps to review]
```

## 🛠️ Customization

### Adapting the Curriculum

Edit `ml-learning-journey/SKILL.md` to:
- Add modules specific to your domain
- Adjust timeline (faster/slower)
- Focus on specific areas (skip what you know)
- Add your own exercises

### Customizing Note Templates

Edit `learning-notes-generator/SKILL.md` to:
- Change note structure
- Add custom sections
- Modify metadata fields
- Create new note types

### Integration with Other Tools

**Obsidian**: Notes work great in Obsidian with wiki-links

**Notion**: Import markdown notes for visual organization

**Anki**: Convert practice questions to flashcards

**VS Code**: Use as second brain with markdown preview

## 📝 Best Practices

### Do's ✅

- **Connect to real projects** - Every concept should apply to something you're building
- **Review regularly** - Upload notes back to Claude weekly
- **Update notes** - Add learnings from implementation to "Applied in My Project"
- **Link concepts** - Build a knowledge graph over time
- **Share with team** - Let others learn from your journey

### Don'ts ❌

- **Don't skip exercises** - Hands-on work is where learning sticks
- **Don't rush phases** - Master fundamentals before moving on
- **Don't just collect notes** - Review and apply them
- **Don't learn in isolation** - Use real projects, not toy examples
- **Don't treat Claude as Google** - Let it teach, not just answer

## 📄 License

MIT License - feel free to use, modify, and share

## 🙏 Acknowledgments

Built with Claude (Anthropic) as both the learning partner and the tool for creating these skills.

**Special thanks to:**
- [Shaw Talebi](https://github.com/ShawhinT) for the [`ai-tutor-skill`](https://github.com/ShawhinT/ai-tutor-skill) that inspired this project and powers the teaching methodology. The ML Learning Journey skill uses ai-tutor for all concept explanations.

Inspired by:
- Fast.ai's practical learning approach
- Andy Matuschak's "How to write good prompts"
- The Zettelkasten method for knowledge management
- Learning in public movement

## ⭐ If This Helped You

If these skills helped your AI learning journey:
- Star this repo ⭐
- Share your learning notes
- Write about your experience
- Help others get started

Learning in public compounds faster.

---

**Built by**: Tanima Ranjan 
**Created**: February 2026
**Last Updated**: March 2026

*"The best way to learn AI is to build AI-powered tools for your own workflows."*
