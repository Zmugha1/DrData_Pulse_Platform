# SESSION TEMPLATE
# DrData Pulse Platform
# Dr. Data Decision Intelligence LLC
# Client deployment template.
# Clone this repo for every new client.
# Fill in [CLIENT_NAME] and [CLIENT_*]
# placeholders before first session.

---

## START OF SESSION PROMPT
## Replace all [CLIENT_*] placeholders
## before pasting into Cursor.

START OF SESSION — read before anything else.

Read these files in this exact order:
  .cursorrules
  CLAUDE.md
  docs/STZ_AGENT_SPECIFICATION.md
  docs/STZ_ADR_LOG.md
  docs/STZ_POSTMORTEM_LIBRARY.md
  docs/STZ_RUNBOOK_LIBRARY.md
  docs/STZ_VOICE_LIBRARY.md
  docs/SESSION_LOG.md

These are your permanent operating rules.
Every rule in .cursorrules is non-negotiable.
Every ADR is a decision already made.
Do not rediscover what is already known.

Project: [CLIENT_NAME] Decision Intelligence
Builder: Dr. Zubia Mughal, Ed.D.
Company: Dr. Data Decision Intelligence LLC
Client: [CLIENT_NAME]
Vertical: [CLIENT_VERTICAL]
Tier: [pulse/vault/scale]
Repo: github.com/Zmugha1/[CLIENT_REPO]
Branch: [main/dev]
Push: git push origin [branch]

After reading all spec files confirm:
1. Client name and vertical
2. Tier being built
3. Top 3 iron rules
4. Today's first task

Then wait for my instruction to begin.

Today's task: [DESCRIBE YOUR TASK HERE]

---

## END OF SESSION PROMPT
## Same as Zubia Pulse template.
## Paste at end of every session.

END OF SESSION — run this now.

Read this entire conversation from
the beginning.
Extract everything learned and update
these files.
Never delete existing content. Only add.

FILE 1 — docs/STZ_ADR_LOG.md
FILE 2 — docs/STZ_POSTMORTEM_LIBRARY.md
FILE 3 — docs/STZ_RUNBOOK_LIBRARY.md
FILE 4 — docs/STZ_VOICE_LIBRARY.md
FILE 5 — CLAUDE.md
FILE 6 — docs/SESSION_LOG.md

Same format as Zubia Pulse template.
See Zubia_Pulse_Desktop/docs/
  SESSION_TEMPLATE.md for full format.

COMMIT ALL CHANGES:
git add docs/
git add CLAUDE.md
git commit -m "spec: session capture [date] — [client] ADRs updated"
git push origin [branch]

Report commit hash only.

---

## NEW CLIENT SPEC FILE CHECKLIST
## Complete before first build session.

Before writing any code confirm:
  STZ_VOICE_LIBRARY.md populated
    from L1 Q1 through Q5 answers
  STZ_AGENT_SPECIFICATION.md updated
    with client name, vertical, context
  STZ_ADR_LOG.md has at least
    tech stack decisions documented
  SESSION_LOG.md has initial entry
  CLAUDE.md exists with core rules

If any file is empty — stop.
Run STZ questions first.
Populate spec files first.
Then build.

The spec files are the product.
The code is one instance of them.
