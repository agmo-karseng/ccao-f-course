---
title: "4. Workflow Integration & Solution Design"
nav_order: 6
---

# Module 4 — Workflow Integration and Solution Design (Domain 4, 16%)

> **Blueprint objectives covered in this module**
>
> 1. Apply Claude to analyze requirements and use cases
> 2. Leverage Claude for research, planning, and process optimization
> 3. Use Claude to support solution design, development, and iteration
> 4. Integrate Claude into existing workflows to augment or redesign them
> 5. Communicate Claude's value and limitations to stakeholders

---

## Why this domain matters

Domain 4 carries 16% of the exam — the second-highest weight — because it tests the skill that separates a certified Associate from a casual prompt user: turning business problems into working, sustainable Claude solutions. The exam guide describes the target candidate as someone who "moves beyond basic question-and-answer usage to process reimagination, task automation, and project development," and who can "translate business objectives into effective AI interactions." Expect scenario questions where you must pick where Claude fits in a process, decide between augmenting and redesigning a workflow, iterate a solution based on feedback, and explain value and limitations honestly to stakeholders — including knowing when the work belongs to a Claude Architect or Developer instead of you.

---

## 4.1 Apply Claude to analyze requirements and use cases

### The core skill

Before building anything with Claude, an Associate clarifies **what problem is being solved, for whom, and what "good" looks like**. Claude itself is a strong partner for this analysis: it can interview you about a fuzzy request, restructure stakeholder notes into requirements, surface unstated assumptions, and identify which parts of a process are actually suitable for AI assistance.

### A simple requirements-analysis pattern

When a stakeholder brings a vague request ("Can AI help our onboarding process?"), work through four questions — and use Claude to help answer each:

1. **Outcome** — What measurable result does the stakeholder want (faster cycle time, fewer errors, more consistent output)?
2. **Inputs** — What information does the task consume? Is it text-based, digitized, and shareable under your organization's data policy?
3. **Judgment profile** — Which steps are mechanical (summarize, reformat, extract, draft) and which require human authority (approve, decide, sign off)?
4. **Constraints** — Data sensitivity, regulatory rules, tone/brand requirements, deadlines, and who must review the output.

A practical prompt pattern for this stage:

```
You are helping me analyze a business process for AI suitability.
Here are my interview notes with the HR team: [paste notes]

1. Restate the problem in one sentence.
2. List the explicit requirements and any implicit ones you can infer.
3. Flag ambiguities or missing information as questions I should ask.
4. Identify which steps involve routine text work vs. human judgment calls.
```

Asking Claude to *flag ambiguities as questions* rather than guess is a Domain 4 habit the exam rewards: requirements analysis is about exposing unknowns, not papering over them.

### Judging use-case suitability

Strong Claude use cases typically involve **language-heavy, repeatable work with a clear quality bar and available context**: summarizing, drafting, comparing documents, extracting structured information, brainstorming, and turning raw notes into polished deliverables. Weak or inappropriate use cases involve steps where the organization needs a **guaranteed-correct, authoritative answer with no human check** (e.g., final legal sign-off, unreviewed compliance filings), where required data cannot be shared under policy, or where the real bottleneck is not language work at all (e.g., a physical logistics delay).

**Scenario.** An operations lead wants Claude to "handle vendor contracts." Analysis reveals three distinct steps: (a) extracting key terms from incoming contracts into a comparison table, (b) drafting a plain-language summary for the business owner, and (c) approving the contract. Steps (a) and (b) are excellent Claude use cases with human review; step (c) must remain a human decision. The exam frequently tests exactly this decomposition: the right answer keeps Claude on the language work and keeps accountability with people.

### Grounding the analysis: Projects as a requirements workspace

On the Claude platform, **Projects** give you a self-contained workspace with its own chat history and knowledge base. You can upload relevant documents (process docs, stakeholder notes, policy excerpts) to the project knowledge and set **project instructions** so Claude consistently responds from the right perspective — for example, "Answer as a business analyst; always list assumptions separately." This keeps a multi-week requirements effort coherent instead of scattering context across one-off chats. On Team and Enterprise plans, projects can be shared with colleagues with "can use" or "can edit" permissions, so the whole working group analyzes against the same context.

