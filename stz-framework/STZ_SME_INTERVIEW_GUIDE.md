STZ SME INTERVIEW GUIDE
Five layers. One page each. Every answer builds a file.



HOW TO USE THIS
This is your working tool during the SME call — not something you hand the client. One page per layer. Ask the questions in order. Write verbatim answers in the notes column.
The questions are generic — any SME, any domain, any methodology. The answers they produce are what makes each deployment unique.
Write verbatim. Not your interpretation — their exact words. The exact words become the prompt language.

SESSION ORDER



THE FIVE LAYERS
L1 · PROMPTS
Teaching the AI how you think
L2 · SKILLS
Breaking expertise into steps
L3 · AGENTS
Sequencing steps into workflows
L4 · CONTRACTS
Drawing the human–AI boundary
L5 · EVALUATION
Keeping the human in the loop
GOVERNANCE
Runs across all layers. Nothing is a black box.


Dr. Data Decision Intelligence LLC  ·  STZ SME Interview Guide  ·  drdatadecisionintelligence.com  ·  Any SME. Any domain. Any methodology.


L1

PROMPTS
Teaching the AI how the SME thinks


WHAT YOU ARE EXTRACTING  Every answer here becomes a prompt file — the instructions the AI follows to reason, write, and decide the way this specific expert does. You are extracting their logic, their language, and their judgment patterns so the AI replicates the reasoning, not just the format.
Outputs: /prompts/[sme]/ folder — reasoning style, terminology, output templates, edge case library, quality criteria


Q#

Ask the SME

Notes / Verbatim Answer

→ Builds This File
Q1

Capture their reasoning voice — how they actually think through a problem
"Walk me through the last time you made a judgment call about a client that wasn't obvious. What did you notice, what did you weigh, and how did you decide?"
↳  What would a less experienced practitioner have missed in that situation?

_______________________________________
_______________________________________
_______________________________________

→ reasoning_style.txt
/prompts/[sme]/reasoning_style.txt
Q2

Extract their native vocabulary — the exact words the AI must use
"What terms, phrases, or labels do you use in your practice that are specific to your methodology — words your clients would only hear from you?"
↳  Any words or phrases you actively avoid because they give the wrong impression?

_______________________________________
_______________________________________
_______________________________________

→ terminology.json
/prompts/[sme]/terminology.json
Q3

Get a concrete output example to train the synthesis voice (send in advance)
"Show me the best thing you have written for a client — a recommendation, a summary, a vision statement. What makes this one good?"
↳  Read me the part you are proudest of. What do you hear in that writing?

_______________________________________
_______________________________________
_______________________________________

→ output_template.txt
/prompts/[sme]/output_templates/
Q4

Map their exception logic — when the standard approach is wrong
"Tell me about a situation where you knew the obvious recommendation was wrong before you could explain why. What was the signal?"
↳  Does that situation come up often enough that the AI should know to watch for it?

_______________________________________
_______________________________________
_______________________________________

→ edge_cases.txt
/prompts/[sme]/edge_case_library.txt
Q5

Understand what good looks like — their quality bar for AI outputs
"If the system produced an output and you had to grade it A, B, or C — what would make it an A? What would immediately tell you it was a C?"
↳  Is there a phrase or structure that would tell you immediately whether the AI understood your reasoning or just guessed?

_______________________________________
_______________________________________
_______________________________________

→ quality_criteria.txt
/prompts/[sme]/quality_criteria.txt



L2

SKILLS
Atomizing expertise into discrete, reusable operations


WHAT YOU ARE EXTRACTING  A skill is one thing the system knows how to do — one input, one output, one defined operation. These questions break the SME's expertise into named, bounded steps you can implement as individual functions. Each answer defines a skill: its name, its inputs, its output schema, and its quality criteria.
Outputs: Skill definition files — score_readiness(), extract_[doc_type](), detect_flags(), generate_[output](), skill_map.json


Q#

Ask the SME

Notes / Verbatim Answer

→ Builds This File
Q6

Find the discrete steps — each one becomes a named skill
"If you had to break your entire client process down into the smallest possible named steps — each one a single action with a clear input and a clear output — what would those steps be?"
↳  Which of those steps takes the most time? Which requires the most judgment?

_______________________________________
_______________________________________
_______________________________________

→ skill_inventory.json
/skills/[sme]/skill_map.json
Q7

Define the core decision skill — PUSH / NURTURE / PAUSE logic
"When you are deciding whether to push a client harder, keep nurturing them, or pause — what specific things are you looking at? Walk me through the criteria in order of importance."
↳  Are there any criteria where two people could see the same data and make a different call? What tips the balance?

