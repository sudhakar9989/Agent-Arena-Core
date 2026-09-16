---
language:
- en
license: apache-2.0
tags:
- agent-evaluation
- multi-turn-benchmarks
- virtual-agents
- llm-judge
---

# 🛡️ AgentArena-Core

**AgentArena-Core** is an extensible benchmarking engine designed for automated multi-turn evaluation, conversational testing, and reliability monitoring of virtual agents and RAG pipelines.

---

## Architectural Highlights

- **Dual-Agent Dialogue Engine:** Deploys an automated evaluator agent that simulates user personas, challenges system boundaries, and assesses target response compliance turn-by-turn.
- **Provider-Agnostic Targets:** Out-of-the-box adapters for Amazon Bedrock Agents, SageMaker, OpenAI Assistants, FastAPI endpoints, and generic WebSocket targets.
- **Dynamic Hook Interceptors:** Run custom validation checks, tool call assertions, and latency monitors before and after each conversational exchange.
- **Automated Summary Reporting:** Exports pass-rates, turn efficiency, and trace transcripts in structured JSON, JUnit XML, or terminal tables.

---

## Quickstart

```bash
# 1. Install editable package
pip install -e .

# 2. Execute test plan
agentarena run --plan arena_plan.yml --target bedrock-agent --verbose
Configuration SchemaYAMLversion: "1.0"
evaluator:
  model: "anthropic.claude-3-7-sonnet"
  max_turns: 8
  criteria:
    - name: "Resolution Accuracy"
      threshold: 0.85
target:
  type: "bedrock-agent"
  agent_id: "YOUR_AGENT_ID"
  agent_alias_id: "YOUR_ALIAS_ID"
