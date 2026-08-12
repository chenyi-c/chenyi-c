# Portfolio hub design

_Approved direction for turning four verified repositories into a recruiter-facing evidence trail._

---

## 🎯 Outcome

Create one GitHub profile entry that lets a reviewer understand the candidate, the two primary capabilities, and the proof behind four projects in under three minutes.

## 📋 Information structure

- `README.md`: short positioning, two primary projects, four-project evidence table, contact direction
- `PORTFOLIO_EVIDENCE.md`: personal contribution boundaries, verified tests/CI, PR links, non-claims
- `INTERVIEW_GUIDE.md`: concise project narrative, failure stories, and common technical questions
- AgentDeck and Log AI Assistant: one interview pack each, linked from the project README

## 🔐 Evidence rules

- Prefer tests, CI runs, PRs, screenshots, and committed JSON/Markdown over adjectives
- Separate individual contribution from team ownership
- Do not claim LLM, RAG, MCP, accuracy, performance, deployment, or upstream ownership without evidence
- Keep Campus and Energy as supporting proof; AgentDeck and Log AI Assistant remain the primary projects
- Do not read or modify any `code-navi` repository or artifact

## ✅ Acceptance

- The profile repository is public and named `chenyi-c/chenyi-c`
- Every project row links to a repository and verified merged PR
- Both primary repositories link to a reusable interview pack
- Markdown has no placeholder text, broken relative links, or unsupported claims
