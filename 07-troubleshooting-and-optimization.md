---
title: "7. Troubleshooting & Optimization"
nav_order: 9
---

# Module 7 — Troubleshooting and Optimization (Domain 7, 10%)

> **Blueprint objectives covered in this module**
>
> 1. Identify, diagnose, and resolve issues with underperforming prompts or poor outputs
> 2. Adjust approach based on feedback and results
> 3. Optimize workflows for efficiency and effectiveness
>
> Domain weight: **10%** of the CCAO-F exam (approximately 6 of 60 items).

---

## Why this domain matters

Every Claude user eventually hits an output that is vague, wrongly formatted, incomplete, or confidently wrong — the difference between a casual user and a certified Associate is what happens next. Anthropic's own guidance frames unhelpful answers as a *diagnosable* problem (usually missing clarity, missing context, or an un-decomposed task) rather than a random one, and frames improvement as an iterative loop of feedback and refinement. This domain tests whether you can name the failure, trace it to a cause, apply the right fix instead of guessing, and — when the same failure keeps recurring — step back and fix the *workflow* (a template, a Project, a different model or feature) instead of patching one prompt at a time.

---

## Objective 7.1 — Identify, diagnose, and resolve issues with underperforming prompts or poor outputs

### The core diagnostic mindset

Before changing anything, do three things:

1. **Name the symptom precisely.** "The output is bad" is not diagnosable. "The output is a wall of prose when I needed a table" or "it invented a statute number" is.
2. **Locate the cause.** Most failures trace back to one of five places: the *instructions* (unclear or conflicting), the *context* (missing background the model needed), the *task size* (too much asked at once), the *knowledge boundary* (asking for facts the model doesn't reliably have — for example, events after its training cutoff), or the *conversation state* (a long, cluttered thread pulling the model in old directions).
3. **Change one thing at a time.** If you rewrite the whole prompt at once, you won't know which change worked — which matters when you need to make the fix repeatable.

Anthropic's help guidance for unhelpful answers boils down to four principles that map directly onto these causes: explain your ask simply and clearly; include as much context as possible (pretend you are instructing someone with no background knowledge); break complex requests into substeps; and give Claude feedback — follow-up instructions, clarifications, or a request to rewrite.

### Symptom → likely cause → fix table

This table is the heart of the domain. Exam scenarios typically describe a symptom and ask for the *most appropriate* fix — so practice moving left to right.

| Symptom | Likely cause | First-line fix |
|---|---|---|
| **Vague, generic, or surface-level output** | Vague prompt: no audience, purpose, constraints, or success criteria given | Be clear and direct. Add context: who the output is for, what it will be used for, what "good" looks like, length and depth expectations. Pretend you're briefing someone with zero background knowledge. |
| **Wrong format** (prose instead of a table, missing sections, wrong structure) | Format was implied, not specified — or specified only in words with no example | State the format explicitly and show it: give an example of the desired output, or a skeleton/template to fill in. Structure the prompt itself (e.g., with clearly delimited sections such as XML-style tags) so instructions, input data, and format spec don't blur together. |
| **Hallucination** (fabricated facts, citations, quotes, links that look authoritative) | The model is generating plausible text beyond what it actually knows — e.g., asked about post-cutoff events, or asked for specifics no source in the conversation contains | Give explicit permission to say "I don't know." Ground the task in provided documents: ask for word-for-word quotes first (especially for long documents) and instruct Claude to use only the provided material, not general knowledge. Require citations for claims. Then *verify* — check cited claims against the original source before the output goes anywhere consequential. These techniques reduce hallucinations; they do not eliminate them. |
| **Instructions ignored or only partially followed** | Too many asks packed into one prompt; buried or conflicting instructions; a long thread where earlier instructions have been superseded | Break the request into substeps and run them in sequence (task decomposition / chaining). Consolidate requirements into one clearly structured prompt with no contradictions. Put the most important constraints prominently and unambiguously. |
| **Output cut off or too brief / partially complete** | The response ended before the task did | Retool the prompt (ask for the continuation explicitly); per Anthropic's guidance, provide the previous prompt and response when writing your next prompt so Claude can pick up where it left off. For inherently large deliverables, request them in sections. |
| **Degraded quality late in a long conversation** (mixing up earlier requirements, reverting to abandoned directions, generic answers) | Long, cluttered conversation state: the accumulated thread contains stale instructions and dead ends competing with your current ask | Summarize the decisions and requirements that still matter, then start a fresh conversation seeded with that summary. If the same background is needed every time, move it into a Project so it persists without re-pasting. |
| **Factually outdated answer on current events** | Question falls after the model's knowledge cutoff — every model is trained on data up to a cutoff date and may not know about later events | Recognize the boundary rather than re-prompting harder. Supply the current information yourself (paste the source), or use a feature that retrieves current information (e.g., web search — then review Claude's cited sources, since response quality depends on the underlying sources). |

