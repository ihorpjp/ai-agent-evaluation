# AI Agent Evaluation — Fintech Internal Deployment Research

Systematic evaluation of 7 AI agents via Anthropic API for internal deployment  
across Sales, Marketing and Support teams in a fintech startup environment.

> Conducted at Koosmik (Luxembourg) as part of internal technical operations work.  
> Business data excluded — methodology and technical findings documented for reference.

---

## Environment

| Component | Details |
|-----------|---------|
| Hardware | Mac Mini M4 |
| OS | macOS |
| Runtime | Docker + Docker Compose |
| API | Anthropic API (Claude Sonnet) |
| Framework tested | agency-agents (GitHub) |

---

## What was evaluated

### Agents tested (7 total)
- Sales outreach agent
- Support ticket classifier
- Marketing content agent
- Internal FAQ assistant
- Data extraction agent
- Email summarisation agent
- Task routing agent

### Evaluation criteria

| Criteria | Weight |
|----------|--------|
| Response quality | 30% |
| Deployment complexity | 20% |
| Cost per operation | 25% |
| Reliability / error rate | 15% |
| Maintenance overhead | 10% |

---

## Architecture comparison

| Factor | OpenClaw | Claude Code |
|--------|----------|-------------|
| Setup complexity | High | Low |
| Requires modification | Yes — significant | No |
| API integration | Custom | Native |
| Reliability | Unstable in testing | Stable |
| Cost estimation | Higher overhead | 5–20 EUR/month |
| Recommended for production | ❌ | ✅ |

---

## Cost analysis

Estimated for **moderate workload** (internal team of ~10 people):

| Usage level | Estimated cost |
|-------------|---------------|
| Light (occasional use) | ~5 EUR/month |
| Moderate (daily team use) | ~10–15 EUR/month |
| Heavy (automated pipelines) | ~20 EUR/month |

Based on Claude Sonnet pricing at time of evaluation (April 2026).

---

## Conclusion

**Claude Code recommended for production deployment.**

OpenClaw was not suitable without significant modification:
- Unstable behaviour during multi-agent orchestration
- Required custom patching for API compatibility
- Higher operational overhead with no clear benefit

Claude Code provided clean API integration, predictable costs,  
and required zero infrastructure modification for the target use case.

---

## Methodology

1. Defined use cases per team (Sales / Marketing / Support)
2. Set up isolated Docker environment on Mac Mini M4
3. Deployed agency-agents framework
4. Ran standardised test prompts per agent (20 prompts each)
5. Scored responses manually + measured latency and error rate
6. Compared deployment complexity between OpenClaw and Claude Code
7. Prepared recommendation report for management review

---

## Tech stack used

`Docker` `Docker Compose` `macOS` `Anthropic API` `Python` `Bash`

---

## Related

- [soc-pipeline](https://github.com/ihorpjp/soc-pipeline) — another internal tooling project
- [Anthropic API docs](https://docs.anthropic.com)