---

## 4.2 Leverage Claude for research, planning, and process optimization

### Matching the research tool to the research need

Official Anthropic guidance distinguishes three capabilities, and the exam expects you to pick the right one for a scenario:

| Need | Best fit | Why |
|---|---|---|
| A quick, current fact ("What did competitor X announce this week?") | **Web search** | Straightforward factual queries answerable with one or two searches |
| Deep reasoning over material you already have, no fresh web data needed | **Extended thinking** | Claude reasons through the problem in more depth before answering |
| A comprehensive, multi-source report ("Compare our three main competitors' pricing and positioning") | **Research** | Claude agentically runs many searches that build on each other and synthesizes findings with citations |

Key verified facts about **Research** (paid plans — Pro, Max, Team, Enterprise):

- Claude operates agentically: it conducts multiple searches that build on each other, decides what to investigate next, and explores different angles of the question systematically.
- Results include **citations** you can check — which matters because the Associate's job (Domain 2 crossover) is to verify claims before they reach stakeholders.
- Web search must be turned on for Research to function.
- Research can also draw on your **connected internal context** — for example Gmail, Google Calendar, and Google Docs when those integrations are connected — combining internal knowledge with the web.
- Research counts against the same usage limits as normal conversations but can consume them faster, because Claude retrieves many sources and writes comprehensive responses. This is a real quality/efficiency/cost trade-off: don't run Research for a question web search answers in one step.
- Extended thinking and Research can be combined when a task needs both careful planning and broad information gathering.

**Scenario.** A marketing manager preparing a product-launch plan uses Research to gather competitive intelligence from the web while pulling the team's own positioning documents through the Google Workspace integration — an officially highlighted pattern. The output is a cited briefing she then verifies and edits, not a finished plan she forwards blindly.

### Planning and process optimization

Beyond research, Claude is effective at the *planning layer* of workflow improvement:

- **Process mapping:** paste a narrative description of how work currently flows ("First the coordinator receives the request by email, then...") and ask Claude to render it as a numbered step list or a diagram, flag handoffs, and identify steps that are pure information transformation.
- **Bottleneck analysis:** ask Claude to classify each step by time cost, error risk, and whether it is language work — producing a shortlist of candidate steps for AI assistance.
- **Option generation:** have Claude propose two or three redesign options with pros, cons, and risks, then pressure-test each ("What could go wrong with option B? Who would object and why?").

The discipline to teach: Claude generates *hypotheses* about a process; the people who run the process **validate** them. An optimization plan built only on Claude's inferences from a document, without checking against operational reality, is a classic exam-style wrong answer.

---

## 4.3 Use Claude to support solution design, development, and iteration

### Draft → review → refine: the iteration loop

Solution development with Claude is iterative by design. The reliable loop is:

1. **Draft** — Claude produces a first version (document, plan, template, tracker, prototype).
2. **Review** — humans (you plus affected stakeholders) evaluate against the requirements from 4.1.
3. **Refine** — feed specific, concrete feedback back to Claude ("The tone is too formal for frontline staff; shorten section 2; add an escalation contact") rather than vague reactions ("make it better").
4. **Repeat** until the output meets the quality bar, then **standardize** the winning prompt/instructions so the result is repeatable.

### Artifacts: the iteration surface

**Artifacts** are Claude's mechanism for substantial, standalone content — documents, tables, diagrams and flowcharts, single-page HTML tools, and interactive components — displayed in a dedicated window beside the chat. Verified capabilities that matter for solution design:

- You can ask Claude to **modify and update** artifact content, and switch between **versions** using the version selector — so iteration rounds are preserved, not overwritten.
- For Markdown documents you can **edit in place**: highlight text, choose "Edit with Claude," and describe the change exactly where you marked it.
- You can **view the underlying code, copy content, or download files** to use outside the conversation.
- Artifacts can be **published and shared**, and you can build **AI-powered artifacts** — small interactive apps whose users authenticate with their own Claude accounts, with usage counting against each user's own subscription limits rather than the creator's.

