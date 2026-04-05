# Pre-Mortem — How Deal-Safer Could Fail

> "It's 6 months later. The project is dead. What killed it?"

---

## Scenario 1: The Hallucination Lawsuit
**What happened**: AI confidently cited a law that doesn't exist. User acted on it. Lost money. Blamed us.
**Likelihood**: Medium (without mitigation)
**Defense**:
- All legal claims MUST be sourced from a live `korean-law-mcp` API call
- UI shows citation source for every claim ("근거: 하도급거래 공정화에 관한 법률 제4조")
- Prominent disclaimer: "This is negotiation assistance, not legal advice"
- No API response = no legal claim made

---

## Scenario 2: The Complexity Wall
**What happened**: Real contracts are 40-page PDFs with cross-references, attachments, and legalese. The system can't handle them.
**Likelihood**: High (if we try to boil the ocean in v1)
**Defense**:
- v1 scope is ruthlessly narrow: **3 contract types only** (하도급, 임대차, 용역)
- Start with 5-page sample contracts for the demo
- Identify the top 10 poison clauses per contract type — check those first

---

## Scenario 3: The "So What" Demo Failure
**What happened**: Demo runs, outputs something, but evaluators say "this is just ChatGPT with a UI."
**Likelihood**: Medium
**Defense**:
- Demo script uses a **real, ugly subcontractor contract** (not a clean fake)
- Show the MCP call happening live — prove the law API is being hit in real-time
- Before/after: show the original clause → show the redlined fix → show the counter-email
- The "wow moment" must be the email draft. That's the magic.

---

## Scenario 4: The Legal Gray Zone
**What happened**: Professors or evaluators raise liability concerns — "you're practicing law without a license."
**Likelihood**: Low-Medium
**Defense**:
- We provide **negotiation assistance**, not legal advice (same as Grammarly ≠ editor)
- Precedent: Rocket Lawyer, LegalZoom, DoNotPay all operate in this space
- All outputs include: "이 분석은 협상 참고용이며 법적 조언이 아닙니다"

---

## Scenario 5: The MCP Setup Hell
**What happened**: `korean-law-mcp` is hard to configure, breaks, or the API is down during demo.
**Likelihood**: Medium
**Defense**:
- Set up and test MCP connection **this week**, not the night before
- Prepare a **cached fallback** (pre-fetched law text) for demo day
- Have a backup demo video recorded in case live demo fails

---

## Kill Conditions (when to pivot)

| If this happens | Then do this |
|---|---|
| MCP 법령 API is unusable | Switch to static 법령 text + RAG |
| 3 contract types are too complex | Narrow to 1 (하도급 only) for demo |
| Demo build takes > 2 weeks | Cut redline feature, keep scan only |
| Team capacity collapses | Pre-record demo, present as "v0.1 proof of concept" |
