Ralph Mode
===========
Ralph Mode is a framework for building AI agents that can iteratively improve
their performance through continuous feedback loops. Named after Ralph Wiggum
from The Simpsons, who is known for his simple and often humorous outlook,
Ralph Mode emphasizes simplicity and adaptability in AI agent design.

This mode is something you (the user) must activate before `samantha-llm` will
operate in this way.

# Activation Pattern

When you say phrases like:
  - "Enter Ralph mode for [task]"
  - "Start iterative coding on [task]"
  - "Use Ralph loop to implement [feature]"

Samantha-LLM will:
  
1. Confirm task understanding:
    - Clarify the task scope
    - Define machine-verifiable success criteria (tests, linting, etc.)
    - Create explicit checklist of completion requirements
2. Initialize Ralph session:
    - Read existing guardrails from .ai-cerebrum/.ai/ralph-guardrails/[project].md
    - Note token budget and set thresholds (60%, 80%, 90%)
    - Confirm ready to enter iteration loop
3. Execute iteration cycle:
  Loop:
    1. Work: Make changes, write code, run tests
    2. Evaluate: Check against success criteria
    3. Document: Update progress, add guardrails if failures
    4. Decide: Complete? → Exit. Incomplete? → Iterate.
    5. Monitor: Check token usage, rotate context if needed
4. Exit conditions:
    - ✅ All success criteria met
    - 🛑 User says "stop" or "exit Ralph mode"
    - ⚠ Critical blocker requiring user input
    - 🔄 Context limit reached (create memory, request fresh start)

# Sources:
  - https://ghuntley.com/ralph/
  - https://github.com/repomirrorhq/repomirror/blob/main/repomirror.md
  - https://dev.to/alexandergekov/2026-the-year-of-the-ralph-loop-agent-1gkj
  - https://www.alibabacloud.com/blog/from-react-to-ralph-loop-a-continuous-iteration-paradigm-for-ai-agents_602799
  - https://github.com/vercel-labs/ralph-loop-agent
  - https://awesomeclaude.ai/ralph-wiggum
