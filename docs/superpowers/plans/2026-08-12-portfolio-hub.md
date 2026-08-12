# Portfolio hub implementation plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publish a recruiter-facing GitHub profile and reusable interview evidence for the two primary projects.

**Architecture:** Keep the profile repository documentation-only. Link to project repositories, draft PRs, tests, CI, and interview packs; do not duplicate source code or touch protected repositories.

**Tech Stack:** GitHub profile README, Markdown, Git, GitHub Actions evidence.

---

### Task 1: Profile entry

**Files:**
- Create: `README.md`
- Create: `PORTFOLIO_EVIDENCE.md`
- Create: `INTERVIEW_GUIDE.md`

- [x] Write a two-project-first profile and four-project evidence matrix
- [x] Link every repository and verified merged PR
- [x] Check Markdown with `git diff --check` and scan for placeholders
- [x] Commit the profile documents

### Task 2: Primary-project interview packs

**Files:**
- Create: `AgentDeck/docs/interview/portfolio-interview-pack.md`
- Modify: `AgentDeck/README.md`
- Create: `Log-AI-Assistant/docs/interview/portfolio-interview-pack.md`
- Modify: `Log-AI-Assistant/README.md`

- [x] Record positioning, three failure-first stories, live/replay/static demo fallbacks, and technical questions
- [x] Link each pack from its project README
- [x] Check relative links and run `git diff --check`
- [x] Commit and push the existing portfolio branches

### Task 3: GitHub presentation

**Files:**
- Publish: `chenyi-c/chenyi-c`

- [x] Create and push the public profile repository
- [x] Add concise descriptions and topics to the four portfolio repositories
- [x] Confirm all four merged PR checks remain successful
- [x] Confirm no path containing `code-navi` appears in any changed-file list