**Scenario.** A project manager designs a weekly status-report template. Round 1: Claude drafts the template as an artifact. Round 2: two team leads say the risk section is too long — the PM highlights it and requests a tighter format in place. Round 3: the sponsor wants a one-line executive summary on top. The version selector preserves each round; when stakeholders agree, the PM downloads the final version and saves the generating instructions into the team's shared Project so every future report starts from the approved pattern.

### From one-off solution to durable solution

A solution isn't "designed" until it survives without its designer. Associates make solutions durable by:

- Moving the winning prompt into **project instructions** so any team member gets consistent results.
- Curating **project knowledge** (style guides, policy excerpts, examples of approved output) so quality doesn't depend on what one person remembers to paste.
- Writing a short **usage note**: what the solution does, what it must not be used for, and what the human review step is.
- Scheduling a periodic check that the knowledge and instructions are still current (Domain 5 crossover).

### Escalation boundary: when design leaves Associate scope

The CCAO-F exam guide is explicit: designing enterprise-scale AI architectures, building against APIs, and designing agentic systems belong to the **Claude Architect** and **Claude Developer** credentials. Practical signals that a solution has outgrown Associate scope:

- The solution must run **automatically without a human in the chat** (scheduled pipelines, API-driven automation at volume).
- It requires **custom system integration** beyond configuring available connectors — e.g., building a custom MCP server or writing integration code.
- It needs **enterprise architecture decisions**: security reviews of new infrastructure, multi-system data flows, or formal SLAs.
- Stakeholders want **guarantees** (uptime, throughput, contractual accuracy commitments) that a chat-based workflow cannot provide.

The right Associate move in these scenarios is to document the validated use case, requirements, and prototype learnings — then **hand off** to technical colleagues or certified Architects/Developers. On the exam, "escalate with a well-documented use case" routinely beats both "attempt the technical build yourself" and "abandon the project."

---

## 4.4 Integrate Claude into existing workflows to augment or redesign them

### Augment vs. redesign: the central decision

**Augmentation** keeps the existing workflow shape and inserts Claude into specific steps — same people, same handoffs, faster or better individual steps. **Redesign** rethinks the workflow around what Claude makes possible — steps merge, disappear, or change owners.

A practical decision framework:

| Factor | Favors augmentation | Favors redesign |
|---|---|---|
| Process health | Process is sound; steps are just slow | Process has structural problems (redundant handoffs, chronic rework) |
| Risk tolerance | Low — regulated, customer-facing, or fragile | Higher — internal, recoverable errors |
| Change capacity | Team is stretched; low appetite for retraining | Leadership sponsorship and time to manage change |
| Evidence base | Little data yet on where Claude helps | Augmentation pilots already proved value in this process |
| Dependency risk | Other teams depend on current outputs/formats | Process is self-contained |

A sound default sequence — and a recurring exam-answer shape — is **augment first, redesign from evidence**: pilot Claude inside one or two steps, measure, learn where value concentrates, then redesign around demonstrated wins rather than assumptions.

**Augmentation scenario.** A communications team keeps its editorial workflow (brief → draft → edit → approve) but adds Claude at two points: converting briefs into structured first drafts, and pre-checking drafts against the style guide stored in project knowledge. Editors and approvers keep their roles; cycle time drops at the drafting step.

**Redesign scenario.** An operations team's monthly report previously involved four people copying figures between documents over five days. After successful pilots, they rebuild the workflow: contributors drop source files into a shared Project, one owner has Claude generate the consolidated draft with a standardized instruction set, and the freed reviewers move to exception-checking and analysis. Steps were eliminated, one role changed from "assembler" to "verifier" — that's redesign.

### Connecting Claude to where work already lives

Integration is easier when Claude can reach existing systems instead of relying on manual copy-paste:

