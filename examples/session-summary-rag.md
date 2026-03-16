# Session 002: Building a Basic RAG System

**Session Number**: 002
**Date**: 2024-02-15
**Duration**: 2.5 hours
**Learning Phase**: Phase 1 - Module 1.2
**File**: `sessions/session-002-rag-fundamentals.md`

---

## Goals for This Session

- Understand RAG architecture conceptually
- Build a working RAG system for project domain data
- Compare different chunking strategies
- Implement semantic search with embeddings

---

## Concepts Covered

### 1. RAG Architecture

**What it is**: Retrieval Augmented Generation - a pattern where you retrieve relevant information from a knowledge base, then use it as context for an LLM to generate a response.

**Key insight**: You don't need to fine-tune a model to give it knowledge. Just retrieve relevant info and pass it in the prompt.

**Application**: My app can now answer questions about 500 documents without fine-tuning or fitting everything in the context window.

→ *Full notes*: `concepts/rag-architecture.md`

### 2. Embeddings

**What it is**: Numerical representations of text that capture semantic meaning. Similar concepts have similar numbers.

**Key insight**: Embeddings let you search by meaning, not just keywords. "Cheap laptops" finds "budget notebooks."

**Application**: User queries get embedded and compared to embedded document descriptions to find the most relevant matches.

→ *Full notes*: `concepts/embeddings.md`

### 3. Chunking Strategies

**What it is**: Breaking large documents into smaller pieces before embedding them.

**Key insight**: Chunk size dramatically affects retrieval quality. Too small = lose context. Too large = lose precision.

**Application**: Found that 300-400 token chunks worked best for our domain documents. Single-paragraph chunks lost important details; multi-page chunks were too generic.

→ *Full notes*: `concepts/chunking-strategies.md`

---

## Hands-On Work

**What we built**:
A basic RAG system that:
1. Takes 500 domain documents
2. Chunks them into ~300 token pieces
3. Embeds each chunk using OpenAI's ada-002
4. Stores embeddings in a simple JSON file (will move to vector DB later)
5. Takes user queries, embeds them, finds top 5 similar chunks
6. Passes chunks to GPT-4 as context for response

**Code/Files**:
- `exercises/week-02-basic-rag/embed_documents.py` - Chunks and embeds all documents
- `exercises/week-02-basic-rag/search.py` - Semantic search implementation
- `exercises/week-02-basic-rag/documents_embedded.json` - Stored embeddings
- `exercises/week-02-basic-rag/README.md` - Full documentation

**Results**:
- ✅ Successfully embedded 500 documents (took ~5 minutes, cost $0.47)
- ✅ Search relevance at 87% (tested on 30 sample queries)
- ✅ Average query time: 234ms (fast enough for now)
- ❌ Struggled with very specific queries like product IDs (need hybrid search)
- ❌ Some documents split awkwardly (need smarter chunking)

---

## Key Takeaways

1. **RAG is simpler than I thought** - Just retrieve, then generate. No magic. The complexity is in making retrieval good.

2. **Chunking strategy matters more than I expected** - Spent an hour testing different sizes. 300-400 tokens was the sweet spot for our domain documents.

3. **Embeddings aren't free** - At $0.0001 per 1K tokens, costs add up. Need to cache query embeddings and batch document updates.

---

## Questions / Confusion

- [ ] How do I handle updates to documents without re-embedding everything?
- [ ] When should I use a vector database vs just storing in JSON? (probably now that I have 500 docs)
- [x] What's the difference between cosine similarity and dot product? (answered: cosine normalizes, dot product doesn't)

---

## Next Steps

- [ ] Move embeddings from JSON to Pinecone or Weaviate
- [ ] Implement hybrid search (embeddings + keyword matching)
- [ ] Add re-ranking step to improve top results
- [ ] Test with more diverse queries
- [ ] Optimize chunking for different content types

---

## Next Session Plan

**Session 003**: Agentic Workflows — building multi-step agents
**Module**: Phase 1 - Module 1.3: Agentic Workflows
**Prerequisites**: Complete hybrid search experiment from homework above

---

## Connections Made

- Embeddings from today explain why vector databases exist (can't search billions of floats efficiently in SQL)
- This connects to prompt engineering because retrieved context needs to fit in the prompt
- The chunking problem is similar to the pagination problem in frontend - too much data, need to break it up smartly

---

## Personal Reflections

**What went well**:
Building something tangible really helped the concepts stick. Reading about RAG vs actually building it are completely different experiences.

**What was challenging**:
Deciding on chunk size felt arbitrary at first. Had to run experiments to find what worked. Would have helped to have a better evaluation framework upfront.

**Energy level**: 4/5 (stayed engaged throughout)
**Confidence level**: 4/5 (feel like I could build this again from scratch now)
