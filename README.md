# 🎬 Stream Framework

> Building real things live — one season at a time.

[![GitHub](https://img.shields.io/badge/GitHub-StreamSaga-blue?logo=github)](https://github.com/Alirun/StreamSaga)

This repo documents how the stream is structured: seasons, episodes, and the "frameworks" we use to build real things live.

---

## 📑 Table of Contents

- [Structure](#-structure)
  - [Seasons](#seasons--long-running-projects--apps)
  - [Episodes](#episodes--individual-streams)
- [Frameworks](#-frameworks)
- [Seasons](#-seasons)
  - [Season 1 - StreamSaga](#season-1---streamsaga)
- [Quick Links](#-quick-links)

---

## 🧱 Structure

### Seasons = Long-running projects / apps

Each **season** is focused on building or evolving **one main project**.

| Season | Project | Description |
|--------|---------|-------------|
| 1 | [StreamSaga](https://github.com/Alirun/StreamSaga) | Viewer proposal + voting app |
| 2+ | TBD | Decided later (possibly via StreamSaga) |

> Every season starts with a **Season Planning** episode.

### Episodes = Individual streams

Each **episode** is one stream inside a season.

- Starts with an **Episode Planning** segment
- Defines what we try to ship *today*
- Pulls from: Season goals, Chat proposals, StreamSaga votes

### Frameworks = How we build things

A constantly evolving methodology for how we approach different parts of the work.

---

## 🔧 Frameworks

Reusable methodologies, checklists, and best practices. **Contributions welcome!**

| Framework | Description | Status |
|-----------|-------------|--------|
| [📝 PRD](./frameworks/prd.md) | Product Requirements Documents | ✅ Available |
| [🏗️ Architecture](./frameworks/architecture.md) | System design & patterns | ✅ Available |
| [💻 Development](./frameworks/development.md) | Development practices & tooling | ✅ Available |
| DevOps | CI/CD, deployment, infrastructure | 🔜 Coming soon |
| DeFi | Decentralized finance protocols | 🔜 Coming soon |
| Trading | Trading systems & strategies | 🔜 Coming soon |
| Security | Security practices & audits | 🔜 Coming soon |
| Testing | Test strategies & automation | 🔜 Coming soon |
| Debugging | Troubleshooting methodologies | 🔜 Coming soon |
| Reverse Engineering | Code analysis & understanding | 🔜 Coming soon |

> Over time, these frameworks should become more concrete: principles, checklists, do/don't, common patterns.

---

## 🎬 Seasons

### Season 1 - StreamSaga

**Tagline:** *Every episode forged by you*

🔗 **Project:** [github.com/Alirun/StreamSaga](https://github.com/Alirun/StreamSaga)

**Goal:** Build a web app that lets viewers:
- Log in via Email or Twitch
- Propose ideas for the stream / next episodes
- Vote on proposals
- Use it live on stream as the decision layer

<details>
<summary><strong>📋 Tech Stack</strong></summary>

- **Frontend:** Next.js
- **Backend:** Supabase (database + vector search + auth)
- **Deployment:** Cloudflare Workers + OpenNext

</details>

<details>
<summary><strong>📖 Season 1 Documentation</strong></summary>

| Document | Description |
|----------|-------------|
| [📝 PRD](./seasons/1_StreamSaga/prd.md) | Product Requirements Document |
| [✅ TODO](./seasons/1_StreamSaga/todo.md) | Current tasks & backlog |

</details>

<details>
<summary><strong>🎥 Episodes</strong></summary>

#### Episode 1 - PRD → Google Antigravity → First Features

**Focus:**
- Define the **PRD for StreamSaga**:
  - User roles (viewer, host)
  - Proposal model
  - Voting rules & weight system
  - First UI flow sketches
- Download, install, and test **Google Antigravity**
- Use Antigravity to generate/assist with the **first features** of the app

#### Episode 2 - TBD

</details>

---

### Season 2 - TBD

Season 2 will be a new project, chosen later (possibly via StreamSaga once it's live).

---

## 🔗 Quick Links

| Resource | Link |
|----------|------|
| 🚀 StreamSaga Project | [github.com/Alirun/StreamSaga](https://github.com/Alirun/StreamSaga) |
| 📝 Season 1 PRD | [seasons/1_StreamSaga/prd.md](./seasons/1_StreamSaga/prd.md) |
| ✅ Season 1 TODO | [seasons/1_StreamSaga/todo.md](./seasons/1_StreamSaga/todo.md) |
| 📝 PRD Framework | [frameworks/prd.md](./frameworks/prd.md) |
