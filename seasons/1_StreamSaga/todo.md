Today
- [ ] Research how redirect links work: confirmation, reset, etc.
- [ ] Use /auth/callback for normal login to use ?code and apply session directly || OR Redirect user to log in page after sign up
- [ ] Sign in with Web3
- [ ] Test functionality and fill the todo list
- [ ] Reset password functionality (from UI / admin panel)
- [ ] Only allow confirmed users to log in
- [ ] Confirmation email template

Later
- [ ] Connect SMTP server (resend.com)
- [ ] SEO stuff
- [ ] Ratelimit: Supabase: Database Size, Egress
- [ ] Backups
- [ ] Change design to something more user friendly and browseable
- [ ] Mobile layout
- [ ] Feature: Admin can ban users
- [ ] Research: Cache for the search or how to not hit the quotas of Supabase?

Done
- [x] ARCHITECTURE.md or similar
- [x] Try new idea about architecture updates rules
- [x] Add `admin` role support for users with gated access to admin panel
- [x] Add "Create Topic" feature
- [x] Add "Search" feature for Topics during creation
- [x] Upgrade React to safe version
- [x] Add "Create Proposal" feature
- [x] Add "Search" feature for Proposals during creation
- [x] Add "Remove Proposal" feature
- [x] Add "Vote" / "Unvote"
- [x] Add "Approve Proposal" feature for admin that resolves the "Topic"
- [x] Fix admin action "Archive Topic"
- [x] Fix "Vote" functionality on the similar proposals window
- [x] Research: Rate limits: embeddings, proposals, etc.
- [x] Ratelimit: OpenAI (limit embeddings generation): per-user rate limit: Use Cloudflare internal rate limiter for embeddings generation
- [x] Deploy
- [x] Connect domain
- [x] Change email confirmation to something more beautiful