### Worked diagnosis: from failing prompt to fix

Walk through one failure end-to-end, the way an exam scenario unfolds.

**The failing prompt:**

> "Summarize the attached customer feedback and tell me what to do about it."

**The output:** three paragraphs of generalities ("customers value responsiveness"), no priorities, no structure, one recommendation that doesn't match the feedback.

**Step 1 — Name the symptoms.** Two distinct symptoms, not one: (a) vague, surface-level analysis; (b) no usable structure for the recommendations.

**Step 2 — Locate the causes.** (a) The prompt gives no audience, purpose, or definition of a useful summary — a context failure. (b) No output format was specified — a format failure. Note what it is *not*: it is not a hallucination problem, not a knowledge-cutoff problem, and not a model-capability problem, so neither grounding techniques nor a model change is the right first move.

**Step 3 — Apply targeted fixes, one per cause:**

> "You are helping a product manager prepare for a quarterly planning meeting. Summarize the attached customer feedback for that audience.
>
> Structure the output as:
> 1. **Top 3 themes** — each with a one-line description and 1–2 representative verbatim quotes from the feedback
> 2. **Severity table** — theme, number of mentions, suggested priority (high/medium/low)
> 3. **Recommended next steps** — max 3, each tied explicitly to a theme above
>
> Base everything only on the attached feedback. If the feedback doesn't support a clear recommendation, say so rather than guessing."

**Step 4 — Note the technique inventory used:** added role and audience context; specified explicit output structure; required verbatim quotes to ground claims in the source material; restricted Claude to the provided document; gave permission not to force an answer. Every one of these is a documented technique — the skill being tested is *choosing which ones the symptoms call for*.

**Step 5 — If this task recurs weekly**, the improved prompt becomes a template, and the standing context ("you are helping a product manager…", formatting rules) moves into a Project's instructions — the Objective 7.3 move.

### Rapid triage checklist

Use before writing (pre-flight) and after a disappointing output (post-mortem):

**Pre-flight**

- [ ] Have I stated the task simply and unambiguously?
- [ ] Would a stranger with no background knowledge have everything needed to do this?
- [ ] Have I specified the output format (structure, length, audience, tone) — ideally with an example?
- [ ] Is this really one task, or several that should be sequenced?
- [ ] Does the task depend on facts Claude may not have (recent events, internal data)? If so, have I supplied them?

**Post-mortem**

- [ ] What exactly is wrong — content, format, depth, accuracy, completeness? (Name it in one sentence.)
- [ ] Which of the five cause families does it map to: instructions, context, task size, knowledge boundary, conversation state?
- [ ] What is the *single* change most likely to fix it?
- [ ] Is this a wording problem at all — or a verification, feature, or model-selection problem?
- [ ] Has this failure happened before? If yes, what structural change prevents the next occurrence?

### Resolving vs. tolerating: when the prompt isn't the problem

