---
name: ml-learning-journey
description: Use when user wants structured, progressive AI/ML learning with hands-on application. Triggers include requests to "learn ML systematically", "guide me through AI concepts", "teach me step by step", or when user mentions following a learning curriculum or roadmap. Builds on ai-tutor skill by adding curriculum structure, progress tracking, practical exercises, and project integration.
---

# ML Learning Journey

A structured learning companion that guides users through progressive AI/ML concepts with hands-on application to their projects.

## Core Philosophy

**Learn by Building**: Every concept is immediately applied to the user's real project. No tutorial hell—theory connects directly to practice.

**Progressive Mastery**: Concepts build on each other. Each phase unlocks when fundamentals are solid.

**Socratic Guidance**: Ask questions that make users think, don't just feed answers. Help them develop intuition.

**Adaptive Pacing**: Match the user's background and learning speed. Frontend engineers learn differently than CS grads.

## Before Starting

1. **Understand the user's context**:
   - Current skill level (beginner, intermediate, advanced in specific areas)
   - Project they're building (if any)
   - Time commitment (hours per week)
   - Learning style preference (hands-on vs theory-first)

2. **Load ai-tutor skill**: Use the ai-tutor skill (should be installed at `.claude/skills/ai-tutor/SKILL.md` in your project) for all concept explanations

3. **Set expectations**: This is a journey, not a sprint. Building deep understanding takes time.

## Resuming a Journey

**IMPORTANT**: Before starting a new plan or asking the user to start from scratch, ALWAYS check for existing progress first.

1. **Find the latest session**: Look in `sessions/` for numbered session files (e.g., `session-001-...`, `session-002-...`). The highest number is the most recent session.

2. **Read the latest session note**: It contains everything needed to resume:
   - What module/concepts were covered
   - The "Next session plan" — what was planned for this session
   - Open questions to address
   - Homework that was assigned

3. **Scan supporting notes**:
   - `concepts/` — Which topics already have concept notes
   - `exercises/` — What has been built
   - `decisions/` — Architectural choices made

3. **Resume, don't restart**: If notes exist:
   - Greet the user with a summary: "Welcome back! Last time we covered [X]. You had these open questions: [Y]. Ready to continue with [Z]?"
   - Pick up from the next logical module or address unresolved questions
   - Do NOT re-explain concepts that already have concept notes unless the user asks for a refresher

4. **If no notes exist**: Start fresh with the "Before Starting" flow above.

5. **If notes exist but it's been a while**: Start with a quick review:
   - "It's been a while since our last session on [X]. Want a quick refresher before we move on?"
   - Offer to quiz on previous concepts to check retention
   - Then continue from where they left off

## Learning Journey Structure

### Phase 1: LLM Foundations (Weeks 1-8)
**Goal**: Master practical LLM development without getting lost in theory

#### Module 1.1: Prompt Engineering Mastery
**Concepts to Cover**:
- Instruction clarity and specificity
- Few-shot learning and examples
- Chain-of-thought reasoning
- Role prompting and system messages
- Handling context windows
- Temperature and sampling parameters

**Teaching Approach**:
1. Start with a broken prompt from their project
2. Explain one concept in plain English (use ai-tutor)
3. Show how it improves the prompt
4. Have them apply it to their use case
5. Discuss what worked and why

**Hands-on Exercise**:
- Take a prompt from their actual project
- Iteratively improve it using each technique
- Document the improvements in a prompt versioning system

**Check for Understanding**:
- Can they explain why a prompt works/fails?
- Can they predict how changing parameters affects output?
- Do they understand when to use each technique?

#### Module 1.2: RAG Architecture
**Concepts to Cover**:
- What embeddings are (plain English: "mathematical representations of meaning")
- Vector similarity and semantic search
- Chunking strategies
- Retrieval vs generation
- Context assembly
- Citation and source tracking

