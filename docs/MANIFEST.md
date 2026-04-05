# Deal-Safer — Project Manifest

> "The contract is signed before the lawyer is called."

## Mission
Empower SMEs, freelancers, and individuals with zero legal budget to enter every contract negotiation armed — not blindsided.

## Problem
Legal tech today offers two options: download a template, or pay a lawyer.
Neither helps you at the table, in the moment, before you sign.

A single missed poison clause can cost ₩10,000,000+.
The people most exposed are the ones least able to recover from it.

## What We Build
A **real-time contract defense system** that:
1. Takes your side — you declare your stance (tenant / subcontractor / freelancer), and the AI becomes your biased bodyguard
2. Reads the actual contract — not a template, the document they sent you
3. Checks it against live Korean law — via `korean-law-mcp`, zero hallucination
4. Hands you weapons — redlined edits + a polished counter-proposal email, ready to send

## What We Are NOT
- Not a legal chatbot that summarizes law
- Not a template library
- Not a lawyer-matching service
- Not a post-dispute tool

## Core Principles
| Principle | Meaning |
|---|---|
| **Adversarial by design** | We are always on the user's side, never neutral |
| **Actionable, not informational** | Every output is something the user can do right now |
| **Hallucination-zero** | Every legal claim is grounded in a real-time API call |
| **Built by practitioners** | Designed by people who have been on the losing side of a bad contract |

## Target Users (v1)
- Subcontractors dealing with prime contractors (하도급)
- Tenants reviewing lease agreements (임대차)
- Freelancers signing service agreements (용역)

## Tech Stack
- **LLM**: Claude (Anthropic) via MCP
- **Law API**: `korean-law-mcp` (국가법령정보 실시간 연동)
- **Document parsing**: PDF/DOCX ingestion
- **Output**: Redline diff + email draft generator

## Team
Built by practitioners — commercial strategy, public sector operations, B2B business development.
We have been the subcontractor. We have been the tenant. We know where it hurts.
