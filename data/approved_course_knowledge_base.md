# Approved Course Knowledge Base

## KB-RAG-01 · Retrieval and model adaptation

Retrieval supplies external evidence at inference time. Fine-tuning adapts behavior using training examples. Use retrieval when traceability or changing factual content is central; use fine-tuning when repeatable behavior or format is central. They can be complementary.

## KB-CHUNK-01 · Quality trade-off

Chunking should preserve enough context to answer a question while avoiding unrelated material. Evaluate candidate strategies with representative questions rather than selecting a size from convention alone.

## KB-CHUNK-02 · Cost trade-off

Chunk size and overlap affect the number of embedded records, index storage, retrieved token volume, and prompt-processing cost. Cost optimization has a different decision objective from retrieval-quality optimization even when both discuss chunk size.

## KB-EVAL-01 · Diagnostic evaluation

If gold evidence is absent from retrieved candidates, investigate retrieval. If gold evidence is present but the answer is wrong or unsupported, investigate generation instructions and grounding. End-to-end correctness alone cannot identify which stage failed.

## KB-SAFE-01 · Evidence limit

Approved course sources do not contain current vendor prices, bank procurement requirements, personal contact details, weather data, or individualized legal, medical, or financial advice.
