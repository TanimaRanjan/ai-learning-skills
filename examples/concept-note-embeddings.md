# Embeddings

**Created**: 2024-02-10
**Related Concepts**: `rag-architecture.md`, `semantic-search.md`
**Learning Phase**: Phase 1 - Module 1.2

---

## Plain English Definition

Embeddings are numbers that capture the meaning of words or sentences. Similar meanings get similar numbers, which lets computers understand that "Paris" and "France" are related even though the words are different.

---

## The Problem It Solves

**Status Quo**: Before embeddings, computers could only match exact words. Searching for "cheap laptops" wouldn't find "budget notebooks."

**Limitation**: Keyword matching misses semantic connections. "Cat" and "feline" mean the same thing, but computers saw them as completely different.

**Solution**: Embeddings convert text into numbers in a way that preserves meaning. Similar concepts end up close together in number space, so computers can find semantically related content even with different words.

---

## How It Works

1. **Text goes into a model** (like OpenAI's text-embedding-ada-002)
2. **Model outputs a vector** - a list of ~1500 numbers (called dimensions)
3. **Similar meanings produce similar vectors** - measured by distance in number space
4. **Compare vectors** using cosine similarity or dot product to find related content

Think of it like GPS coordinates. New York (40.7, -74.0) is closer to Boston (42.4, -71.1) than to Los Angeles (34.1, -118.2). Embeddings work the same way but with hundreds of dimensions instead of just latitude/longitude.

---

## Concrete Example

For a product catalog, I embedded 500 product descriptions:

**Scenario**: User asks "lightweight running shoes"

**Implementation**:
1. Embed the query → gets vector like [0.23, -0.15, 0.89, ...]
2. Compare to all product embeddings
3. Find closest matches:
   - Ultra-light marathon trainers → distance: 0.12 (very close)
   - Breathable jogging sneakers → distance: 0.18 (close)
   - Heavy-duty hiking boots → distance: 0.76 (far)

**Result**: System returns marathon trainers and jogging sneakers even though the query said "running shoes" and descriptions said "trainers" and "sneakers" - embeddings captured the semantic similarity.

---

## When to Use This

✅ **Use when**:
- Searching for semantic similarity (not just keywords)
- Building RAG systems that need to find relevant context
- Comparing documents or text snippets
- Clustering similar content

❌ **Don't use when**:
- Exact keyword matching is needed (use traditional search)
- Working with very short texts (< 5 words) - embeddings need context
- Need to explain WHY things are similar (embeddings are black boxes)
- Real-time constraints are extreme (embedding takes ~100ms per call)

---

## Common Pitfalls

**Pitfall 1: Embedding Individual Words**
- What it is: Trying to embed single words like "shoe" or "laptop"
- How to avoid: Embed full sentences or paragraphs. Embeddings need context to be meaningful.

**Pitfall 2: Not Normalizing for Comparison**
- What it is: Comparing raw embedding vectors without normalization
- How to avoid: Use cosine similarity (which normalizes) or normalize vectors before dot product

**Pitfall 3: Embedding Too Much Text**
- What it is: Trying to embed a 10-page document as one embedding
- How to avoid: Chunk documents into smaller pieces (300-500 tokens) and embed each chunk separately

---

## Key Tradeoffs

| Aspect | Benefit | Cost |
|--------|---------|------|
| Semantic search | Finds related content even with different words | Slower than keyword search (~100ms vs <1ms) |
| Smaller indexes | 1500 numbers vs full text | Need embedding API (costs money) |
| Multilingual | Same embeddings work across languages | Black box - can't explain why similar |

---

## Technical Details

**Parameters/Configuration**:
- **Model**: `text-embedding-ada-002` (OpenAI) or `text-embedding-3-small`
- **Dimensions**: 1536 for ada-002, 512-3072 for ada-003 (configurable)
- **Max tokens**: 8191 tokens per embedding
- **Cost**: $0.0001 per 1K tokens (as of Feb 2024)

**Under the Hood**:
- Embeddings come from the intermediate layers of transformer models
- They capture semantic meaning learned from training on billions of text examples
- The model learns that words appearing in similar contexts should have similar embeddings

---

## Related Concepts

- **RAG Architecture** (`rag-architecture.md`): Embeddings are the "retrieval" part of RAG
- **Vector Databases** (`vector-databases.md`): Where embeddings are stored and searched efficiently
- **Semantic Search** (`semantic-search.md`): The primary application of embeddings
- **Chunking Strategies** (`chunking-strategies.md`): How to break text before embedding

---

## Practice Questions

1. Why can't you just compare text directly instead of using embeddings?
2. Your search returns irrelevant results for "eco-friendly products". What might be wrong with your embeddings?
3. When would keyword search be better than embedding-based search?

<details>
<summary>Answers</summary>

1. Text comparison only catches exact matches. "Car" and "automobile" look completely different to string matching, but embeddings know they mean the same thing. Embeddings capture semantic meaning that simple text comparison misses.

2. Possible issues:
   - Chunks are too large/small (losing context or meaning)
   - Not enough eco-focused items in the database to learn from
   - Using wrong embedding model (some are better at sentiment/style)
   - Need to fine-tune or use different retrieval strategy

3. Keyword search is better when:
   - User searches exact terms (product IDs, specific names)
   - Speed is critical (<1ms needed)
   - Budget is tight (embeddings cost money)
   - Looking for code or technical terms (exact matching matters)

</details>

---

## Applied in My Project

**Where I used this**:
Product catalog search - embedded all 500 product descriptions and user queries

**Results**:
- Search relevance improved from 60% to 87%
- Users find what they want even with vague queries
- "Lightweight running shoes" now returns trainers, sneakers, etc.

**Lessons learned**:
- Chunk size matters: 300-400 tokens worked best for product descriptions
- Need to re-embed when descriptions change (embeddings don't auto-update)
- Hybrid search (keywords + embeddings) works better than embeddings alone for specific searches

**Costs**:
- Initial embedding of 500 products: ~$0.50
- Per-query embedding: ~$0.0001
- Total monthly cost: ~$5 for 50K queries

---

## Resources

- [OpenAI Embeddings Guide](https://platform.openai.com/docs/guides/embeddings)
- [Vector Search Best Practices](https://www.pinecone.io/learn/vector-search/)
- [Understanding Text Embeddings](https://jalammar.github.io/illustrated-word2vec/)

---

## Revision History

- 2024-02-10: Initial note created
- 2024-02-15: Added cost analysis from implementing in project
- 2024-02-18: Updated with chunking lessons learned
