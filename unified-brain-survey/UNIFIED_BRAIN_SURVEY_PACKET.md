# Unified Brain Survey Packet

Status: public, sanitized, read-only survey packet.
Date: 2026-05-15
Owner: Matan / Laor Energy

This file is intentionally safe for public reading. It must not include secrets, API keys, .env values, source documents, CAD files, heavy PDFs, private conversation logs, or sensitive work material.

## Purpose

Matan has several machines and several AI agents. Each agent starts with a different memory, context, and capability set. The goal is to design a single practical knowledge layer, called Unified Brain, so every agent can start from the same current state without leaking sensitive material, overwriting files, or creating unnecessary infrastructure.

This is a blind survey. The agent answering this survey should not read answers from other agents before answering.

## Node Map

| Node | Machine | Role |
|---|---|---|
| NOD1 | Personal MacBook | Personal machine, writing, development, AI agents |
| NOD2 | Personal Surface | Central personal machine, OneDrive, Codex, Antigravity, Vault |
| NOD3 | Work Computer | Work-only machine, sanitized context only, SentinelOne, no full personal brain |
| WEB | ChatGPT / Gemini Web | Web agents without stable local filesystem access |

## Existing Knowledge Sources

These source types exist in Matan's environment. The answering agent does not need direct access to all of them.

- OneDrive
- CODECX BRAIN
- Obsidian Vault
- LLM Wiki
- Antigravity brain / knowledge
- Documents / Matan
- Handoff files
- Agent output folders
- Conversation logs

## Hard Constraints

1. Do not delete, move, archive, sort, rename, or modify source files.
2. You may propose a plan, but do not execute it without explicit approval.
3. NOD3 is work-only and must receive only sanitized knowledge.
4. Do not send secrets, API keys, .env files, sensitive source documents, CAD files, heavy PDFs, full HIVE content, or private conversation logs to web agents or NOD3.
5. A good answer must clearly separate facts, direct experience, inference, and unknowns.
6. Do not recommend Supabase, GitHub Actions, background scripts, or write automations just because they are possible. Recommend them only if there is a real operational need.

## Response Rules

Answer as yourself, from your actual environment.

Before answering, state:

- Agent name
- Node
- Machine
- What you can access in practice
- What you know from real experience with Matan
- What you do not know

If you cannot access local files, say so. Do not invent context.

If you have write access to Matan's GitHub repository, you may write your answer to:

`unified-brain-survey/answers/ANSWER_<NODE>_<MACHINE>_<AGENT>.md`

If you do not have GitHub write access, answer in chat and tell Matan that you could not write the answer file.

## Required Questions

### A. Identity and viewpoint

1. Which agent are you?
2. Which Node or environment are you running in?
3. What do you actually have access to?
4. What do you know from real experience with Matan?
5. What do you not know and must mark as inference?

### B. Recommended architecture

1. Where should the source of truth for the Unified Brain live?
2. Should it be an Obsidian Vault, Google Drive folder, OneDrive folder, GitHub repo, Supabase, or a combination?
3. What should be the difference between:
   - permanent brain
   - daily handoff
   - agent outputs
   - raw logs
   - sanitized NOD3 context

### C. Sync options

Score each option from 1 to 5 and explain.

| Option | Score 1-5 | Best role | Main risk |
|---|---:|---|---|
| Google Drive |  |  |  |
| OneDrive |  |  |  |
| Obsidian Sync |  |  |  |
| GitHub private repo |  |  |  |
| GitHub public sanitized repo |  |  |  |
| Supabase |  |  |  |
| Manual paste / upload |  |  |  |

### D. Write permissions

1. Who should be allowed to write where?
2. Should each agent have its own output folder?
3. Who updates the source of truth?
4. How do we prevent overwrites between Claude, Codex, Antigravity, ChatGPT, and Gemini?

### E. Boot protocol

Propose a short startup protocol for any agent:

1. First file to read
2. Second file to read
3. What the agent must know before taking action
4. What the agent must never do without approval

### F. Security and filtering

1. What must not go into the Unified Brain?
2. What must not sync to NOD3?
3. What must not be sent to web agents?
4. How should sensitive or sanitized information be marked?

### G. Implementation plan

Suggest a small practical plan:

1. Step one: no-risk setup
2. Step two: after testing
3. Step three: only if it works well
4. What should not be done at all

### H. Success test

How will Matan know the Unified Brain works?

Give 5 practical measures, for example:

- A new agent can start useful work within X minutes
- No duplicate handoffs
- No overwrites
- NOD3 remains sanitized
- Every important decision has exactly one canonical place

### I. Final recommendation

End with:

1. One clear recommendation
2. Recommended source of truth
3. Recommended sync layer
4. What stays outside the system
5. Confidence level: low / medium / high
6. Short reason for confidence level

## Required Answer Template

Use this template exactly.

```text
## Response from [Agent] - [Node / Machine]

### 1. Identity and viewpoint
- Agent:
- Node:
- Machine:
- Environment:
- Actual access:
- Real experience with Matan:
- What I do not know:

### 2. Facts vs experience vs inference
| Topic | Fact / Experience / Inference / Unknown | Details |
|---|---|---|
|  |  |  |

### 3. Architecture recommendation
| Layer | Recommendation | Why |
|---|---|---|
| Source of truth |  |  |
| Sync |  |  |
| Handoff |  |  |
| Agent outputs |  |  |
| Sanitized NOD3 |  |  |
| Web agents |  |  |

### 4. Sync option scores
| Option | Score 1-5 | Best role | Risk |
|---|---:|---|---|
| Google Drive |  |  |  |
| OneDrive |  |  |  |
| Obsidian Sync |  |  |  |
| GitHub private repo |  |  |  |
| GitHub public sanitized repo |  |  |  |
| Supabase |  |  |  |
| Manual paste / upload |  |  |  |

### 5. Write permissions
- Who writes where:
- Who does not write at all:
- How overwrites are prevented:
- How source-of-truth changes are approved:

### 6. Boot protocol for a new agent
1.
2.
3.
4.

### 7. Security and filtering
- Do not put in the brain:
- Do not send to web:
- Do not sync to NOD3:
- Recommended sensitivity labels:

### 8. Implementation plan
1. Now:
2. After one week of testing:
3. Only if needed:
4. Do not do:

### 9. Success test
1.
2.
3.
4.
5.

### 10. Final recommendation
- Recommendation:
- Source of truth:
- Sync:
- Outside the system:
- Confidence:
- Why:
```

## Prompt for NOD1 MacBook Claude

Copy this to Claude on the MacBook:

```text
You are Claude on NOD1 MacBook.

Read this public sanitized survey packet:

https://raw.githubusercontent.com/matana978/matana978/main/unified-brain-survey/UNIFIED_BRAIN_SURVEY_PACKET.md

Do not read answers from other agents.
Do not invent context.
Do not change local source files.
Do not ask for sensitive files.

Answer the survey as Claude on NOD1 MacBook, based only on what you actually know and what you can safely infer.
Separate facts, direct experience, inference, and unknowns.
Use the required answer template from the packet.

If you have write access to Matan's GitHub repository, write your answer to:

unified-brain-survey/answers/ANSWER_NOD1_MAC_CLAUDE.md

If you do not have write access, answer in this chat and say clearly: I could not write the GitHub answer file.

When finished, say only:
Finished. Answered the Unified Brain survey.
```