- **Connectors** let Claude access your apps and services, retrieve data, and take actions within them (for example, searching files in Google Drive or creating issues in a work-tracking tool). Critically, **Claude inherits each person's permissions from the connected service** — if you can't access a file in the source system, Claude can't reach it for you either. This is a governance point the exam can pair with Domain 6.
- On **Team and Enterprise plans**, an organization Owner must enable a connector before members can use it, and each person still authenticates individually. Owners can also **restrict actions** org-wide — e.g., allow Claude to read email but not send messages, or read Drive files but not edit them — a key control when integrating Claude into workflows conservatively.
- The **Google Workspace integration** (Gmail, Google Calendar, Google Docs) lets Claude pull meeting notes, action items from email threads, and document context without manual uploads — officially highlighted patterns include sales teams building client-meeting briefings from correspondence history and calendar context, and marketing teams combining internal strategy docs with web research for launch plans.

Design principle: **start integrations read-only where possible, add write actions only after trust is established.** The action-restriction capability exists precisely to support this staged rollout.

### Change management basics (general guidance)

Workflow integration succeeds or fails on people, not features. Practical, non-product guidance an Associate should apply:

- **Pilot small** with a willing team and a defined success measure before scaling.
- **Keep humans accountable**: every integrated workflow should name who reviews Claude-assisted output and who owns the outcome.
- **Document the new workflow** — where Claude is used, with what instructions, and what the review step is — so the process survives staff turnover.
- **Measure honestly**: compare time, quality, and error rates before and after; report what didn't improve as well as what did.

---

## 4.5 Communicate Claude's value and limitations to stakeholders

### Why balanced communication is the tested skill

Overselling Claude creates failed expectations and adoption backlash; underselling it leaves value uncaptured. The exam positions the Associate as the honest translator between the technology and the business. Answers that promise perfection, hide limitations, or dismiss stakeholder concerns are wrong answers.

### The Value–Limits–Controls (VLC) framing

A simple three-part structure for any stakeholder conversation, memo, or demo:

1. **Value** — Speak in business outcomes, not features. Not "Claude has a Research feature," but "First-draft competitive briefs that took a day now take under an hour, with citations we then verify." Anchor claims in your own pilot measurements wherever possible.
2. **Limits** — State them plainly and specifically:
   - Claude can produce **confident-sounding errors (hallucinations)**; outputs that carry factual or legal weight require human verification.
   - Claude works from **the context it is given**; incomplete or stale knowledge sources produce incomplete answers.
   - **Data policies constrain inputs** — some information may not be shareable with the tool under organizational policy.
   - Quality is **variable and prompt-dependent**; the workflow includes review for a reason.
   - Usage operates within **plan limits**, and heavy features like Research consume limits faster — so the design accounts for capacity, not unlimited use.
3. **Controls** — Show the safeguards that make the limits manageable: named human reviewers, verification steps for cited facts, read-only connector permissions where appropriate, documented instructions, and an escalation path.

This framing works because it answers the three questions every sponsor actually has: *What do we gain? What could go wrong? What are you doing about it?*

### Tailoring the message by audience

- **Executives:** outcomes, measured pilot results, risk posture, and what decision you need from them. One page.
- **The team doing the work:** what changes in their day, what doesn't (their judgment still decides), and where to raise problems. Demo with their real work, not canned examples.
- **Risk/compliance/IT partners:** data flows, permissions model (connectors inherit user permissions; admins control enablement and can restrict write actions), review checkpoints, and alignment with organizational AI policy.

### Communicating the escalation boundary

Part of honest communication is being clear about **what you are not offering**. When a stakeholder asks for fully automated, system-integrated, or API-driven capability, the credible Associate answer is: "That's beyond what we should build with chat-based workflows. I'll document the requirements and validated use case, and we'll bring in engineering / a Claude Architect or Developer for that scope." Saying this early builds trust; discovering it late destroys it.

---

## Trainer notes

### Teaching tips

- **Teach with a real process, not slides.** Have each participant bring one workflow from their actual job. Every concept in this module (suitability analysis, augment vs. redesign, VLC communication) should be applied to their own process during the session — retention is dramatically higher.
- **Drill the decomposition reflex.** Learners default to evaluating whole workflows ("Can Claude do procurement?"). Force step-level analysis every time: list the steps, classify each, decide per step. Most exam scenarios in this domain reward step-level thinking.
- **Rehearse the honest pitch out loud.** The VLC framing only becomes natural when spoken. Pair learners up: one plays a skeptical CFO or a nervous team lead, the other delivers value, limits, and controls in two minutes.
- **Connect domains explicitly.** Domain 4 scenarios frequently embed Domain 2 (verify before sharing), Domain 3 (pick the right feature/model for cost and speed), and Domain 6 (data sensitivity, permissions). Point out these seams whenever they appear.
- **Keep the escalation boundary visible.** Post the Associate/Architect/Developer scope distinction on the wall for the whole session; ask "whose job is this?" about every proposed solution.

