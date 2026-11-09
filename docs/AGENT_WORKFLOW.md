# Partner-agent workflow

## Before coding

1. Read the repository-root [AGENTS.md](../AGENTS.md) and [PROJECT_CONTEXT.md](PROJECT_CONTEXT.md).
2. Read the prompt the human assigned in `prompts/`.
3. Inspect the affected pages and their links before changing them.
4. Keep changes in the repository; do not rely on files outside this checkout.

## If a requirement is unclear

Add a numbered entry to [AGENT_QUESTIONS.md](AGENT_QUESTIONS.md) with:

- **Question ID**
- **Task/branch**
- **Files or behavior involved**
- **What is unclear**
- **Options or a recommendation**, if helpful

Do not guess on gameplay rules, role ownership, scoring, or security behavior. Continue independent work that does not depend on the answer.

## Recording answers

The human can bring the question file or repository link back to the LUMINA planning thread. Answers from that thread will be recorded in [AGENT_ANSWERS.md](AGENT_ANSWERS.md). Re-read the answer file before proceeding. This file workflow does not automatically deliver messages between separate AI-agent chats; a human must bring/publish the questions and answers.

## Handoff

When done, report:

- What changed and where
- How the pages connect
- Any assumptions
- Any checks actually performed
- Remaining limitations

Do not claim tests, previews, backend security, real-time synchronization, or physical simulation unless they were actually performed or implemented.