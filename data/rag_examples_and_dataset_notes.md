# Approved RAG Examples and Dataset Notes

## EX-01 · Frequently changing handbook

A fictional training provider updates a certification handbook every week. Retrieval is preferred for the changing handbook facts because updated passages can be indexed without retraining the model. This example illustrates `DECK-S02-P01` and does not make a vendor recommendation.

## EX-02 · Chunk near-miss

Questions about chunk size for retrieval relevance may share evidence from `DECK-S04-P01` and `DECK-S04-P03`. A question about chunk size for storage and token cost requires `KB-CHUNK-02`, so it stays in a separate cluster even though the broad category is the same.

## EX-03 · Evaluation diagnosis

For each synthetic test question, the evaluation set identifies a gold passage. First check whether retrieval returns that passage; then judge whether the generated answer faithfully uses it.

## DATA-01 · Synthetic-data declaration

All learner aliases, questions, timestamps, approvals, records, and ratings in this prototype are fictional and created solely for the capstone evaluation.
