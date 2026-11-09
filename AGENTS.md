# Instructions for coding agents

Before changing the app, read:

1. [Project context](docs/PROJECT_CONTEXT.md)
2. [Agent workflow](docs/AGENT_WORKFLOW.md)
3. The task prompt in [prompts/](prompts/)

## Project invariants

- Product name: **LUMINA**.
- The team has three members. Round 1 has three distinct roles: Bomb Maker, Thrower, and Builder. Each role must eventually be assigned to one member only, and role access must be enforced by the server. Do not treat a client-side page split as authorization.
- Bomb Maker uses a fictional component puzzle station with three independent bomb circuit boards and five component feed slots. Each feed slot refills one second after a component is used; shuffled component draws must cycle through every type. A circuit check must update feedback only on that bomb card. Incorrect circuits do not change shared match state. Correct circuits add one ammo crate, subject to the ammo cap.
- Thrower has at most three shots and must calculate a precise launch angle. Do not turn every slider movement into a network write.
- Builder advances construction progress through stages. The Builder does not manage structure HP.
- Round 3 is a timed LED pattern deduction challenge on an eight-LED Rangoli layout.
- Round 4 is a free-build circuit workspace with a required target circuit. Its current Arduino and component behavior is a browser simulation, not an electrical solver or physical hardware connection.
- Keep demo/local-browser behavior clearly identified. Do not claim that localStorage is secure, shared across devices, or authoritative.
- Preserve the current independent HTML page navigation and naming unless the task explicitly changes it.
- Never put secrets, real team codes, credentials, and private participant data in the repository.

## Questions and decisions

Do not silently invent scoring rules, role assignment, answer banks, match rules, or electrical behavior when those choices affect gameplay. Add concise questions to [docs/AGENT_QUESTIONS.md](docs/AGENT_QUESTIONS.md). Human answers should be recorded in [docs/AGENT_ANSWERS.md](docs/AGENT_ANSWERS.md), then reflected in implementation.

Keep changes scoped to the request. Summarize changed pages, behavior, and limitations in the final handoff.