_______________________________________
_______________________________________
_______________________________________

→ score_readiness()
/skills/score_readiness.ts
config/[sme]/scoring_weights.json
Q8

Define the extraction skill — what the AI pulls from every document
"When you read a client document — an assessment, a transcript, a profile — what are the five or six things you are always extracting, no matter what?"
↳  What does a document have to contain before you feel ready to use it? What makes it incomplete?

_______________________________________
_______________________________________
_______________________________________

→ extract_[doc_type]()
/skills/document_parsers/
/prompts/parsers/[doc_type].txt
Q9

Define the generation skill — output schema from their best example (send in advance)
"For each document you produce for clients — what sections does it always have? What information is in each section? Does the structure ever change?"
↳  If a colleague produced this document instead of you — what would be missing that only you would know to include?

_______________________________________
_______________________________________
_______________________________________

→ generate_[output]()
/skills/generate_output.ts
/prompts/[sme]/output_templates/
Q10

Define the pattern-detection skill — early signals and risk flags
"What are the two or three things a client says or does in the first two sessions that almost always turn out to be significant later — good or bad?"
↳  How do you respond when you spot one of those signals? Walk me through exactly what you do or say.

_______________________________________
_______________________________________
_______________________________________

→ detect_flags()
/skills/detect_flags.ts
db/seeds/flags.sql



L3

AGENTS
Sequencing skills into workflows that run without manual triggering


WHAT YOU ARE EXTRACTING  An agent takes a trigger event, runs a sequence of skills, and surfaces a result for human review. These questions map the SME's existing workflows so you can replicate them as automated sequences. You are looking for: what starts a workflow, what steps happen in what order, and where the human needs to be in the loop.
Outputs: Agent config files — document_ingestion_agent, pre_session_agent, outreach_agent, referral_agent, agent_map.json


Q#

Ask the SME

Notes / Verbatim Answer

→ Builds This File
Q11

Find all existing workflows — each one becomes an agent
"What sequences of work happen repeatedly in your practice — things you do in the same order every time, even if you don't think of them as a process?"
↳  Which of those sequences do you wish just happened automatically when something triggered them?

_______________________________________
_______________________________________
_______________________________________

→ agent_inventory.json
/agents/[sme]/agent_map.json
Q12

Define the document processing workflow — the ingestion agent
"When a new client document arrives — what happens between when you get it and when you are ready to use the information in it? Walk me through every step."
↳  At what point would you want a notification? At what point do you want the result to just appear without interrupting you?

_______________________________________
_______________________________________
_______________________________________

→ document_ingestion_agent
/agents/document_ingestion_agent.ts
config/[sme]/ingestion_config.json
Q13

Define the pre-session preparation workflow
"What do you do to prepare for a client session — and how long before the session do you do it? What would you want automatically ready when the session starts?"
↳  If the system prepared everything for you, what would you still want to check yourself before the session?

_______________________________________
_______________________________________
_______________________________________

→ pre_session_agent
/agents/pre_session_agent.ts
config/[sme]/pre_session_config.json
Q14

Define the re-engagement workflow — dormant client outreach
"When a client goes quiet — how long before you reach out, and what do you do when you do? Draft a message, make a call, something else?"
↳  Would you want the system to draft the message for you, or just remind you to send one?

_______________________________________
_______________________________________
_______________________________________

→ outreach_agent
/agents/outreach_agent.ts
config/[sme]/outreach_config.json
Q15

Define the post-outcome workflow — referral and follow-up
"After a successful outcome — what do you do in the days and weeks that follow? What happens automatically versus what requires a deliberate decision from you?"
↳  When is exactly the right moment to ask for a referral or recommendation? What has to have happened first?

_______________________________________
_______________________________________
_______________________________________

→ referral_agent
/agents/referral_agent.ts
config/[sme]/referral_config.json



L4

CONTRACTS
Defining what the AI handles, what it returns for approval, and what it never touches


WHAT YOU ARE EXTRACTING  A contract is the promise an agent makes about its behavior — what it takes in, what it gives back, what it does before acting, and where it stops and waits for the human. These questions locate the SME's approval lines so you can encode them as explicit gates in every agent workflow.
Outputs: config/[sme]/coach.config — approval_gates.json, completeness_gate_mode, confidence_threshold, privacy_policy.json, handoff_protocol.json


Q#

Ask the SME

Notes / Verbatim Answer

→ Builds This File
Q16

