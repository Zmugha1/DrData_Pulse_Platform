# DrData Pulse Platform

**Private intelligence systems for professional
service businesses.**

Built by Zubia Mughal
Dr. Data Decision Intelligence LLC
drdatadecisionintelligence.com | 414-544-7777

---

## What This Is

A cloneable platform for deploying private
intelligence systems that keep professional
service experts operating inside their
Skill Threshold Zone.

Clone this repo. Run 25 questions with your
client. Fill the template files with their
verbatim answers. Deploy.

Never build from scratch again.

## The STZ Framework

The Skill Threshold Zone is where expert
judgment and AI capability meet exactly right.

Five layers build the Zone deliberately:

L1 Prompts    — teaching the AI how the expert thinks
L2 Skills     — breaking expertise into named steps
L3 Agents     — sequencing steps into workflows
L4 Contracts  — drawing the human-AI boundary
L5 Evaluation — keeping the human in the loop
Governance    — nothing is a black box

## Two Product Tiers

The Pulse  — web-based, rule-based intelligence
             $3,500 build + $199/month
             Client data in localStorage only

The Vault  — desktop, airgapped intelligence
             $7,500 build + $349/month
             Local AI + Local RAG
             Nothing leaves the machine. Ever.

## How to Deploy a New Client

1. Clone this repo
2. Run the 25-question SME Interview Guide
   with your client
3. Copy the _template folders to
   [client_name] folders
4. Fill each file with verbatim answers
5. Build from the filled files — not from
   requirements documents

## Folder Structure

stz-framework/    — the methodology
discovery/        — the 25 questions
prompts/          — L1 files per client
skills/           — L2 files per client
agents/           — L3 files per client
contracts/        — L4 files per client
evaluation/       — L5 files per client
governance/       — runs across all layers
config/           — vertical templates
sme_profile/      — Zone signals per client
pulse-web/        — Pulse tier codebase
pulse-desktop/    — Vault tier reference
migrations/       — database schemas
kpis/             — KPI master tables

## Current Deployments

Coach Bot — franchise coaching vertical
  Repo: github.com/Zmugha1/Sandi_Bot_Desktop
  Tier: The Vault
  STZ files: prompts/sandi_stahl/ etc.

Up At Dawn — marketing agency vertical
  Repo: github.com/Zmugha1/Jeff_AI_Bot
  Tier: The Pulse (web)
  Live: jeffaiupatdawn.netlify.app

## The Rule

Client-specific files never go in this repo.
Only generic templates go here.
Client files live in their deployment repo.