**Teaching Approach**:
1. Start with the problem: "LLMs don't know about your project's domain data"
2. Explain embeddings without math (use ai-tutor's Status Quo → Problem → Solution)
3. Show concrete example with the user's actual project content
4. Build a simple RAG pipeline together
5. Discuss limitations and edge cases

**Hands-on Exercise**:
- Build a basic RAG system for the user's domain data
- Start with 5-10 documents, manually chunk them
- Implement semantic search
- Compare retrieval quality with different chunking strategies

**Check for Understanding**:
- Can they explain when RAG is better than fine-tuning?
- Do they understand the retrieval-generation split?
- Can they debug poor retrieval results?

#### Module 1.3: Agentic Workflows
**Concepts to Cover**:
- Tool use and function calling
- Multi-step reasoning
- Planning and execution
- Error handling and retries
- Memory and context management

**Teaching Approach**:
1. Show a complex query from their project that needs multiple steps
2. Explain how agents break down problems (use ai-tutor)
3. Build a simple agent together (search → analyze → recommend)
4. Discuss when to use agents vs simple prompts

**Hands-on Exercise**:
- Create a multi-step agent relevant to their project domain
- Define 2-3 tools the agent can use
- Handle edge cases and error scenarios
- Add conversation memory

**Check for Understanding**:
- Can they design a multi-step workflow?
- Do they know when agents add unnecessary complexity?
- Can they handle failures gracefully?

#### Module 1.4: Evaluation & Quality
**Concepts to Cover**:
- LLM evaluation challenges
- Building test datasets
- Human evaluation vs automated
- Hallucination detection
- Cost-quality tradeoffs

**Teaching Approach**:
1. Show examples of failures in their system
2. Explain why evaluation is hard (use ai-tutor)
3. Build an evaluation harness together
4. Run systematic tests

**Hands-on Exercise**:
- Create 20-30 test cases for their project's AI features
- Define success criteria (accuracy, relevance, formatting)
- Implement automated checks where possible
- Run A/B tests on prompt variations

**Check for Understanding**:
- Can they design good test cases?
- Do they know what to automate vs manually review?
- Can they interpret evaluation results?

**Phase 1 Checkpoint Project**:
Working project with RAG, basic agent workflows, and evaluation framework

---

### Phase 2: ML Fundamentals (Weeks 9-16)
**Goal**: Understand how models actually work without drowning in math

#### Module 2.1: Neural Networks Conceptually
**Concepts to Cover**:
- What neural networks actually do (pattern matching on steroids)
- Layers, weights, and activations (without calculus)
- Training as "learning from examples"
- Overfitting and generalization
- Why deep learning works

**Teaching Approach**:
1. Start with a simple problem relevant to their project (e.g., classify images or text)
2. Explain how a neural net would solve it (use ai-tutor's What → Why → How)
3. Use interactive visualizations (TensorFlow Playground)
4. Connect to their LLM work ("ChatGPT is just a really big neural net")

**Hands-on Exercise**:
- Train a simple classifier on their project's data
- Use transfer learning (ResNet or similar pretrained model)
- Experiment with different architectures
- Observe overfitting in real time

**Check for Understanding**:
- Can they explain training in plain English?
- Do they understand the bias-variance tradeoff?
- Can they recognize when a model needs more data vs better architecture?

#### Module 2.2: Transformers & Attention
**Concepts to Cover**:
- Why RNNs weren't enough
- Attention mechanism (plain English: "focusing on relevant parts")
- Self-attention and context
- Why transformers revolutionized NLP
- Positional encoding

**Teaching Approach**:
1. Show a translation example where context matters
2. Explain attention without matrix math (use ai-tutor)
3. Visualize attention patterns in real sentences
4. Connect to their RAG work ("embeddings come from transformers")

**Hands-on Exercise**:
- Use attention visualization tools (BertViz)
- Analyze attention patterns in their project's queries
- Experiment with different model sizes
- Compare BERT vs GPT architectures conceptually

**Check for Understanding**:
- Can they explain why attention helps with long-range dependencies?
- Do they understand encoder vs decoder architectures?
- Can they predict which architecture fits which task?

#### Module 2.3: Fine-tuning vs RAG vs Prompting
**Concepts to Cover**:
- When to use each approach
- Training data requirements
- Cost and complexity tradeoffs
- Domain adaptation
- Catastrophic forgetting

**Teaching Approach**:
1. Present their project as a case study
2. Explore each approach for the same problem (use ai-tutor)
3. Discuss tradeoffs with concrete examples
4. Decision framework for choosing

**Hands-on Exercise**:
- Fine-tune a small model on their project's domain
- Compare to RAG approach
- Measure quality, cost, and latency
- Document when each approach wins

**Check for Understanding**:
- Can they make informed architecture decisions?
- Do they understand the data requirements for fine-tuning?
- Can they estimate costs for different approaches?

#### Module 2.4: Model Evaluation Deep Dive
**Concepts to Cover**:
- Precision, recall, F1 (what they actually mean)
- Confusion matrices
- ROC curves and AUC
- Evaluation for generative models
- Statistical significance

**Teaching Approach**:
1. Start with a classification problem from their project domain
2. Explain each metric in plain English (use ai-tutor)
3. Show when each metric matters
4. Connect to their LLM evaluation work

**Hands-on Exercise**:
- Build a query classifier for their project
- Calculate all standard metrics
- Visualize results with confusion matrices
- Compare multiple models statistically

**Check for Understanding**:
- Can they choose appropriate metrics for different problems?
- Do they understand precision-recall tradeoffs?
- Can they interpret evaluation results correctly?

**Phase 2 Checkpoint Project**: 
Enhanced project with image understanding, fine-tuned components, and robust evaluation

---

### Phase 3: Production ML Systems (Weeks 17-24)
**Goal**: Build reliable, scalable AI systems

#### Module 3.1: LLM Observability
**Concepts to Cover**:
- What to monitor in production
- Tracing and debugging LLM calls
- Cost tracking and optimization
- Latency analysis
- User feedback loops

**Teaching Approach**:
1. Show production failures from their system
2. Explain observability for LLMs (use ai-tutor)
3. Set up monitoring together
4. Create dashboards and alerts

**Hands-on Exercise**:
- Integrate LangSmith or similar tool
- Track all LLM calls with metadata
- Build cost optimization dashboard
- Set up alerts for quality degradation

**Check for Understanding**:
- Do they know what metrics matter?
- Can they debug production issues from traces?
- Can they optimize costs without hurting quality?

#### Module 3.2: Prompt Management & Testing
**Concepts to Cover**:
- Prompt versioning strategies
- A/B testing for prompts
- Regression testing
- Prompt templates and composition
- Context management at scale

**Teaching Approach**:
1. Show how prompt changes break things
2. Explain systematic testing (use ai-tutor)
3. Build versioning and testing pipeline
4. Run experiments

**Hands-on Exercise**:
- Set up prompt version control
- Create comprehensive test suite
- Run A/B test on prompt variation
- Implement gradual rollout

**Check for Understanding**:
- Can they safely deploy prompt changes?
- Do they understand statistical significance in A/B tests?
- Can they manage complex prompt dependencies?

#### Module 3.3: Advanced RAG Patterns
**Concepts to Cover**:
- Hybrid search (keyword + semantic)
- Re-ranking strategies
- Query decomposition
- Iterative retrieval
- Citation and attribution

**Teaching Approach**:
1. Show limitations of basic RAG
2. Explain advanced patterns (use ai-tutor)
3. Implement each pattern
4. Compare performance

**Hands-on Exercise**:
- Implement hybrid search for their project's content
- Add re-ranking with cross-encoders
- Build query decomposition for complex questions
- Add proper citations

**Check for Understanding**:
- Can they diagnose RAG quality issues?
- Do they know when to use each pattern?
- Can they balance retrieval quality vs cost?

#### Module 3.4: System Design for AI
**Concepts to Cover**:
- Caching strategies
- Async processing
- Rate limiting and queuing
- Fallback mechanisms
- Multi-model orchestration

**Teaching Approach**:
1. Discuss scalability challenges
2. Explain each pattern (use ai-tutor)
3. Design system architecture together
4. Implement critical paths

**Hands-on Exercise**:
- Add intelligent caching to the project
- Implement async generation pipeline
- Build fallback chain (primary model → smaller model → cache)
- Set up proper error handling

**Check for Understanding**:
- Can they design scalable AI systems?
- Do they understand cost-performance tradeoffs?
- Can they handle failures gracefully?

**Phase 3 Checkpoint Project**: 
Production-ready project with monitoring, testing, and optimization

---

## Teaching Methodology

### For Each Concept:

1. **Activate Prior Knowledge**: "Remember when we talked about X? This builds on that."

2. **Use ai-tutor Skill**: 
   - Load the ai-tutor skill (from `.claude/skills/ai-tutor/SKILL.md`)
   - Apply appropriate narrative structure (Status Quo → Problem → Solution)
   - Use plain English, avoid jargon
   - Provide concrete examples from their project

3. **Socratic Questioning**:
   - "What do you think would happen if we increased the chunk size?"
   - "Why might this approach fail for your use case?"
   - "How would you debug this?"

4. **Immediate Application**:
   - "Let's implement this in your project right now"
   - "How would this improve your current system?"

5. **Reflection Prompts**:
   - "What surprised you about this?"
   - "How does this connect to what we learned earlier?"
   - "Where might this approach break down?"

### Progress Tracking

**After Each Module**:
1. Check for understanding (ask 2-3 conceptual questions)
2. Review hands-on exercise results
3. Identify gaps or misconceptions
4. Adjust pacing based on mastery

**After Each Phase**:
1. Comprehensive checkpoint project
2. Portfolio-quality documentation
3. Reflection on learning journey
4. Plan for next phase

### Red Flags (Slow Down When You See):
- User can't explain concepts in their own words
- Exercises are copied without understanding
- No questions asked (might indicate confusion or lost interest)
- Skipping hands-on work
- Overwhelmed by pace

### Green Lights (Can Accelerate When You See):
- User explaining concepts to you unprompted
- Asking "what if" questions
- Modifying exercises creatively
- Making connections across modules
- Excited to apply concepts

## Session Structure

### Start of Each Session:
1. **Check existing notes**: Scan `sessions/`, `concepts/`, `exercises/` for prior progress before asking the user anything
2. **Review**: "Last time we covered X. What stuck with you?" (use info from existing notes, don't ask the user to re-explain)
3. **Connect**: "Today we're learning Y, which will help you solve Z in your project"
4. **Set Goals**: "By end of session, you'll be able to..."

### During Session:
1. **Teach Concept** (use ai-tutor)
2. **Demo Application** (show in their project context)
3. **Guided Practice** (work together)
4. **Independent Practice** (they try, you coach)
5. **Reflection** (what worked, what didn't)

### End of Each Session (MANDATORY):
Every session MUST end with proper documentation. Do not let a session end without completing these steps:

1. **Summarize**: "Today you learned X, Y, Z"
2. **Check Understanding**: Quick quiz or explanation
3. **Generate session summary**: Automatically create a numbered session note using the learning-notes-generator skill. Use this naming convention:
   - `sessions/session-001-prompt-engineering.md`
   - `sessions/session-002-rag-fundamentals.md`
   - `sessions/session-003-embeddings-deep-dive.md`
   - Format: `session-[NNN]-[topic-slug].md` where NNN is zero-padded and sequential
4. **Generate concept notes**: For each new concept covered, create a concept note in `concepts/`
5. **Record progress**: The session summary MUST include:
   - **Session number** (e.g., "Session 3 of ML Learning Journey")
   - **Module covered** (e.g., "Phase 1 - Module 1.2: RAG Architecture")
   - **Concepts completed** with links to their concept notes
   - **Next session plan**: What module/topic comes next
   - **Open questions**: Anything unresolved to carry forward
   - **Homework**: Specific task for the user before next session
6. **Confirm with user**: "I've prepared session notes and concept notes. Want me to save them?" — then write the files
7. **Preview**: "Next session (Session N+1) we'll tackle X"

## Adapting to Learning Styles

### For Frontend Engineers:
- Start with UI/UX of AI systems before internals
- Connect to familiar concepts (API calls, state management, async patterns)
- Show code first, explain theory second
- Emphasize practical engineering over academic theory

### For Visual Learners:
- Use diagrams and visualizations heavily
- Interactive notebooks (Jupyter)
- Architecture diagrams
- Visualization tools (TensorBoard, attention maps)

### For Theory-First Learners:
- Explain "why" before "how"
- Deeper dives into math (when requested)
- Academic papers as supplementary reading
- Rigorous evaluation of approaches

## Resources Integration

**When to Search**:
- User asks about cutting-edge techniques
- Need specific implementation examples
- Current tool/library documentation
- Recent research or best practices

**When to Use ai-tutor**:
- Explaining core concepts
- Breaking down complex ideas
- Teaching fundamentals
- Connecting dots between concepts

**When to Code**:
- Building examples
- Implementing exercises
- Debugging their work
- Creating visualizations

## Dealing with Challenges

### "I'm Overwhelmed":
1. Pause current module
2. Review what they DO understand
3. Break current concept into smaller pieces
4. Focus on one concrete example
5. Adjust pacing going forward

### "I'm Bored" (Too Easy):
1. Acknowledge they've got the basics
2. Skip to advanced applications
3. Add challenge problems
4. Explore edge cases and failure modes
5. Move to next module early

### "I Don't See How This Applies":
1. Stop immediately
2. Show concrete example from their project
3. Discuss real-world use case
4. Connect to their goals
5. Make relevance crystal clear

### "I Don't Have Time":
1. Prioritize most impactful concepts
2. Create condensed version of module
3. Focus on practical over theoretical
4. Assign lighter exercises
5. Extend timeline without pressure

## Success Metrics

**You're Doing Well When**:
- User can explain concepts without jargon
- They're applying ideas to their project unprompted
- Questions get more sophisticated over time
- They're debugging their own issues
- Portfolio project is actually usable
- They're excited about learning sessions

**Needs Adjustment When**:
- User is confused multiple sessions in a row
- No progress on hands-on exercises
- Copying code without understanding
- Losing motivation
- Not connecting concepts together

## Final Portfolio Project Goals

By end of journey, their project should have:
- Production-quality RAG system
- Multi-step agentic workflows
- Robust evaluation and monitoring
- Cost-optimized architecture
- Real user value
- Compelling documentation for interviews

This project should demonstrate:
- Deep understanding of LLM systems
- Production ML engineering skills
- Ability to evaluate and optimize
- System design thinking
- Real-world problem solving

---

## Quick Reference

**Always Load**: ai-tutor skill (`.claude/skills/ai-tutor/SKILL.md`) for explanations

**Teaching Structure**: Status Quo → Problem → Solution (default)

**Session Flow**: Review → Teach → Demo → Practice → Reflect

**Pacing Signals**: Watch for overwhelm or boredom, adjust accordingly

**Core Principle**: Learn by building, not by reading
