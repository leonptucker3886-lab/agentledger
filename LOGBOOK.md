# AgentLedger Logbook

## 2026-10-27 - v0.1 first draft
- Built a single-page app: agents, shared memory with search and tags, approval queue (approve/deny with note), audit trail with CSV download, JSON export/import, reset.
- Deployed to Vercel: https://agentledger-tan.vercel.app ; subdomain agentledger.leonlink.net added (needs CNAME to cname.vercel-dns.com if not already present).
- Wrote HOWTO.md and a step-by-step PDF. Not linked from the main site.

## 2026-10-27 - Self-review: what could be better
1. **The audit trail claim was too strong.** v0.1 said entries "can't be edited", but they were plain browser storage anyone could change. An audit tool that overstates its guarantees is a defect.
2. **Agents could approve their own requests.** That defeats the point of an approval queue.
3. **Removing an agent erased authorship.** Their memories and requests then showed "Unknown".
4. **Destructive actions had no confirmation.** One click removed an agent or deleted a memory.
5. **Import was loosely checked.** A partial file could load, ID counters could collide, and there was no check of the audit trail's integrity.
6. **Pending approvals were easy to miss** from other tabs.

## 2026-10-27 - v0.2 polish
- Audit trail is now a SHA-256 hash chain: each entry stores the previous hash and its own. New **Verify chain** button flags the first broken or tampered entry. CSV export includes the hashes. Wording now says tampering is *detectable*, not impossible.
- Self-approval blocked: the decider's name can't match the requesting agent.
- Memories and requests keep a snapshot of the author's name.
- Confirmation dialogs before removing an agent or deleting a memory.
- Import requires all four collections, asks before replacing, repairs the ID counter, verifies the chain and logs the result.
- Pending-approval count shown on the Approvals tab.
- HOWTO.md updated to match.

## Known limits / next
- Data still lives in one browser. Phase 2: Supabase backend so all agents share one live ledger, with the hash chain stored server-side.
