---
title: "3. Product & Model Selection"
nav_order: 5
---

# Module 3 — Product and Model Selection (Domain 3, 12%)

> **Blueprint objectives covered in this module**
>
> - Select appropriate Claude product features (Projects, research mode, chat, artifacts)
> - Differentiate between Claude model types (Haiku, Sonnet, Opus)
> - Align model selection with task requirements (cost, speed, quality)
> - Understand and manage context limitations and memory considerations (when to restart, summarize, or persist)

---

## Why this domain matters

Domain 3 tests whether you can pick the right tool for the job — not whether you can memorize specs. A certified associate who reaches for the most capable, most expensive model for every routine task wastes cost and time; one who runs a week-long team workstream in a single plain chat loses context, consistency, and shareability. The exam's own sample item for this domain (Sample 2 in the exam guide) is exactly this kind of judgment call: high-volume, straightforward drafting belongs on a faster, lower-cost model. Expect scenario questions that describe a task's volume, complexity, budget, and collaboration needs, then ask which feature and which class of model fit best — and what to do when a long conversation starts to strain its context.

---

## 1. Selecting the right product feature

### 1.1 The core feature set

Claude's interface offers several distinct ways of working. Knowing what each is *for* is the first selection skill the exam tests.

**Plain chat** is the default: a single conversation with Claude. It is the right choice for one-off questions, quick drafting, brainstorming, and any task where you will not need the context again later. Related in-chat capabilities you can toggle include:

- **Web search** — best for straightforward, factual queries answerable with one or two lookups (recent news, a company detail, "what happened yesterday"). You steer the general direction; Claude runs the searches and analyzes results.
- **Extended thinking** — lets Claude spend more time reasoning before it responds, showing its thought process in an expandable section. Best for complex reasoning that does *not* need fresh information from the web: math, debugging, multi-step analysis, planning.

**Projects** are self-contained workspaces with their own chat histories and knowledge bases. You upload relevant documents, text, code, or files to the project's knowledge base, and you can define **project instructions** (e.g., "answer as a compliance analyst, in formal tone") that shape every chat inside the project. Key facts verified against the official help article:

- Projects are available to all users, including free accounts (free users can create a limited number of projects — five, at the time the source article was published).
- On paid plans, project knowledge scales through **Retrieval Augmented Generation (RAG)**: when knowledge approaches context limits, Claude switches to retrieval mode so only relevant content loads into context, expanding effective capacity substantially.
- On Team and Enterprise plans, projects can be **shared** with others in the organization, with "can use" and "can edit" permission levels — making them the natural home for recurring team workflows.

**Research** turns Claude into an agentic investigator: it runs multiple searches that build on each other across the web *and* your connected internal context (e.g., Google Workspace connectors), then synthesizes an in-depth, **cited** report. Verified characteristics:

- Available on paid plans (Pro, Max, Team, Enterprise); requires web search to be turned on.
- Enabled from the tools menu in the chat input area; it runs for a few minutes rather than seconds.
- Officially positioned for "comprehensive information gathering requiring five or more tool calls," versus web search's one-or-two-lookup questions.
- It uses the same usage limits as normal chat but consumes them faster, because it retrieves many sources.

**Artifacts** are how Claude delivers substantial, standalone content in a dedicated window beside the chat — documents, code, single-page websites, SVG images, diagrams, and interactive components. Verified characteristics:

- Claude creates an artifact when content is significant and self-contained (typically more than ~15 lines), likely to be edited/iterated/reused, and something you'll refer back to.
- You can iterate on an artifact, switch between versions, view/copy the underlying content, and download it.
- Artifacts can be published and shared; AI-powered artifacts let others use an app you built with usage counted against *their* subscription, not yours.
- Artifacts require the "code execution and file creation" capability to be enabled in settings.

### 1.2 Decision framework: plain chat vs. Project vs. Research vs. artifact

Note that these are not mutually exclusive — you might run Research *inside* a Project and receive the report *as an artifact*. The exam skill is knowing which one the scenario is really asking about.