### Discussion prompts

1. "Think of a workflow you own. Which single step would you give to Claude first, and why that one? What would you refuse to hand over, and why?"
2. "Your pilot cut drafting time by 60%, but reviewers now spend 20% more time checking outputs. Is the pilot a success? How would you present this to a sponsor without spinning it?"
3. "A director says: 'If it still needs human review, what's the point?' Construct a response using the Value–Limits–Controls framing."
4. "When has 'automate the existing process' been the wrong goal in your experience — where the process itself needed rethinking first? How does that map to the augment-vs-redesign decision?"
5. "A stakeholder asks you to build something that should run automatically overnight across three systems. Script the exact handoff conversation: what do you document, and to whom do you escalate?"

### Common misconceptions

- **"Integration means automation."** Associate-scope integration keeps a human in the loop; unattended automation and API pipelines are Architect/Developer territory. Exam answers that remove human review from consequential steps are almost always wrong.
- **"Redesign is always better than augmentation."** Redesign is higher-risk and needs organizational readiness and evidence. "Augment first, redesign from evidence" is the safer default and the more frequently correct exam pattern.
- **"More features = better solution."** Running Research (or the most capable settings) on everything wastes usage limits and time. Matching web search / extended thinking / Research to the actual need is the tested behavior.
- **"Research output is pre-verified because it has citations."** Citations make verification *easier*; they don't replace it. The human still checks claims that matter before they reach stakeholders.
- **"Connecting a tool gives Claude broad access to it."** Connectors inherit the individual user's existing permissions in the source system, and org admins on Team/Enterprise plans control enablement and can restrict actions (e.g., read-only).
- **"Mentioning limitations weakens the business case."** In practice, stating limits with matching controls is what makes sponsors trust the value claims.

### Hands-on classroom exercise: "Redesign sprint" (60–75 minutes)

1. **Form teams of 3–4.** Each team selects one real workflow a member actually performs (e.g., weekly reporting, candidate screening summaries, event planning, customer-inquiry triage).
2. **Map (15 min):** List the workflow's steps on cards or a whiteboard. For each step, tag: language work vs. judgment call; data sensitivity; time cost.
3. **Design (20 min):** Produce two proposals — an *augmentation* (Claude inserted into 1–2 steps, everything else unchanged) and a *redesign* (workflow rebuilt around Claude, e.g., using a shared Project with instructions and knowledge). For each: which Claude features are used (Projects, Artifacts, Research, connectors), where the human review sits, and one metric to judge success.
4. **Pitch (15 min):** Each team gives a three-minute stakeholder pitch for its preferred option using Value–Limits–Controls. The audience plays skeptical stakeholders and must ask at least one limitations question and one data-sensitivity question.
5. **Debrief (10 min):** Which teams chose augmentation vs. redesign, and did their reasoning match the decision factors? Did any proposal cross the escalation boundary into Architect/Developer scope without noticing? (If Claude access is available in class, have teams actually build the pilot prompt or project instructions for their chosen step.)

---

## Practice questions

*The following items are original practice questions written in the style of the exam guide's samples. They are not actual exam items. Unless an item states otherwise, select ONE response.*

**Q1.** An operations manager asks an Associate to "get AI into our invoice-handling process." What is the most appropriate first step?

A. Configure a Project immediately and upload all invoice records so Claude can begin processing.
B. Map the process into individual steps and identify which involve routine language or information tasks versus human judgment.
C. Tell the manager invoice handling is a financial process and therefore unsuitable for Claude.
D. Ask engineering to build an automated invoice pipeline against the API.

**Q2.** A project manager has stakeholder interview notes that are vague and partly contradictory. Which use of Claude best supports requirements analysis at this stage?

