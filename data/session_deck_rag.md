# Retrieval-Augmented Generation — Approved Session Deck

## SLIDE-02 · What RAG changes

**Passage DECK-S02-P01.** Retrieval-Augmented Generation retrieves relevant material at request time and supplies that material to a generative model as context. It is useful when answers must be grounded in a controlled body of knowledge or when facts change more quickly than a model can be retrained.

**Passage DECK-S02-P02.** Fine-tuning primarily changes model behavior, style, or task performance. It is not a dependable method for keeping frequently changing factual knowledge current. A system may combine fine-tuning for behavior with retrieval for current facts.

## SLIDE-04 · Chunking for retrieval quality

**Passage DECK-S04-P01.** Chunk size is a tunable design choice, not a universal constant. Smaller chunks can improve precision by isolating relevant statements, but may lose surrounding context. Larger chunks preserve context but may mix relevant and irrelevant material.

**Passage DECK-S04-P02.** Overlap can preserve meaning that crosses a chunk boundary. Excessive overlap creates duplicate retrieval results and increases indexing and prompt-processing cost.

**Passage DECK-S04-P03.** Select chunk size by testing representative questions against retrieval metrics. The session does not prescribe 500 tokens or any other value as universally best.

## SLIDE-05 · Embeddings and hybrid retrieval

**Passage DECK-S05-P01.** Embeddings represent semantic relationships as vectors. Cosine similarity compares vector direction and is commonly used when direction represents meaning more strongly than magnitude.

**Passage DECK-S05-P02.** Hybrid search combines semantic retrieval with lexical matching. It can help when exact identifiers, product codes, or names matter alongside semantic meaning.

## SLIDE-06 · Reranking

**Passage DECK-S06-P01.** A reranker scores an initial candidate set with a more precise relevance model. It can improve top-result quality when first-stage retrieval has acceptable recall but poor ordering, at the cost of added latency and computation.

## SLIDE-08 · Evaluation and limitations

**Passage DECK-S08-P01.** Evaluate retrieval and generation separately. Retrieval evaluation asks whether relevant evidence appears in the candidate set; generation evaluation asks whether the answer is correct, supported, and faithful to that evidence.

**Passage DECK-S08-P02.** RAG can reduce unsupported answers when retrieval and grounding work well, but it does not eliminate hallucinations. Missing, irrelevant, or conflicting evidence can still lead to incorrect output.

**Passage DECK-S08-P03.** Source references make grounded answers inspectable. The appropriate learner-facing citation detail depends on the interface and course policy, but the review card must always identify the supporting passage.