A certified Associate also recognizes failures that prompt-wording *cannot* fix:

- **Knowledge-boundary failures.** No rewording makes a model know last week's news from training data alone. The fix is supplying the information or using retrieval — or accepting the limit.
- **Wrong-tool failures.** Anthropic's prompt-engineering guidance is explicit that not every problem is best solved by prompt engineering — for example, latency and cost concerns are often better addressed by selecting a different model. If outputs are fine but too slow or too expensive for a high-volume task, that's a Domain 3 model-selection fix, not a prompt fix.
- **Trust failures.** If the task is high-stakes (legal, medical, financial, compliance), the resolution always includes human verification. Anthropic's guidance is direct: do not rely on Claude as a singular source of truth, and carefully scrutinize high-stakes advice. "Fixing the prompt" never substitutes for validating the output.

---

## Objective 7.2 — Adjust approach based on feedback and results

### The iterate-from-feedback loop

Prompt improvement is an empirical loop, not a one-shot art. Anthropic's prompt-engineering guidance assumes you have (1) a clear definition of success for the task, (2) a way to test outputs against it, and (3) a draft to improve. In day-to-day (non-API) terms, the loop looks like this:

1. **Define "good" before you prompt.** What must the output contain, for whom, in what format? If you can't state it, Claude can't hit it.
2. **Run the prompt and compare the result against that definition.** Note *specific* gaps: missing sections, wrong tone, unsupported claims.
3. **Diagnose using the table above.** Match each gap to a cause.
4. **Give targeted feedback in-conversation.** Follow-up instructions, clarifications, or "rewrite this with X" are an officially recommended fix path — you don't always need to start over. Correct the specific failure, not "make it better."
5. **Fold the lesson back into the prompt.** When a follow-up correction works, the correction belongs in the *next version of the original prompt* (or the Project instructions), so you don't pay the same correction cost every time.
6. **Know when to reset.** If a thread has accumulated so many corrections that new outputs keep regressing, summarize what you've learned and start clean with an upgraded prompt.

### Feedback in both directions

- **Feedback *to* Claude:** clarifications, examples of what you wanted, asking it to critique or verify its own draft against your criteria (iterative refinement — using an output as input for a follow-up prompt that verifies or expands it is a documented technique).
- **Feedback *about* Claude:** in the Claude apps you can use the thumbs-down control to flag an unhelpful response to Anthropic. This improves the product; it does not fix your current output — exam answers should never treat "rate the response" as a resolution step.

### Interpreting results honestly

Two evaluation habits distinguish strong candidates:

- **Don't mistake confidence for accuracy.** Claude can produce text (including quotes and citations) that looks authoritative but is not grounded in fact. Self-reported confidence is not a validation method.
- **Check consistency.** Running the same prompt more than once and comparing outputs can surface hallucinations — inconsistency across runs is a warning sign that a claim is fabricated rather than known.

---

## Objective 7.3 — Optimize workflows for efficiency and effectiveness

Troubleshooting fixes one bad output. Optimization asks: *why does this failure or this cost keep happening, and what structural change removes it?*

### From repeated fixes to structural fixes

| Recurring pattern | Structural optimization |
|---|---|
| You paste the same background/instructions into every new chat | Create a **Project** with instructions and knowledge sources, so context persists across conversations. Keep project instructions concise — general context, key guidelines, and Claude's role. |
| You rebuild similar prompts from scratch for a routine task | Save a **prompt template**: a tested prompt with slots for the parts that change (input text, audience, date). Templates make quality repeatable and make iteration cumulative instead of starting from zero. |
| Many similar small items processed one chat at a time | **Batch** them: provide the items together with one clear instruction set and a specified output structure (e.g., "for each of these 12 replies, produce X in format Y"). One well-structured request beats twelve improvised ones — but keep batches small enough that per-item quality doesn't degrade, and spot-check items. |
| One giant prompt keeps producing tangled results | **Chain** the work: decompose into sequenced steps (extract → analyze → draft → format), passing each step's output into the next. |
| Outputs are fine but slow/costly for a simple high-volume task — or too shallow for a complex one | Revisit **model selection**: match the model to task requirements (cost, speed, quality) instead of prompt-tweaking around a mismatch. |
| The task needs current or external information every time | Use the **feature** built for it (e.g., web search / research capabilities) rather than fighting the knowledge cutoff — and review cited sources. |
| Long working sessions keep hitting context problems | Manage context deliberately: Projects use retrieval (RAG) to load only relevant knowledge into context; keep instructions concise; be mindful that active tools and connectors consume context. Summarize-and-restart remains the manual fallback. |

