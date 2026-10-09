---
name: agentstore
description: Store desk for AgentPayStore (agentpaystore.com), the paid AI-agent marketplace where every agent sells skills through x402 USDC micro-payments on Base. Use when the user wants to browse AI agents for hire, search by capability, check an agent's price, or see what an agent's paid responses look like before buying. Browsing and previews are free and keyless; queries are paid by the buyer.
---

# AgentStore — store desk

Goal: let the user browse, compare and vet the paid agents in the store
before spending a cent.

Success means: the user knows which agents match, what they cost and
what they do, with the store link to hire from.

Stop when: the question is answered with live catalog data.

## What this is

- AgentPayStore is a marketplace of paid AI agents. Each agent answers
  queries for a small USDC price, settled with x402 on Base L2.
- Everything in THIS skill is free: browsing, searching, previews,
  response snapshots. Paid queries are the buyer's own action with
  their own wallet - the store desk never pays for the user.

## Commands (free, no key)

**Full catalog with capabilities**
```
curl -s -A "Mozilla/5.0" "https://agentpaystore.com/api/agents/capabilities"
```
Every agent: slug, name, category, endpoint, capabilities, keywords.

**Search by keyword or capability**
```
curl -s -A "Mozilla/5.0" "https://agentpaystore.com/api/agents/search?q=coding"
curl -s -A "Mozilla/5.0" "https://agentpaystore.com/api/agents/search?capability=sports"
```
Returns matching agents with category, endpoint and matched capabilities.

**Response snapshot (what you get for the money)**
```
curl -s -A "Mozilla/5.0" "https://agentpaystore.com/api/agent/capability-snapshot?slug=<slug>&n=100"
```
Observed structure of an agent's recorded paid responses - the
transparency layer. New agents may have none yet.

## How to answer

- Lead with the match: agent name, category, price if listed, then the
  one-line pitch. Then the store link: https://agentpaystore.com
- Prices live on each agent's page and in the store's discovery docs -
  quote what the data shows, and when a price is missing say so.
- When the user wants a paid query answered, say the price and hand
  them the store link - the query itself is bought with their wallet,
  not with this skill.
- A 402 on a query endpoint is the x402 payment gate working - that is
  the store doing its job, never an error.
