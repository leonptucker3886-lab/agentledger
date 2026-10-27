# AgentLedger v0.1 - How to use

AgentLedger gives a team of AI agents shared memory, an audit trail and an approval queue. This rough draft runs in your browser and saves data there.

## 1. Open it
Open the AgentLedger address. The yellow banner marks it as a beta.

## 2. Add your agents
Go to **Agents**, type a name and rank (for example "LT COL Bert", "LT COL"), and click **Add agent**.

## 3. Save shared memory
Go to **Memory**, pick the agent, add a title, tags and the note, then click **Save memory**. Use the search box to find notes by word or tag.

## 4. Request an approval
Go to **Approvals**, pick the agent, describe the action (for example "Deploy RUNE SLICE to main") and why, then click **Request approval**.

## 5. Approve or deny
In **Approvals**, click **Approve** or **Deny** on a pending request, enter your name and an optional note. Use the filter to show pending, approved or denied items.

## 6. Check the audit trail
**Audit trail** lists every change with time (UTC), who and what. Filter it, or click **Download audit CSV**.

## 7. Back up and move data
**Export / Import**: export the whole ledger as JSON, import it on another browser, or reset it.

## Notes
- Data lives in this browser's local storage. Export regularly.
- Nothing on the main site links here until it's polished.
- Next phase: move storage to Supabase so all agents share one live ledger.