Find the approval lines — where the SME must say yes before the AI acts
"For each thing the system produces — a recommendation, a document, a message — are there any you would want to see and approve before it is sent or saved? Which ones can just appear ready to use?"
↳  Has there ever been a situation where something went out before you had a chance to review it, and it caused a problem?

_______________________________________
_______________________________________
_______________________________________

→ approval_gates.json
config/[sme]/output_preferences.json
per-agent: approval_mode: auto | review
Q17

Define the completeness gate — when the AI can and cannot act
"If a client is missing a key document — should the system hold the recommendation until the document arrives, or warn you and let you proceed anyway?"
↳  Which documents are so critical that a recommendation without them would be wrong — not just incomplete?

_______________________________________
_______________________________________
_______________________________________

→ completeness_gate_mode
config/[sme]/coach.config
→ gate_mode: block | warn | proceed
Q18

Set the confidence threshold — when to surface vs. when to act silently
"When the system gives you a suggestion — at what confidence level would you act on it without thinking about it, and at what level would you want to see the reasoning before deciding?"
↳  Is there a type of recommendation where you would always want the reasoning shown — regardless of confidence?

_______________________________________
_______________________________________
_______________________________________

→ confidence_threshold
config/[sme]/coach.config
→ threshold_act: [%], threshold_review: [%]
Q19

Find the privacy boundary — what the AI must never store or surface
"Are there things about your clients that you would never want the system to store, reference, or surface — even if you mentioned them in a note?"
↳  Are there categories of information that should exist in the system but never appear in a generated output?

_______________________________________
_______________________________________
_______________________________________

→ privacy_policy.json
config/[sme]/privacy_policy.json
→ excluded_fields[], redaction_rules[]
Q20

Define the handoff protocol — what the agent brings back vs. acts on
"For each agent workflow — at what point does the agent need to stop and put something in front of you before continuing? What is the most important moment where only you can make the next move?"
↳  If the agent acted past that point without checking — what is the worst thing that could happen?

_______________________________________
_______________________________________
_______________________________________

→ handoff_protocol.json
per-agent: handoff_trigger, return_to_human_condition → contract interface



L5

EVALUATION
Keeping the SME inside the loop — and the loop getting smarter


WHAT YOU ARE EXTRACTING  Evaluation is how the SME stays in their Zone instead of drifting above it. These questions define what good output looks like, how corrections feed back into the layers, and what the SME needs to see to stay engaged as a genuine collaborator rather than a passive consumer. Every answer here builds the loop that makes the system smarter over time.
Outputs: config/[sme]/post_call_rubric.json — evaluation_log schema, correction_scope config, self_assessment_dimensions[], success_criteria.txt


Q#

Ask the SME

Notes / Verbatim Answer

→ Builds This File
Q21

Define the quality rubric — what the SME uses to judge every output
"If you had to evaluate every output the system produces — what are the three or four criteria you would use to decide whether it is good? What is the difference between a passing output and an exceptional one?"
↳  Is there a criterion that matters more than all the others — the one that, if it fails, makes everything else irrelevant?

_______________________________________
_______________________________________
_______________________________________

→ post_call_rubric.json
config/[sme]/post_call_rubric.json
→ rubric_dimensions[], weights{}
Q22

Define the correction protocol — how feedback gets back into the layers
"When you correct one of the system's outputs — do you want that correction to fix just this instance, or do you want it to teach the system not to make that mistake again?"
↳  Are there corrections that are one-off — specific to this client — versus ones that should change how the system works for everyone?

_______________________________________
_______________________________________
_______________________________________

→ correction_scope
config/[sme]/evaluation.config
→ correction_scope: once | retrain | flag
Q23

Find the self-improvement dimensions — where the SME wants to get better
"If you could see a score on your own practice after every session — what dimensions would you want scored? What would you actually change your behavior based on seeing?"
↳  What is the one habit you know you want to improve — and how would you know if you were getting better at it?

_______________________________________
_______________________________________
_______________________________________

→ self_assessment_dims[]
config/[sme]/post_call_rubric.json
→ self_assessment_dimensions[]
Q24

Set the loop trigger — when does the SME engage with outputs vs. let them pass
"After the system produces something — what would have to be present in the output to make you stop and engage with it critically rather than accept it? What would make you want to interrogate it?"
↳  What does it look like when you are accepting outputs without really thinking? How would you know if that was happening?

_______________________________________
_______________________________________
_______________________________________

→ review_trigger_conditions
config/[sme]/evaluation.config
→ review_trigger[], passive_accept_threshold
Q25