### Efficiency vs. effectiveness

Optimization on the exam is a *balancing* judgment, echoing the credential's purpose statement ("balance quality, efficiency, and cost"):

- **Efficiency** improvements: fewer iterations to an acceptable output, less re-pasting of context, faster/cheaper model where quality permits, batching where quality holds.
- **Effectiveness** improvements: higher first-pass quality via better templates and Project instructions, verification steps for anything high-stakes, format specifications that eliminate rework.
- The trap answers in exam items usually maximize one at the expense of the other: "always use the most capable model" (ignores cost/speed), "skip verification to save time" (ignores risk), "batch everything into one prompt" (ignores quality degradation on complex composite tasks).

### Knowing when to escalate

Optimization has a ceiling for an Associate. If the recurring problem requires API integration, automated pipelines, custom evaluation harnesses, or agentic system design, the correct "optimization" is escalation to Claude Developer/Architect roles — recognizing that boundary is itself a blueprint competency.

---

## How this domain is tested — exam strategy

Domain 7 items are almost always **scenario-first**: a short situation describing a symptom, followed by "What is the *most appropriate* action?" Mirroring the exam guide's Section 8 samples, expect one clearly best answer, one plausible-but-weaker answer, and two distractors that either do nothing about the cause or trade away something important.

Reliable elimination patterns:

- **Eliminate answers that trust the model to police itself.** "Ask Claude if it's sure," "ask Claude to rate its confidence," "send it if Claude confirms" — self-report is never the validation step.
- **Eliminate brute-force repetition.** "Resend the same prompt," "try again until it works," "add MORE emphasis" — no diagnosis, no fix.
- **Eliminate over-corrections.** "Abandon the task," "switch platforms," "always use the most expensive model," "remove all context to simplify" — these trade away quality, cost, or the task itself instead of addressing the cause.
- **Prefer answers that (1) identify the cause and (2) change the input accordingly** — add context, specify format with an example, decompose, ground in sources, summarize-and-restart, or move standing context into a Project.
- **Watch for the "wrong lever" item.** At least occasionally, the correct answer is that prompting is not the fix: the scenario needs verification against an authoritative source (Domain 2 overlap), a different model (Domain 3 overlap), or escalation to a technical role.

Budget-wise: at 10% weight this domain is worth roughly 6 of 60 items — enough to matter, small enough that the symptom→cause→fix table plus these elimination habits cover nearly everything it can ask.

---

## Trainer notes

### Teaching tips

- **Teach the table as a reflex, not a reference.** Drill symptom → cause → fix aloud: you call out a symptom ("it gave me prose, I wanted JSON-like structure"), learners answer with cause and fix in one breath. Exam items reward the *most appropriate first action*, so train learners to rank fixes, not just list them.
- **Anchor everything in "one change at a time."** Learners instinctively rewrite entire prompts. Force single-variable edits in exercises so they experience attribution: *which* change fixed it?
- **Contrast fixable vs. unfixable by prompting.** The most common classroom error is treating hallucination and knowledge-cutoff issues as wording problems. Use a live example: no rephrasing makes the model reliably know a post-cutoff event.
- **Connect Domain 7 to Domain 2.** Diagnosis (7) depends on evaluation (2). A quick recap of hallucination-spotting before this module pays off.

