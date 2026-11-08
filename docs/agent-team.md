# Agent team

I am using GitHub Copilot CLI in a Codespace to orchestrate the custom agent team building Mona's Project Pulse dashboard.

| Agent | Target model | Responsibility | Definition |
| --- | --- | --- | --- |
| Orchestrator | Claude Opus 5.5 (copilot) | Coordinates the team: obtains a plan, assigns explicit file scopes, sequences or parallelizes phases, verifies integration, and reports the outcome. | `.github/agents/orchestrator.agent.md` |
| Planner | Claude Opus 5.5 (copilot) | Researches the repository and relevant documentation, then produces an implementation plan with file ownership, dependencies, risks, edge cases, and validation expectations. | `.github/agents/planner.agent.md` |
| Coder | GPT-5.5 (copilot) | Implements the assigned dashboard code with explicit errors and testable behavior; when assigned runnable app work, it can also create the Project Pulse launch configuration. | `.github/agents/coder.agent.md` |
| Designer | Gemini 3.7 Flash (copilot) | Shapes the dashboard's UI/UX, accessibility, responsive layout, visual hierarchy, styling, and interaction flow. | `.github/agents/designer.agent.md` |

The Orchestrator starts with the Planner's implementation strategy, then delegates distinct, non-overlapping file scopes to the Coder and Designer while preserving the learner's control of all Git operations through Copilot CLI.