A. Ask Claude to write the final requirements document so the project can start on schedule.
B. Ask Claude to restate the problem, extract explicit and implicit requirements, and list ambiguities as questions to take back to stakeholders.
C. Ask Claude to decide which stakeholder's version of the requirements is correct.
D. Skip requirements analysis; iterate on the solution until stakeholders stop complaining.

**Q3.** An Associate needs a comprehensive competitive analysis synthesizing many web sources plus the company's internal strategy documents into a cited report. Which approach best fits the task?

A. Web search, since the question involves current information.
B. Extended thinking alone, so Claude can reason deeply without outside distraction.
C. The Research capability, with the relevant workspace integration connected, so Claude can agentically search across the web and internal context and produce a cited report.
D. A plain chat with no features enabled, to conserve usage limits.

**Q4.** After Claude's Research feature produces a well-cited market report, what should the Associate do before including its findings in a board presentation?

A. Present it as-is; the citations demonstrate the content has been verified.
B. Ask Claude whether the report is accurate and proceed if it says yes.
C. Spot-check key claims against the cited sources and verify the figures that carry decision weight.
D. Remove the citations so the deck looks cleaner.

**Q5.** A communications team's editorial process works well but drafting is slow. The team is stretched thin, and other departments depend on the current output formats. Leadership wants improvement this quarter. Which approach is most appropriate?

A. Redesign the entire workflow around Claude immediately to maximize impact.
B. Augment the existing workflow by adding Claude at the drafting step, keep review and approval unchanged, and measure results before considering broader redesign.
C. Decline to change anything until a full enterprise AI architecture is in place.
D. Replace the editors with Claude-generated output to free capacity fastest.

**Q6.** An Associate is designing a report template with Claude and expects several rounds of stakeholder feedback. Which practice best supports this iteration? 

A. Start a brand-new conversation for every feedback round so old versions can't cause confusion.
B. Give feedback like "make it better overall" so Claude has creative freedom.
C. Work in an artifact, give specific concrete change requests each round, and use versioning to preserve and compare iterations.
D. Collect all feedback for six weeks and apply it in a single final rewrite.

**Q7.** A sponsor asks an Associate to pitch a Claude-assisted client-briefing workflow to the leadership team. Which pitch best reflects appropriate stakeholder communication?

A. "Claude eliminates errors and will fully automate briefings, so no staff review will be needed."
B. "Briefing prep time dropped from four hours to one in our pilot. Outputs can contain errors, so a named reviewer verifies facts before anything is sent, and the email connector is limited to read-only access."
C. "The AI details are too technical to explain; leadership should simply trust the results."
D. "There are significant risks, so we recommend not discussing limitations to avoid alarming anyone."

**Q8. (Multiple response — select TWO.)** Which of the following requests signal that work has moved beyond Associate scope and should be escalated toward Claude Architect / Developer expertise? (Choose 2.)

A. A team wants a shared Project configured with instructions and a curated knowledge base for consistent report drafting.
B. A director wants an unattended, API-driven pipeline that processes thousands of documents nightly across three internal systems.
C. A colleague wants help iterating a slide-outline prompt to improve draft quality.
D. IT asks for a custom-built integration server to connect Claude to a proprietary internal platform not covered by available connectors.
E. A manager wants Claude's Research feature used to prepare a cited market overview.

**Q9.** A Team-plan organization is integrating Claude with its email and file-storage systems for a pilot, and the risk team is worried about unintended changes to source data. Which verified platform capability most directly addresses this concern?

A. Instructing Claude in the prompt to "please be careful" with connected systems.
B. Having org admins enable the connectors and restrict actions so Claude can read from the services but not write changes back, while each user's access still inherits their own source-system permissions.
C. Sharing one privileged user's connector login across the whole team to simplify auditing.
D. Avoiding connectors entirely and pasting customer data into chats instead.

### Answers

**Q1 — B.** Requirements analysis starts with decomposing the process and classifying steps by suitability; that determines where (and whether) Claude helps. Uploading all records first (A) skips analysis and raises data-sensitivity issues; blanket rejection (C) ignores that sub-steps like summarization may be excellent fits; jumping to an API pipeline (D) is beyond Associate scope and premature before requirements exist.