### Discussion prompts

1. "Your prompt worked perfectly last month; the same prompt is now producing weaker results in a 60-message thread. What are the plausible causes, and what would you try first — and why *that* first?"
2. "A teammate says: 'I asked Claude to double-check its own answer and it said it was correct, so we shipped it.' What's wrong with this as a validation strategy, and what would a legitimate check look like?"
3. "When is it better to keep correcting within a conversation versus starting a new one? What information should survive the reset, and where should it live?"
4. "Your team re-pastes a 2-page style guide into every chat. What are two structural fixes, and how would you decide between them?"
5. "Give an example where the *right* optimization is to stop prompt-engineering entirely. What signals tell you the prompt isn't the problem?"

### Common misconceptions

- **"Bad output means a bad model."** Most underperformance traces to missing clarity, context, or decomposition — the officially documented first checks — not model capability.
- **"Hallucinations can be eliminated with the right prompt."** Grounding, permission to say "I don't know," and citation requirements *reduce* hallucinations; official guidance is explicit that they don't eliminate them. Verification stays in the workflow.
- **"Confident tone or a specific citation means it's right."** Fabricated content can look authoritative — specificity is not evidence.
- **"Longer prompts are always better."** More *relevant* context helps; contradictory, bloated, or redundant instructions cause ignored-instruction failures. Concise, structured, unambiguous wins.
- **"Thumbs-down fixes my output."** It's product feedback to Anthropic, not a troubleshooting step for the task in front of you.
- **"Iteration means retyping the same request more forcefully."** Iteration means changing something diagnosable: context, structure, decomposition, format spec, or feature/model choice.

### Hands-on classroom exercise: the Troubleshooting Clinic

**Setup (10 min):** Prepare four deliberately broken prompts, one per failure family, e.g.:

1. *Vagueness:* "Write something about our product for the newsletter." (no product info, audience, length, tone)
2. *Format failure:* "Summarize this meeting transcript." (learner secretly needs a decisions/owners/deadlines table)
3. *Hallucination bait:* "List the five key provisions of the 2025 Riverside Data Act with section numbers." (fictitious law)
4. *Overload:* one prompt demanding a competitive analysis + pricing recommendation + email draft + slide outline simultaneously.

**Run (30 min):** Pairs rotate through stations. For each prompt they must (a) run it and *name the symptom* in one sentence, (b) diagnose the cause using the module's table, (c) apply **one** targeted fix and re-run, (d) record before/after. For station 3, the required "fix" is recognizing that verification/grounding — not rewording — is the correct response, and demonstrating a grounding technique (permission to say "I don't know" / restrict to provided sources).

**Debrief (15 min):** Each pair presents their worst-to-best transformation. Close by asking which of the four failures would justify a *workflow-level* fix (template, Project, different feature) if it recurred weekly.

---

## Practice questions

> These are original practice items written in the style of the exam guide's Section 8 samples. They are **not** actual exam items and are not drawn from any live item bank. Unless an item states otherwise, select ONE response.

**Q1.** An operations analyst asks Claude to "improve our onboarding doc" and receives generic advice that could apply to any company. What is the most appropriate next step?

- A. Switch to a more capable model and resend the identical prompt.
- B. Re-send the prompt with added context: the actual document, the audience, the specific problems to fix, and what a successful revision looks like.
- C. Ask Claude why its answer was generic.
- D. Report the response using the thumbs-down button and wait for improvements.

**Q2.** A marketer asks Claude for a competitor summary as "a table with columns for company, pricing, and key differentiator," but keeps receiving paragraphs of prose across several attempts. Which adjustment is most likely to resolve the formatting failure?

- A. Repeat the same prompt in a new conversation until the format appears.
- B. Ask for the output in a different file type.
- C. Restructure the prompt so the format specification is explicit and prominent, and include a small example of the desired table for Claude to follow.
- D. Shorten the prompt by removing the background context about the competitors.