| The scenario says... | Best-fit choice | Why |
|---|---|---|
| One-off question, quick draft, no reuse | Plain chat | No setup overhead; context not needed later |
| "Every week," "our team," "consistent tone," "based on our style guide / docs" | **Project** | Persistent knowledge base + instructions give repeatable, consistent results; shareable on Team/Enterprise |
| "Compare vendors/competitors," "in-depth report," "many sources," "with citations" | **Research** | Agentic multi-search with citations; built for synthesis across many sources |
| "What's the latest news on X?" / single fact to check | Web search in chat | One or two lookups; Research would be overkill |
| "Work through this hard problem carefully" (no fresh data needed) | Extended thinking | Deeper reasoning, no retrieval required |
| Deliverable to edit, version, reuse, share, or publish (doc, app, diagram, code file) | **Artifact** | Standalone content in its own window with versions, export, and sharing |

Quick discriminators to teach:

- **Recurrence + shared context → Project.** The moment a scenario mentions re-uploading the same files or repeating the same background every chat, a Project with knowledge and instructions is the answer.
- **Breadth of sources + citations → Research.** "Thorough," "synthesize," "report" are Research cues; "quick fact" is a web-search cue.
- **Depth of reasoning → extended thinking.** No new information required, just harder thinking.
- **A thing you keep → artifact.** If the output is a deliverable rather than an answer, it belongs in an artifact.

### 1.3 Worked examples

Walk learners through the reasoning aloud — the exam rewards the *why*, not just the pick.

**Scenario A.** *"A project manager compiles a weekly status digest from the same five source documents and wants a consistent format every time."*
Reasoning: recurring task + standing source documents + consistent format = **Project** (documents in project knowledge, format rules in project instructions). Each week's digest is substantial, reusable content = deliver as an **artifact**. Neither Research nor web search is implicated — no external information is needed.

**Scenario B.** *"An associate needs to know whether a vendor announced a price change this morning."*
Reasoning: single, current, factual question = **web search** in plain chat. Choosing Research here isn't wrong so much as wasteful — it spends minutes and heavier usage on a one-lookup answer. Feature selection, like model selection, is a right-sizing exercise.

**Scenario C.** *"A strategy team wants a thorough, citation-backed briefing on how three competitors position their products, drawing on the web and the team's own meeting notes in connected Google Docs."*
Reasoning: many sources + synthesis + citations + internal connectors = **Research**. If the briefing will be edited and circulated afterward, have it delivered as an **artifact**; if this kind of briefing recurs monthly, house the work in a **Project**.

---

## 2. Differentiating Claude model types (Haiku, Sonnet, Opus)

### 2.1 The three families

Anthropic offers Claude in model families that trade off capability, speed, and cost. Specific version numbers change over time, but the family positioning is stable and is what the exam objective names:

| Family | Official positioning (per Anthropic's model documentation) | Typical strengths |
|---|---|---|
| **Haiku** | The fastest model family, near-frontier intelligence at the most economical price point | Real-time and high-volume work, quick drafting, classification, cost-sensitive tasks |
| **Sonnet** | The best combination of speed and intelligence — frontier performance for everyday work | General business tasks, content creation, data analysis, coding — the balanced default |
| **Opus** | The most capable family, for complex reasoning and demanding enterprise/agentic work | Deep analysis, complex multi-step problems, high-stakes work where quality outweighs cost |

Relative trade-offs as officially characterized: **Haiku is fastest and lowest-cost; Opus is most capable with higher cost and latency; Sonnet sits between as the balance point.**

> **Important — lineups evolve.** Anthropic ships new model versions regularly, and the current lineup on the docs may include additional models beyond these three families. Do not memorize version numbers, context-window figures, or prices for the exam or for real work; instead, learn the *family trade-offs* above and always check the current model documentation (docs.claude.com models overview) and the in-product model menu before advising anyone on a specific model.

### 2.2 Where you choose the model — and the adjacent settings

In the Claude apps, the **model menu next to the send button** controls which model you're chatting with. Points verified against the official help article:

- You can change the model at any point in a conversation; the change applies from Claude's next response.
- Some models expose an **effort** setting: higher effort produces more thorough responses but takes longer and uses more of your usage limits; lower effort stretches usage further on routine tasks.
- **Extended thinking** is a separate toggle from effort; for everyday tasks the defaults work well, and you raise effort and/or enable thinking for math, complex planning, detailed document analysis, and multi-step technical problems.
- On Enterprise plans, administrators can restrict which models and effort levels are available to a role — so a "missing" model may be a policy, not a bug.

Exam relevance: an item may test that model choice and effort/thinking settings are *levers you adjust per task*, not fixed properties of your account.

---

## 3. Aligning model selection with task requirements (cost, speed, quality)

### 3.1 The three criteria

Anthropic's official "choosing a model" guidance frames the decision around three questions:

1. **Capabilities/quality** — how hard is the task? Does it need nuanced reasoning or is it straightforward?
2. **Speed** — does the user or workflow need answers in real time, or can it wait for deeper processing?
3. **Cost** — what's the budget, and how many times will this task run? (Volume multiplies every cost difference.)

### 3.2 Model-selection decision table by task type

| Task profile | Signals in the scenario | Model family to reach for |
|---|---|---|
| High-volume, straightforward, speed/cost-sensitive | "hundreds of replies," "real time," "keep costs down," "simple classification/drafts" | **Haiku** |
| Everyday knowledge work | "summarize this report," "draft a proposal," "analyze this spreadsheet," mixed difficulty | **Sonnet** |
| Complex, high-stakes, reasoning-heavy | "multi-step analysis," "accuracy outweighs cost," "complex planning," "hardest problems" | **Opus** |
| Complex but budget-constrained | "important but we're cost-sensitive" | Start balanced (Sonnet), raise effort/thinking, escalate to Opus only if quality falls short |

### 3.3 Two official starting strategies

Anthropic's documentation describes two legitimate approaches — exam items may present either as correct depending on the scenario:

- **Start fast and cheap, upgrade if needed.** Begin with the fastest, most cost-effective model; test; move up only if there's a real capability gap. Best for prototyping, tight latency, cost-sensitive and high-volume work.
- **Start most capable, optimize down.** Begin with the most capable model to establish a quality ceiling; then reduce effort or step down model families once the workflow is proven. Best when accuracy outweighs cost or the task is genuinely complex.

Either way, the officially recommended practice is to **test with your actual tasks and compare** — accuracy, quality, edge cases — and weigh performance against cost, rather than assuming.

### 3.4 The anti-patterns the exam punishes

- **"Always use the biggest model."** Wastes cost and latency budget on tasks a faster model handles fine (this is exactly the wrong answer in the exam guide's Sample 2).
- **"Always use the cheapest model."** False economy when errors on a complex, high-stakes task cost more than the model savings.
- **"Cost control means disabling features / switching platforms."** Distractor logic: the fix for a cost/speed/quality mismatch is realigning model (or effort) to task, not abandoning capability.

---

## 4. Context limitations and memory: restart, summarize, or persist

### 4.1 What the context window is

The **context window** is the amount of conversation-plus-attachments a model can consider at once. It is large (hundreds of pages of text on current models) but finite, and its size **varies by model and plan** — check current documentation rather than memorizing figures. Everything in the active conversation competes for that space: your messages, Claude's replies, uploaded files, project knowledge loaded into context, and active tools/connectors (which are officially noted as token-intensive).

### 4.2 Signs a conversation's context is degrading

Teach candidates to recognize these symptoms in scenarios:

- Claude forgets or contradicts instructions or facts established earlier in the same chat.
- Claude asks for information that was already provided many messages ago.
- Responses drift off the agreed format, tone, or constraints.
- The conversation has accumulated many large files and long tangents unrelated to the current ask.
- You hit length-limit errors or notice sluggish, meandering answers late in a very long session.

### 4.3 What the platform does automatically

On paid plans with code execution enabled, Claude performs **automatic context management**: when a conversation approaches the context limit, it summarizes earlier messages to make room, preserving the full chat history for reference, so most conversations can continue indefinitely. You may notice Claude "organizing its thoughts" — that is this mechanism at work. It has edge cases (e.g., a very large first message), so manual judgment still matters.

### 4.4 The restart / summarize / persist decision

| Situation | Action | How |
|---|---|---|
| Conversation is long, cluttered, and the *task has changed* | **Restart** | Start a fresh chat; carry over only what the new task needs |
| Conversation is long but the *thread of work must continue* | **Summarize** | Ask Claude to produce a concise summary of decisions, constraints, and open items; paste it into a new chat as the starting brief |
| The same background/context will be needed *across many future chats* | **Persist** | Move it into durable storage: a Project's knowledge base and instructions (for documents, guidelines, role), or an artifact (for a deliverable you'll keep iterating) |
| Claude should recall *who you are and how you work* across chats | **Persist (memory)** | Claude's memory feature builds a summary from your chat history; each project also has its own separate memory space |

Rules of thumb worth drilling:

- **Restart is not losing work** — the durable outputs (summaries, artifacts, project knowledge) carry forward; the disposable back-and-forth does not need to.
- **Summarize at natural milestones**, not just at failure: end of a phase, end of a meeting's worth of decisions.
- **Persist deliberately.** Recurring context belongs in a Project (knowledge + concise instructions), not re-pasted into every chat. Official guidance: keep project instructions concise, and remember Projects' RAG loads only relevant knowledge into context, which conserves the window.

### 4.5 Memory and past-chat features (as officially described)

- **Search past chats** (paid plans): you can prompt Claude to find and reference previous conversations ("What did we discuss about X?"); searches within a project are limited to that project.
- **Memory**: Claude builds a periodically updated memory summary from your chat history; **each project has its own separate memory space** so contexts don't bleed together. You can view and edit what Claude remembers, tell it what to remember, and pause or reset memory in settings.
- **Incognito chats** are excluded from memory and past-chat search — relevant when a scenario involves a sensitive one-off conversation that shouldn't influence future context.
- Availability and controls vary by plan (e.g., organization-level memory controls on Enterprise), so scenarios about admin-disabled features are plausible.

### 4.6 Worked example: the milestone summary

A practical pattern to demonstrate live in class. At the end of a long planning session, before context strain sets in, prompt:

> "Summarize this conversation for a hand-off: (1) decisions made and their rationale, (2) constraints and requirements we agreed on, (3) open questions, (4) next steps. Keep it under one page."

Then open a fresh chat (or a chat inside the relevant Project), paste the summary as the opening brief, and continue. Learners should notice that the new chat is *more* reliable than the old one — the signal survived, the noise did not. If the same brief will matter for weeks, that is the cue to move it from a pasted summary into the Project's knowledge or instructions (persist), rather than repeating the summarize step forever.

---

## Domain cram card (quick review)

| Exam cue | Answer direction |
|---|---|
| Recurring task, shared docs, consistent tone | Project (knowledge + instructions) |
| Multi-source, in-depth, cited report | Research (paid plans; web search must be on) |
| One quick, current fact | Web search in chat |
| Hard reasoning, no fresh data needed | Extended thinking / higher effort |
| Substantial reusable deliverable | Artifact |
| High-volume, simple, speed/cost-sensitive | Haiku-class (fastest, most economical) |
| Everyday balanced work | Sonnet-class (speed + intelligence balance) |
| Complex, high-stakes, accuracy over cost | Opus-class (most capable) |
| Unsure which model | Test against real tasks; upgrade or downgrade on evidence |
| Chat forgetting earlier instructions | Context degradation: summarize, then restart |
| Same background needed across many chats | Persist: Project knowledge/instructions, artifacts, memory |
| Sensitive one-off that must leave no trace in memory | Incognito chat |

And the standing caveat: model versions, context sizes, prices, and plan entitlements evolve — reason from family trade-offs and verify specifics against current official documentation.

---

## 5. Trainer notes

### Teaching tips

- **Lead with the exam guide's Sample 2.** It anchors the whole domain: the tested skill is matching resources to requirements, not product trivia. Have learners articulate *why* each distractor fails (over-provisioning, feature-disabling, platform-switching).
- **Teach cues, not catalogs.** Drill the scenario keywords: "recurring + shared docs" → Project; "many sources + citations" → Research; "single fact" → web search; "deliverable" → artifact; "high volume + speed/cost" → Haiku-class; "balanced default" → Sonnet-class; "hardest, highest-stakes" → Opus-class.
- **Insist on the evolution disclaimer.** Model versions, context sizes, and plan entitlements change. Train learners to reason from family trade-offs and to check the current official docs — this is both exam-safe and professionally correct.
- **Make the context section experiential.** Symptoms of context degradation are easier to recognize after learners have deliberately overloaded a chat than after a lecture about tokens.
- Common time split for a 60–75 minute session: 15 min features, 15 min models/alignment, 15 min context/memory, 20 min exercise, 10 min practice questions and debrief.

### Discussion prompts (pick 3+)

1. Your team re-pastes the brand style guide into every chat. What are the costs of that habit, and what exactly would you move into a Project's knowledge versus its instructions?
2. When would "start with the most capable model and optimize down" beat "start cheap and upgrade" — and what evidence would you collect before stepping down a model family?
3. A colleague says, "Never restart a chat — you lose everything." What actually persists across a restart in a well-run workflow (Projects, artifacts, summaries, memory), and what genuinely is lost?
4. Research and web search both reach the internet. Give two scenarios that look similar on the surface but split cleanly between the two features, and name the deciding signal.
5. Where is the line between what belongs in Claude's memory (who you are, how you work) versus a Project's knowledge (what the work is about)?

### Common misconceptions to correct

- **"Opus is always the best choice because it's the most capable."** Selection means matching, not maximizing; high-volume simple tasks are officially a fastest-family use case.
- **"Projects are just chat folders."** The differentiators are the knowledge base (with RAG scaling on paid plans), project instructions, separate project memory, and sharing — not grouping.
- **"Research is web search with a different name."** Web search = one or two lookups; Research = agentic multi-search synthesis with citations over minutes, including connected internal sources.
- **"Artifacts are only for code."** Documents, diagrams, SVGs, single-page sites, and interactive components are all official artifact types.
- **"A long chat never degrades because context management is automatic."** Automatic summarization helps, but it has edge cases, and judgment about restarting/summarizing/persisting remains the associate's job.
- **"Memory and context window are the same thing."** The context window is what the model sees *in this conversation*; memory is a separate feature that carries summarized understanding *across* conversations.

### Hands-on classroom exercise: "Pick the feature + model" scenario cards

Prepare cards (or a slide) with scenarios like the following. Teams get 60 seconds per card to commit to (a) product feature(s), (b) model family, (c) any context/memory action — then defend the choice in one sentence.

1. Draft 300 short, friendly responses to routine customer reviews before lunch. *(Chat, Haiku-class; no persistence needed.)*
2. Produce a cited competitive-landscape report on three rivals for the exec team. *(Research, balanced-or-capable model; deliver as artifact if it will be edited.)*
3. Weekly newsletter that must always follow the style guide and past issues. *(Project with knowledge + instructions; Sonnet-class.)*
4. One-off: "What changed in the new EU packaging rules announced this week?" *(Web search in plain chat.)*
5. Design a five-year scenario model for a market entry decision the board will act on. *(Opus-class, extended thinking/higher effort; artifact for the deliverable.)*
6. A 200-message chat about Project A is now being used to plan unrelated Project B, and Claude keeps mixing up requirements. *(Restart; summarize A's decisions first; persist recurring context into separate Projects.)*
7. Build a small interactive ROI calculator the sales team can reuse. *(Artifact — interactive component; publish/share per plan.)*
8. Sensitive one-time HR question that must not influence future conversations. *(Incognito chat.)*

Debrief by asking which cards had *two* defensible answers and what extra fact would settle each.

---

## 6. Practice questions

> These are **original practice items written in the style of the exam**. They are not real exam questions and are not drawn from any live item bank.

**Q1.** An operations associate must triage 500 short internal support tickets per day into four categories. Speed and cost matter more than nuanced reasoning. Which approach best fits? *(Select ONE.)*

- A. Use the most capable model family with maximum effort for every ticket.
- B. Use the fastest, most cost-efficient model family suited to high-volume, straightforward tasks.
- C. Turn off all product features to conserve usage.
- D. Batch the tickets into a single mega-prompt for the most capable model once per week.

**Q2.** A marketing team writes a weekly newsletter that must consistently follow the company style guide and reference past issues. Team members currently paste the style guide into a new chat every week. What is the best improvement? *(Select ONE.)*

- A. Ask Claude to memorize the style guide by repeating it in three consecutive chats.
- B. Create a Project, upload the style guide and past issues to its knowledge base, and set project instructions for tone and format.
- C. Use research mode each week so Claude can find the style guide on the web.
- D. Keep one never-ending chat open permanently so context is never lost.

**Q3.** An analyst needs an in-depth comparison of four competitors' pricing, positioning, and recent announcements, synthesized from many web sources with citations she can verify. Which feature is designed for this? *(Select ONE.)*

- A. Web search, because it retrieves live information with a quick lookup.
- B. Extended thinking, because the comparison requires careful reasoning.
- C. Research, because it agentically runs multiple searches and produces a cited, synthesized report.
- D. An artifact, because reports should be displayed in a dedicated window.

**Q4.** Claude has produced a 40-line interactive budget calculator that the finance team wants to keep refining and eventually share. How should this content be handled? *(Select ONE.)*

- A. Keep it inline in the chat and re-generate it whenever someone needs it.
- B. As an artifact, so it exists as standalone content that can be iterated, versioned, and shared.
- C. As a project instruction, so every chat in the project can run it.
- D. As a memory entry, so Claude recalls the calculator in future chats.

**Q5.** Which TWO factors most justify choosing a model from the most capable (Opus-class) family instead of a balanced or fast model? *(Select TWO.)*

- A. The task involves complex, multi-step reasoning where accuracy outweighs cost.
- B. The task is high-volume and highly repetitive.
- C. The output is high-stakes, and errors would be costly to the business.
- D. The team wants responses as fast as possible at the lowest price.
- E. The task is a simple reformatting job with strict latency requirements.

**Q6.** Midway through a long working session, Claude begins contradicting formatting rules agreed at the start and re-asks for a file that was uploaded earlier. The team must continue the same workstream this afternoon. What is the most effective next step? *(Select ONE.)*

- A. Continue in the same chat and repeat every instruction in full with each new message.
- B. Ask Claude to summarize the decisions, constraints, and open items, then start a fresh chat seeded with that summary (and persist recurring materials in a Project).
- C. Switch to a more capable model in the same chat; a stronger model has a memory that never degrades.
- D. Delete the earlier messages one by one until Claude behaves.

**Q7.** A consultant is choosing a model for a new client workflow and is unsure whether a fast, economical model will be good enough. According to Anthropic's official model-selection guidance, what is the most appropriate approach? *(Select ONE.)*

- A. Always deploy the most capable model; quality can never be too high.
- B. Choose based on which model has the newest version number.
- C. Test the candidate models against the actual tasks, compare quality and cost, and upgrade or downgrade based on the evidence.
- D. Choose the cheapest model and commit to it regardless of results, since cost is the primary constraint.

**Q8.** An associate wants Claude to reliably know her role, communication preferences, and ongoing project context across future conversations — without re-explaining each time. Which combination best achieves this? *(Select ONE.)*

- A. Rely on very long single conversations so nothing is ever forgotten.
- B. Use Claude's memory for personal/working context, and Projects (knowledge + instructions) for each workstream's documents and standing guidance.
- C. Use incognito chats so conversations stay consistent.
- D. Enable research mode, which stores everything Claude learns about the user.

### Answers

**Q1 — B.** High-volume, straightforward, speed/cost-sensitive work is the officially characterized fit for the fastest, most economical model family. A over-provisions cost and latency; C confuses cost control with capability removal; D adds delay and doesn't address the model-to-task mismatch.

**Q2 — B.** Projects exist precisely for recurring work with standing context: a knowledge base for the style guide and past issues, plus project instructions for tone. A is not how memory or context works; C misuses Research (the guide is internal, not on the web); D invites context degradation instead of persisting context properly.

**Q3 — C.** Research is officially positioned for comprehensive gathering across many sources, run agentically, with citations. A fits one-or-two-lookup questions; B adds reasoning but no multi-source retrieval; D is an output format, not an information-gathering capability (though the finished report could be delivered as an artifact).

**Q4 — B.** Substantial, self-contained, reusable content is exactly the artifact use case, with iteration, version switching, export, and sharing. A discards the ability to iterate on a stable deliverable; C misunderstands project instructions (guidance for Claude, not an app container); D misunderstands memory (it stores context about you and your work, not interactive deliverables).

**Q5 — A and C.** The most capable family is justified when complexity and stakes demand top quality — accuracy outweighing cost, and costly-if-wrong outputs. B, D, and E are the officially characterized profile of the fastest, most economical family.

**Q6 — B.** The symptoms are context degradation with a need for continuity, so summarize-then-restart is the right pattern, moving recurring materials into persistent storage (a Project). A worsens the context load; C is false — every model has a finite context window; D is unreliable and destroys potentially needed history.

**Q7 — C.** Official guidance says to establish criteria (capabilities, speed, cost), test with your actual prompts and data, and upgrade or downgrade based on measured results — either starting fast-and-cheap or starting most-capable, then optimizing. A and D skip evaluation in opposite directions; B is irrelevant to fit.

**Q8 — B.** Memory carries synthesized personal and working context across chats, and each Project keeps its own knowledge, instructions, and separate memory space for a workstream. A relies on a finite context window; C does the opposite (incognito chats are excluded from memory); D misstates what research mode is for.

---

## 7. Sources

Official Anthropic sources verified during authoring (July 2026). Model lineups, plan entitlements, and limits change over time — always check the current pages.

- What are projects? — Claude Help Center: https://support.claude.com/en/articles/9517075-what-are-projects
- Use research on Claude — Claude Help Center: https://support.claude.com/en/articles/11088861-use-research-on-claude
- When should I use web search, extended thinking, and research? — Claude Help Center: https://support.claude.com/en/articles/11095361-when-should-i-use-web-search-extended-thinking-and-research
- What are artifacts and how do I use them? — Claude Help Center: https://support.claude.com/en/articles/9487310-what-are-artifacts-and-how-do-i-use-them
- Change the model, effort, and thinking settings — Claude Help Center: https://support.claude.com/en/articles/8664678-change-the-model-effort-and-thinking-settings
- How large is the context window on paid Claude plans? — Claude Help Center: https://support.claude.com/en/articles/8606394-how-large-is-the-context-window-on-paid-claude-plans
- Use Claude's chat search and memory to build on previous context — Claude Help Center: https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context
- Models overview — Claude Docs: https://docs.claude.com/en/docs/about-claude/models/overview
- Choosing the right model — Claude Docs: https://platform.claude.com/docs/en/about-claude/models/choosing-a-model
- CCAO-F Exam Guide (Domain 3 objectives and Sample 2), provided course reference file.