**Q2 — B.** Claude's value here is structuring messy input and *exposing* ambiguity as questions for humans to resolve. Writing the final document from contradictory notes (A) bakes the contradictions in; asking Claude to adjudicate stakeholder conflicts (C) misassigns human authority; skipping analysis (D) guarantees rework.

**Q3 — C.** Official guidance positions Research for comprehensive, multi-source synthesis with citations, and it can draw on both the web and connected internal context. Web search (A) fits quick factual lookups, not deep synthesis; extended thinking alone (B) adds reasoning depth but no current outside information; a bare chat (D) prioritizes trivial savings over the task's actual requirements.

**Q4 — C.** Citations make verification easier; they are not verification. Findings that carry decision weight get checked against sources by a human before reaching the board. Self-assessment by the model (B) is not a reliable accuracy signal, and removing citations (D) makes the report *less* verifiable.

**Q5 — B.** Every factor given — healthy process, low change capacity, downstream format dependencies, near-term deadline — favors augmentation first, with measurement creating the evidence base for any later redesign. Immediate full redesign (A) mismatches readiness; waiting for enterprise architecture (C) is unnecessary for a human-in-the-loop pilot; removing editorial review (D) removes the accountability the workflow depends on.

**Q6 — C.** Artifacts are designed for exactly this: substantial standalone content you iterate on, with versioning to preserve rounds and in-place editing for precise changes. New conversations each round (A) discard useful context; vague feedback (B) produces vague revisions; batching feedback for weeks (D) forfeits the fast feedback loop that makes iteration with Claude valuable.

**Q7 — B.** It leads with a measured outcome, states the limitation specifically (errors are possible), and names the controls (human reviewer, read-only connector access) — the Value–Limits–Controls pattern. A promises the impossible; C demands blind trust; D hides limitations, which undermines informed decision-making and stakeholder trust.

**Q8 — B and D.** Unattended API-driven pipelines at volume (B) and custom integration builds for systems outside available connectors (D) are agentic/engineering work that the exam guide assigns to Claude Architect and Developer scope. Configuring shared Projects (A), prompt iteration coaching (C), and using Research for a cited overview (E) are core Associate-level activities.

**Q9 — B.** These are verified platform controls: on Team/Enterprise plans admins enable connectors, can restrict actions org-wide (for example, read-only), and connectors always inherit each individual user's permissions from the source system. Prompt-level politeness (A) is not a control; credential sharing (C) breaks user-level permission enforcement and accountability; pasting customer data into chats (D) trades a governed integration for an ungoverned data-handling risk.

---

## Sources

Official Anthropic sources verified for the product claims in this module:

- https://support.claude.com/en/articles/9517075-what-are-projects — Projects: self-contained workspaces, knowledge bases, project instructions, Team/Enterprise sharing and permission levels ("can use" / "can edit").
- https://support.claude.com/en/articles/9487310-what-are-artifacts-and-how-do-i-use-them — Artifacts: standalone content window, edit/iterate, version selector, in-place Markdown editing, download/copy, publishing, AI-powered artifacts and usage attribution.
- https://support.claude.com/en/articles/11088861-using-research-on-claude — Research: agentic multi-search behavior, citations, paid-plan availability, web search prerequisite, internal-context integration, usage-limit behavior.
- https://support.claude.com/en/articles/11095361-when-should-i-use-web-search-extended-thinking-and-research — Choosing among web search, extended thinking, and Research; combining Research with extended thinking.
- https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities — Connectors: permission inheritance from source systems, Team/Enterprise admin enablement, per-user authentication, org-wide action restrictions (e.g., read-only).
- https://www.anthropic.com/news/research (published at claude.com/blog/research) — Research + Google Workspace announcement: Gmail/Calendar/Docs integration, cited business use cases (marketing launch planning, sales meeting briefings).
- CCAO-F Exam Guide v1.0 (provided course reference) — Domain 4 objectives, audience definition, Associate vs. Architect/Developer scope, and sample-item style.