**Q3.** Claude produces a market overview citing a named industry report with specific percentage figures. The user cannot find the report anywhere. What is the best interpretation and response?

- A. The report is probably paywalled; cite it anyway since Claude referenced it.
- B. The citation may be hallucinated; treat the figures as unverified, and re-run the task grounded in source documents the user provides, instructing Claude to use only those sources.
- C. Ask Claude to confirm the report exists; if it says yes, proceed.
- D. Ask Claude to regenerate the answer with more confident wording.

**Q4.** An associate's single prompt asks Claude to analyze survey data, draft an executive summary, propose three initiatives, and write a rollout email. The output addresses the analysis well but skims or skips the rest. What is the most appropriate fix?

- A. Add "make sure you complete every part" to the same prompt and resend.
- B. Break the request into sequential steps, feeding each step's output into the next.
- C. Move the email request to the beginning of the prompt.
- D. Ask for the output twice and merge the two responses.

**Q5.** Deep into a very long conversation with many changed requirements, Claude begins reintroducing ideas the user rejected an hour earlier and mixing up current constraints. What is the most effective response?

- A. Scold the model within the thread and restate that the old ideas were rejected.
- B. Summarize the current, still-valid requirements and decisions, then start a fresh conversation seeded with that summary.
- C. Continue the thread but write in all caps for emphasis.
- D. Abandon the task, since degradation means the model cannot handle it.

**Q6.** A support team uses Claude to draft replies to roughly 40 similar tickets per day. Each agent writes a new prompt from scratch each time, re-explaining the company's tone rules, and quality varies widely between agents. Which TWO changes best optimize this workflow? (Select TWO.)

- A. Store the tone rules and product context as persistent instructions in a shared Project instead of re-explaining them per chat.
- B. Require each agent to use the most capable, highest-cost model for every ticket.
- C. Standardize on a tested prompt template with slots for the ticket-specific details.
- D. Prohibit follow-up messages so agents accept the first draft as-is.
- E. Have each agent rate every response with thumbs-up to lock in quality.

**Q7.** An associate has refined a summarization prompt through several rounds of in-chat corrections, and the latest outputs are finally excellent. Tomorrow the same task must be done again on a new document. What should the associate do to benefit from today's iteration?

- A. Keep the long conversation open forever and append tomorrow's document to it.
- B. Nothing — Claude will remember the corrections in any new chat automatically.
- C. Consolidate the successful corrections into an updated reusable prompt (or Project instructions), so the next run starts from the improved version.
- D. Re-run tomorrow's task with the original first-draft prompt to keep results comparable.

**Q8.** Claude's outputs for a high-volume classification task are consistently accurate, but the workflow feels too slow and costly for such a simple task. Prompt tweaks haven't changed this. What does official guidance suggest is the appropriate lever?

- A. Keep prompt-engineering until latency improves.
- B. This is not a prompt-engineering problem; select a faster, lower-cost model suited to the straightforward task.
- C. Remove the accuracy checks to save time.
- D. Split every item into its own conversation to speed things up.

### Answers

**Q1 — Correct: B**

- **Why B:** Generic output is the classic symptom of a context-starved prompt. Official guidance for unhelpful answers is to explain the ask clearly and include as much context as possible, as if briefing someone with no background knowledge.
- **Why not A:** A model upgrade doesn't supply missing context.
- **Why not C:** Asking why doesn't fix the input.
- **Why not D:** Thumbs-down is product feedback, not a resolution.

**Q2 — Correct: C**

- **Why C:** Wrong-format failures are resolved by making the format specification explicit, prominent, and structurally separated from other content — and examples are one of the most effective ways to show the desired output shape.
- **Why not A/B/D:** Blind retries, changing file type, or deleting useful context don't address the cause.

**Q3 — Correct: B**

