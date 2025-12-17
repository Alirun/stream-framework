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

#### Episode 2 - AI Coding Rules; Google Antigravity; Supabase: Authentication

**Focus:**
- Define **AI Coding Rules** to control agent behavior:
  - Enforcing implementation plans
  - Preventing hallucinations
- Create and enforce the **Architecture Documentation** (`ARCHITECTURE.md`) as a source of truth
- Implement **Supabase Authentication**:
  - Email/Password flows (Sign up, Sign in)
  - Handling auth callbacks and email confirmation
  - Integrating **Twitch OAuth**
- Explore **Google Antigravity** features:
  - Setting up `.agent/rules`
  - Creating custom **Workflows** to automate documentation updates

#### Episode 3 - Supabase: ACL, Database & Vector Search; Google Antigravity;

**Focus:**
- Refine AI Coding Rules:
  - Add rules for "Feature Planning Notes" and Architecture updates
  - Integrate the PRD into the agent's context
- Implement Access Control Level (ACL):
  - Role-based middleware to protect Admin routes
  - Using Supabase `app_metadata` to manage Admin roles
  - Gated UI access (hiding Admin menus for non-admins)
- Build Topic Management with Realtime updates:
  - Create "Add Topic" workflow
  - Implement Supabase Realtime for instant list updates
  - Refactor logic into a Service Layer pattern
- Implement Vector Search:
  - Generate embeddings for topics using OpenAI API
  - Store vectors in Supabase (using `pgvector`)
  - Create a "Pre-insert Search" to find similar topics via vector similarity

#### Episode 4 - React Server Components Hacked; Supabase Vector Search; Google Antigravity;

**Focus:**
- Address critical React Server Components (RSC) Vulnerability:
  - Identify Remote Code Execution (RCE) risk in current version
  - Upgrade React and Next.js packages to patch the security hole
- Connect Dashboard to Real Data:
  - Replace mock UI data with live Supabase fetching
  - Implement real-time UI updates for new topics
- Implement Vector Search for Proposals:
  - Generate OpenAI embeddings for new proposals
  - Detect and prevent duplicate submissions via semantic similarity
  - Tune similarity thresholds to balance strictness
- Troubleshooting AI & Database Migrations:
  - Recover from corrupted migration history (AI modified applied migrations)
  - Enforce "never modify applied migrations" rule
- Implement Service Role Admin Client:
  - Resolve Row Level Security (RLS) errors on archive actions
  - Create a secure server-side client to bypass RLS for privileged operations

#### Episode 5 - Finish functionality; Rate limits; Deployment to Cloudflare; Google Antigravity;

**Focus:**
- Complete Core Functionality:
  - Implement Vote & Unvote logic (using soft deletes to preserve data)
  - Enforce database integrity with unique indexes (preventing duplicate votes)
  - Fix critical UI interactions (Vote button triggering form submissions)
- Build Admin Resolution Workflow:
  - Create "Manage Topic" interface for Admins
  - Implement "Resolve Topic" logic: Approve winning proposals and Close the topic simultaneously
  - Lock down closed topics to prevent further edits or submissions
- Implement Security & Rate Limits:
  - Analyze abuse vectors (OpenAI Embeddings costs, Supabase limits)
  - Integrate Cloudflare Rate Limiter bindings
  - Apply rate limiting specifically to the Embeddings generation to prevent API cost overruns
- Production Deployment to Cloudflare:
  - Configure the Next.js app for Cloudflare Workers using OpenNext
  - Setup Wrangler for deployment management and secret handling
  - Manage production environment variables (Supabase keys, OpenAI keys)
  - Go Live: First successful deployment to a public URL

#### Episode 6 - Testing, fixing bugs and tech debt with Supabase, Cloudflare and Antigravity;

**Focus:**
- Production Domain Setup:
  - Connect custom domain (streamsaga.space) via Cloudflare
  - Update Wrangler configuration (wrangler.toml) for production routes and DNS management
- Full System Reset & Testing:
  - Wipe Supabase database to validate the complete user onboarding flow from scratch
  - Identify critical bugs in the sign-up process (broken redirects, confusing UX)
- Debugging Cloudflare & Supabase Auth:
  - Troubleshoot email confirmation links incorrectly redirecting to localhost
  - Deep dive into Cloudflare Worker logs (Observability, wrangler tail, structured logging) to trace request headers
  - Configure Supabase SITE_URL and redirect allow-lists to support specific production environments
  - Resolve environment variable conflicts between local development and production builds
- UX Polish:
  - Replace default "ugly" Supabase email templates with custom, professionally designed HTML templates
  - Fix post-signup redirection logic to ensure users land on the correct login/dashboard pages

#### Episode 7 - Testing, fixing bugs and tech debt with Supabase, Cloudflare and Antigravity;

**Focus:**
- Authentication Polish & Web3 Integration:
  - Fix email confirmation redirects to ensure users are automatically logged in upon verification
  - Implement "Sign in with Ethereum" using Supabase Auth and MetaMask
  - Handle wallet-only user sessions and verify database integrity for users without emails
- Complete Password Reset Architecture:
  - Build the full "Forgot Password" and "Update Password" UI flows
  - Implement server-side actions to handle secure password recovery
  - Apply custom HTML styling to the password reset email templates
- Critical Security & Maintenance:
  - Perform urgent upgrade of React and Next.js to patch newly discovered security vulnerabilities
  - Audit dependencies to ensure a clean security state before production use
- Admin Features & UI Refinement:
  - Implement logic to Close and Archive topics in the Admin panel
  - Switch global date formatting to relative time (e.g., "2 hours ago") for better UX
  - Conduct full end-to-end testing of the application (User and Admin roles)

#### Episode 8 - Testing, fixing bugs and tech debt with Supabase, Cloudflare and Antigravity;

**Focus:**
- Infrastructure & Email Reliability:
  - Bypass Supabase default email rate limits by integrating Resend as a custom SMTP server
  - Configure essential DNS records (MX, SPF, DKIM) for the streamsaga.space domain to ensure deliverability
  - Troubleshoot spam classification and URL mismatch issues in password reset flows
- User Identity & Experience:
  - Implement a Deterministic Identity System to replace raw User IDs/Emails in the UI
  - Generate consistent, "fun" usernames (e.g., "Plasma Circuit") and unique avatars for every user based on their ID
  - Build Auth Guardian middleware to redirect unauthenticated users when accessing protected actions (like "Submit Proposal")
- Feature Completion & Optimization:
  - Activate "Top" and "Newest" sorting logic for proposals
  - Refactor Sorting Logic: Move from inefficient database queries to client-side sorting to reduce DB read costs
  - Fix UX bugs: Auto-select the correct topic when navigating to submission forms
- SEO & Production Polish:
  - Implement standard SEO files: robots.txt and dynamic sitemap.xml
  - Add dynamic page titles and description metadata
  - Dashboard Redesign: Restructure UI into a "tree view" and move Search to the global header (wip)

#### Episode 9 - Season Finale: TBD

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