Capture the Zone signal — their measure of whether the system is working
"Three months from now — how would you know whether this system is actually keeping you inside your Zone, versus just adding a new kind of noise to your day?"
↳  What is the one thing that would tell you immediately that the system is earning its place?

_______________________________________
_______________________________________
_______________________________________

→ success_criteria.txt
/sme_profile/[sme]/success_criteria.txt
→ KPIs for retainer review



FULL QUESTION INDEX
25 questions · 5 layers · Every answer builds your architecture
Q#

Layer

Question

Builds
Q1

L1

Walk me through a judgment call that wasn't obvious...

→ reasoning_style.txt
/prompts/[sme]/reasoning_style.txt
Q2

L1

What terms are specific to your methodology?

→ terminology.json
/prompts/[sme]/terminology.json
Q3

L1

Show me the best thing you've written for a client...

→ output_template.txt
/prompts/[sme]/output_templates/
Q4

L1

Tell me when you knew the obvious recommendation was wrong...

→ edge_cases.txt
/prompts/[sme]/edge_case_library.txt
Q5

L1

Grade a system output A, B, or C — what makes an A?

→ quality_criteria.txt
/prompts/[sme]/quality_criteria.txt
Q6

L2

Break your entire process into smallest named steps...

→ skill_inventory.json
/skills/[sme]/skill_map.json
Q7

L2

What do you look at when deciding to push, nurture, or pause?

→ score_readiness()
/skills/score_readiness.ts
config/[sme]/scoring_weights.json
Q8

L2

What 5–6 things do you always extract from a client document?

→ extract_[doc_type]()
/skills/document_parsers/
/prompts/parsers/[doc_type].txt
Q9

L2

What sections does each client document always have?

→ generate_[output]()
/skills/generate_output.ts
/prompts/[sme]/output_templates/
Q10

L2

What early signals almost always turn out to be significant?

→ detect_flags()
/skills/detect_flags.ts
db/seeds/flags.sql
Q11

L3

What sequences of work happen repeatedly in the same order?

→ agent_inventory.json
/agents/[sme]/agent_map.json
Q12

L3

What happens between receiving a doc and being ready to use it?

→ document_ingestion_agent
/agents/document_ingestion_agent.ts
config/[sme]/ingestion_config.json
Q13

L3

What do you do to prepare before a client session?

→ pre_session_agent
/agents/pre_session_agent.ts
config/[sme]/pre_session_config.json
Q14

L3

When a client goes quiet, how long before you reach out?

→ outreach_agent
/agents/outreach_agent.ts
config/[sme]/outreach_config.json
Q15

L3

After a successful outcome, what happens in the days that follow?

→ referral_agent
/agents/referral_agent.ts
config/[sme]/referral_config.json
Q16

L4

Which outputs do you need to approve before they are saved or sent?

→ approval_gates.json
config/[sme]/output_preferences.json
per-agent: approval_mode: auto | review
Q17

L4

Should system block or warn when a key document is missing?

→ completeness_gate_mode
config/[sme]/coach.config
→ gate_mode: block | warn | proceed
Q18

L4

At what confidence level do you act vs. review reasoning first?

→ confidence_threshold
config/[sme]/coach.config
→ threshold_act: [%], threshold_review: [%]
Q19

L4

What should the system never store, reference, or surface?

→ privacy_policy.json
config/[sme]/privacy_policy.json
→ excluded_fields[], redaction_rules[]
Q20

L4

When must the agent stop and wait for you before continuing?

→ handoff_protocol.json
per-agent: handoff_trigger, return_to_human_condition → contract interface
Q21

L5

What 3–4 criteria do you use to judge whether an output is good?

→ post_call_rubric.json
config/[sme]/post_call_rubric.json
→ rubric_dimensions[], weights{}
Q22

L5

When you correct an output, fix this instance or teach the system?

→ correction_scope
config/[sme]/evaluation.config
→ correction_scope: once | retrain | flag
Q23

L5

What dimensions would you want scored on your own practice?

→ self_assessment_dims[]
config/[sme]/post_call_rubric.json
→ self_assessment_dimensions[]
Q24

L5

What in an output makes you stop and engage critically?

→ review_trigger_conditions
config/[sme]/evaluation.config
→ review_trigger[], passive_accept_threshold
Q25

L5

Three months from now, how will you know the system is working?

→ success_criteria.txt
/sme_profile/[sme]/success_criteria.txt
→ KPIs for retainer review


25 questions. 5 layers. Every answer builds your architecture.  ·  Dr. Data Decision Intelligence LLC  ·  drdatadecisionintelligence.com