- **Why B:** Claude can produce citations and quotes that look authoritative but are not grounded in fact; an unfindable source is a hallucination red flag. The remedy is verification plus grounding: restrict Claude to user-provided sources and require support for claims.
- **Why not A:** Citing unverified material compounds the error.
- **Why not C:** Self-confirmation is not validation.
- **Why not D:** Confident rewording is not validation.

**Q4 — Correct: B**

- **Why B:** Partially followed instructions on a multi-part request point to task overload; the documented fix is breaking complex requests into substeps (decomposition/chaining) so each part gets full attention.
- **Why not A/C:** Emphasis phrases and reordering don't reduce the load.
- **Why not D:** Merging two inconsistent outputs creates new problems.

**Q5 — Correct: B**

- **Why B:** Long, cluttered conversation state — stale instructions and rejected directions still in context — degrades output relevance. Summarizing what still matters and restarting cleanly preserves progress while removing interference.
- **Why not A/C:** Leave the clutter in place.
- **Why not D:** Abandons a solvable problem.

**Q6 — Correct: A and C**

- **Why A and C:** Recurring re-explanation of the same context is the signal for a structural fix: a Project makes shared instructions and knowledge persistent, and a tested template makes per-ticket prompting fast and consistent.
- **Why not B:** Forcing the top model everywhere ignores the cost/speed/quality balance for routine drafts.
- **Why not D:** Banning iteration removes a documented improvement mechanism.
- **Why not E:** Ratings don't standardize inputs.

**Q7 — Correct: C**

- **Why C:** Iteration only compounds if lessons are captured: fold the successful corrections back into the reusable prompt or the Project instructions.
- **Why not A:** An ever-growing thread invites long-conversation degradation.
- **Why not B:** Separate chats don't automatically inherit one conversation's corrections.
- **Why not D:** Reverting to the weak draft discards the improvement.

**Q8 — Correct: B**

- **Why B:** Anthropic's prompt-engineering guidance states that not every problem is best solved by prompt engineering — latency and cost can often be more easily improved by selecting a different model. Since quality is already sufficient, matching a faster, lower-cost model to the straightforward task is the right optimization.
- **Why not A:** Fights the wrong lever.
- **Why not C:** Sacrifices effectiveness.
- **Why not D:** Adds overhead without addressing cost or speed.

---

## Sources

Official Anthropic pages verified for this module (accessed July 2026):

- https://support.claude.com/en/articles/7996857-my-prompt-isn-t-giving-me-a-helpful-answer — clarity, context ("no background knowledge" framing), breaking requests into substeps, giving Claude feedback/rewrites.
- https://support.claude.com/en/articles/8525154-claude-is-providing-incorrect-or-misleading-responses-what-s-going-on — hallucination definition, authoritative-looking but ungrounded content, not relying on Claude as a singular source of truth, scrutinizing high-stakes advice, reviewing web-search citations, thumbs-down feedback.
- https://support.claude.com/en/articles/8114518-claude-s-response-to-my-prompt-is-too-brief — handling brief/partial responses by retooling prompts and supplying the previous prompt and response to continue.
- https://support.claude.com/en/articles/8114494-how-up-to-date-is-claude-s-training-data — model knowledge cutoffs and unawareness of later events.
- https://support.claude.com/en/articles/8606394-how-large-is-the-context-window-on-paid-claude-plans — Projects using retrieval (RAG), keeping project instructions concise, tools/connectors consuming context.
- https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview (docs.claude.com prompt-engineering overview) — success criteria and empirical testing before prompt engineering; latency/cost sometimes better solved by model selection than prompting.
- https://platform.claude.com/docs/en/test-and-evaluate/strengthen-guardrails/reduce-hallucinations — permission to say "I don't know," quote-based grounding for long documents, citation verification, best-of-N consistency checks, iterative refinement, restricting to provided documents; reduction, not elimination.
- https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices — technique names: be clear and direct, add context, use examples, XML-tag structuring, role prompting, output format control, chaining complex prompts.
