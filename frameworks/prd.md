# 📝 PRD Framework

> A framework for writing Product Requirements Documents that are clear, actionable, and developer-friendly.

## Overview

This framework captures the patterns we use when defining new projects. A good PRD should answer: *What are we building, for whom, and how does it work?*

---

## 📑 PRD Template

### 1. Project Summary

Start with a one-liner that explains what the product does.

```markdown
# [Project Name]

[One sentence describing what it does and for whom]
```

**Example:** *"An app where stream viewers can propose and vote for projects/features that will be developed live."*

---

### 2. Tech Stack

Define the tools upfront. Split by concern:

```markdown
## Tech Stack

**Development:**
- [Frontend framework]
- [Backend/Database]
- [Auth provider]

**Deployment:**
- [Hosting/Infrastructure]
```

**Considerations:**
- Keep it minimal — fewer tools = less complexity
- Choose based on team expertise and project needs
- Consider free tiers for MVPs

---

### 3. Access Control

Define who can do what before diving into features:

```markdown
## Access

- **Public:** [What anyone can see/do]
- **Authenticated:** [What logged-in users can do]
- **Admin:** [What admins can do]
```

**Why first?** Access levels shape your entire feature set. Define them early.

---

### 4. Data Models

List your entities with their key fields and relationships:

```markdown
## Data Models

All entities have: `createdAt`, `updatedAt`, `archivedAt`

### [Entity Name]
- `id`
- `field1`
- `field2`
- `foreignKey` (FK → OtherEntity)
```

**Best Practices:**
- Include standard timestamps on all entities
- Use soft deletes (`archivedAt`) instead of hard deletes
- Define foreign key relationships explicitly
- Add unique constraints where needed (e.g., one vote per user per proposal)

---

### 5. User Flows

Describe step-by-step what each user type does:

```markdown
## User Flows

### [User Type]
1. [First action]
2. [Second action]
3. [Decision point → options]
```

**Tips:**
- Write flows as numbered steps
- Include decision points and alternatives
- Cover the happy path + key edge cases

---

### 6. Features

List features with scope and key details:

```markdown
## Features

### [Feature Name]
- **Scope:** [Public | Authenticated | Admin]
- [Key detail 1]
- [Key detail 2]
```

**Keep it concise** — implementation details go in technical docs, not the PRD.

---

### 7. Security & Rate Limiting

Always consider abuse prevention:

```markdown
## Rate Limiting & Bot Protection

- **Captcha:** [Where and what service]
- **Rate limits:**
  - [Action]: max [N] per user per [time period]
- **Account age:** [Optional restrictions for new accounts]
```

**Common patterns:**
- Captcha on user-generated content (proposals, comments)
- Rate limits on writes (proposals, votes)
- Account age requirements to prevent spam accounts
- Consider privacy-friendly options (e.g., Cloudflare Turnstile)

---

### 8. Compliance

Consider legal and regulatory requirements:

```markdown
## Compliance

- **Data Privacy:** [GDPR, CCPA considerations]
- **Data Storage:** [Where data is stored, retention policies]
- **User Rights:** [Data export, deletion requests]
- **Third-party Services:** [Data shared with external services]
```

**Common considerations:**
- GDPR (EU users) — consent, right to deletion, data portability
- CCPA (California users) — disclosure, opt-out rights
- Cookie policies and tracking disclosure
- Terms of Service and Privacy Policy requirements
- Age restrictions if applicable

---

### 9. Authentication

Define auth methods:

```markdown
## Authentication
- [Method 1] (e.g., Email magic link)
- [Method 2] (e.g., OAuth provider)
```

**Consider:**
- Your target audience (Twitch viewers → Twitch OAuth makes sense)
- Friction vs security tradeoffs
- Email as fallback for account recovery

---

## ✅ PRD Checklist

Use this to validate your PRD is complete:

- [ ] **Summary** — One-liner explaining the product
- [ ] **Tech Stack** — Development + Deployment tools defined
- [ ] **Access Control** — Who can do what (Public/Auth/Admin)
- [ ] **Data Models** — Entities, fields, relationships, constraints
- [ ] **User Flows** — Step-by-step for each user type
- [ ] **Features** — Scoped feature list with key details
- [ ] **Security** — Rate limits, captcha, abuse prevention
- [ ] **Authentication** — Auth methods and providers

---

## 📎 Example

See a complete PRD example: [StreamSaga PRD](../seasons/1_StreamSaga/prd.md)

---

## 💡 Tips

1. **Start with access control** — it shapes everything else
2. **Use soft deletes** — you'll thank yourself later
3. **Define constraints early** — "one vote per user per proposal" prevents bugs
4. **Think about abuse** — rate limits and captcha from day one
5. **Keep it readable** — tables and lists over paragraphs
6. **Version your PRD** — it will evolve, that's okay
