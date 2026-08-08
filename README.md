# Session Intelligence Studio

Session Intelligence Studio is a human-supervised live Q&A assistant for large virtual technical-learning sessions. It categorizes and clusters learner questions, retrieves evidence from approved session material, drafts grounded answers, and routes every learner-facing response through mentor or TA approval before publication.

**Live capstone prototype:** [ankit28123.github.io/session-intelligence-studio](https://ankit28123.github.io/session-intelligence-studio/)

> This is a browser-based capstone prototype using synthetic data. It is not a production learning-platform integration or an autonomous teacher.

## Core workflow

1. A synthetic learner question enters the active session queue.
2. The agent assigns one or more approved categories.
3. It joins an existing cluster only when concept, intent, objective, evidence requirement and answer logic all match; otherwise it creates or recommends a separate cluster.
4. It retrieves evidence only from the approved session deck, notes and knowledge base.
5. It drafts a cited answer or escalates unsupported, ambiguous, sensitive, high-judgement or unsafe requests.
6. A mentor or TA approves, edits or escalates the exact draft version.
7. Only a version with matching human approval can be published.

## Supporting materials

| Material | What it contains |
|---|---|
| [Synthetic data](data/) | Learner questions, approved RAG sources, session state, clusters, review queue, publication log and optional rating events |
| [Evaluation cases](data/eval_cases.csv) | Five end-to-end cases covering grounding, clustering, unsupported recommendations, privacy and prompt injection |
| [Golden evaluation labels](data/golden_eval_cases.csv) | Expected categories, clusters, routing decisions, evidence and workflow states |
| [Clustering pairs](data/cluster_eval_pairs.csv) | Must-link, cannot-link and acceptable-either-way question pairs |
| [Agent policies](policies/) | Category, clustering, escalation, approval, source-priority and input-safety rules |
| [Evaluation evidence](docs/EVALUATION_EVIDENCE.md) | Final results, improvement story, interpretation and reproduction steps |
| [Design system](design/) | Interface tokens and visual skins used by the single-file prototype |

## Evaluation summary

The prototype was rerun against all five synthetic evaluation cases after the final prompt, retrieval, citation and parser changes. All five cases passed, and no unapproved answer was published.

The key improvement came from an unseen question about hybrid versus semantic search. It was initially merged into the RAG-versus-fine-tuning cluster because both involved choosing a technique. The clustering policy was strengthened so concept, intent, objective, evidence and answer logic must all match, and an existing cluster cannot be broadened merely to admit a new question. The rerun correctly created a separate retrieval-method cluster.

See [Evaluation evidence](docs/EVALUATION_EVIDENCE.md) for the case-by-case record.

## Privacy and security

- All learner, mentor, session and rating records are synthetic.
- No real learner or institutional data is included.
- No API key is stored in this repository.
- A visitor who wants to run the agent supplies their own Anthropic API key in the prototype's Settings panel; it is stored only in that browser's `localStorage`.
- Learner text cannot create approval, override policies or authorize publication.

## Known limitations

- English-only, synthetic RAG-session data.
- Questions are processed sequentially in a browser prototype.
- No live learning-platform chat stream, shared audit database or simultaneous mentor/TA review.
- No external retrieval beyond the approved embedded sources.
- No cross-session learner memory, learner reports, automated emails or quiz analytics.

## Run locally

Download the repository and open [index.html](index.html) in a browser. No build step or framework is required. To run agent-generated responses, add your own Anthropic API key through the app's Settings panel.

