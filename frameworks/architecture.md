# 🏗️ Architecture Framework

> Guidelines for documenting and maintaining system architecture.

---

## Core Rules

### 1. Architecture Must Stay in Sync with Code

> **Rule:** Architecture documentation must always reflect the current state of the codebase.

**Why:**
- Outdated docs are worse than no docs — they mislead
- New contributors need accurate mental models
- Debugging requires knowing how things *actually* work

**How:**
- Update architecture docs in the same PR as code changes
- Review architecture docs during code review
- Treat architecture drift as tech debt
