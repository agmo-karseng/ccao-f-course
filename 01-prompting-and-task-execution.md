---
title: "1. Prompting & Task Execution"
nav_order: 3
---

# Module 1 — Prompting and Task Execution (Domain 1, 14%)

> **Blueprint objectives covered in this module**
>
> 1. Create effective prompts for business and technical tasks
> 2. Apply task decomposition techniques to structure complex requests
> 3. Iterate prompts to improve output quality
> 4. Adapt prompting strategies based on task type (analysis, research, drafting, brainstorming)

---

## Why this domain matters

Domain 1 carries 14% of the CCAO-F exam — roughly 8 of 60 items — and it underpins every other domain: you cannot evaluate outputs (Domain 2), choose features (Domain 3), or troubleshoot poor results (Domain 7) if the prompt itself is weak. The exam's minimally qualified candidate is "distinguished by their ability to translate business objectives into effective AI interactions" and to "create structured prompts" (Exam Guide, Sections 3–4). Expect scenario items that describe a workplace task and a first-attempt prompt, then ask which change would most improve the result. This module teaches the judgment those items test: clarity, structure, decomposition, and deliberate iteration.

---

## Objective 1.1 — Create effective prompts for business and technical tasks

### The core principle: be clear and direct

Anthropic's guidance is consistent across its documentation: Claude responds best to clear, explicit, specific instructions. Two mental models from official sources anchor everything else in this domain:

- **The "new employee" model.** Anthropic's prompting best practices say to think of Claude as "a brilliant but new employee who lacks context on your norms and workflows." The help center uses a similar frame: treat Claude like "a newly-hired contractor" with no context about you, your task, or your organization — so give very specific instructions about exactly what you want.
- **The golden rule of clear prompting.** Show your prompt to a colleague who has minimal context on the task and ask them to follow it. If *they* would be confused, Claude will be too.

For the exam, this means: when a scenario shows a vague prompt producing a disappointing output, the best answer is almost always "add specificity and context," not "switch tools," "regenerate and hope," or "add forceful language."

### The anatomy of an effective business prompt

A reliable prompt for a business task typically supplies five things:

| Element | What it answers | Example fragment |
|---|---|---|
| **Task** | What exactly should Claude do? | "Draft a one-page project status update" |
| **Context / motivation** | Why? Who is it for? What's the situation? | "…for the executive steering committee, who only meet monthly and need decisions flagged" |
| **Inputs** | What material should Claude work from? | Pasted meeting notes, an uploaded report, a data table |
| **Constraints and format** | Length, structure, tone, what to include/exclude | "Under 400 words; sections: Progress, Risks, Decisions Needed; neutral tone" |
| **Success criteria** | What does "good" look like? | "A reader should be able to identify the two decisions we need in under a minute" |

Anthropic's docs specifically call out two of these as high-leverage:

- **Add context and motivation.** Explaining *why* an instruction matters helps Claude "better understand your goals and deliver more targeted responses." Claude generalizes from the explanation — "avoid jargon because this goes to customers with no technical background" outperforms a bare "avoid jargon."
- **Be specific about output format.** State the desired format and constraints explicitly, and use numbered steps or bullets when the order or completeness of steps matters. A further documented technique: **tell Claude what to do instead of what not to do** — for example, instead of "Do not use markdown," say "Write in smoothly flowing prose paragraphs."

### Before/after example (business task)

**Scenario:** An operations lead wants help communicating a delivery delay.

> **Before (weak):**
> "Write an email about the shipping delay."

Claude has to guess the audience, cause, severity, tone, remedy, and length. The output may be generically apologetic and unusable.

> **After (effective):**
> "You are helping me, an operations manager at a mid-size furniture retailer, draft a customer email.
>
> Context: A port strike has delayed about 1,200 customer orders by 10–14 days. Affected customers already received an automated 'delayed' status, so this email must add real information, not repeat the status.
>
> Task: Draft the email. It should (1) state the new delivery window plainly in the first two sentences, (2) explain the cause in one sentence without blaming partners, (3) offer the two remedies we approved — free shipping refund or cancellation with full refund — with clear instructions for each, and (4) close warmly but briefly.
>
> Constraints: Under 200 words, plain language a non-native English speaker can follow, no exclamation marks, subject line included."

Every element the "before" prompt left to chance is now specified. Notice this also uses a light **role** ("you are helping me, an operations manager…") — Anthropic documents that setting a role focuses Claude's behavior and tone, and that even a single sentence makes a difference.

### Structuring technical or mixed-content prompts

When a prompt mixes instructions, background context, reference documents, and examples, the documented technique is to **separate the parts with XML-style tags** such as `<instructions>`, `<context>`, and `<input>`. This helps Claude parse the prompt unambiguously — it can no longer confuse "text I want you to edit" with "instructions about how to edit it." Best practices from the docs: use consistent, descriptive tag names, and nest tags when content has a natural hierarchy (e.g., multiple documents each inside their own `<document>` tag).

> **Example (technical task):**
> ```
> <instructions>
> Review the SQL query below. Identify performance problems and rewrite it.
> Explain each change in one sentence. Do not change the columns returned.
> </instructions>
>
> <context>
> The orders table has ~40 million rows. The query runs in a nightly
> reporting job that currently takes 25 minutes.
> </context>
>
> <input>
> SELECT * FROM orders WHERE YEAR(order_date) = 2026 ...
> </input>
> ```

### Using examples (few-shot / multishot prompting)

Anthropic describes well-crafted examples as "one of the most reliable ways to steer Claude's output format, tone, and structure." Documented guidance:

- Include **3–5 examples** for best results.
- Make examples **relevant** (mirroring the real use case), **diverse** (covering edge cases so Claude doesn't learn unintended patterns), and **structured** (wrapped in `<example>` tags, with multiple examples inside `<examples>` tags).
- You can even ask Claude to critique your examples or generate more from your initial set.

**Business application:** A support team lead wants ticket summaries in a house style. Rather than describing the style in ten adjectives, she pastes three real tickets each followed by an ideal summary, then the new ticket. The examples carry the format, length, and tone implicitly.

### Long inputs: put documents first, question last

For prompts containing long documents or data-rich inputs, Anthropic's documented guidance is to **place the long material near the top of the prompt, above the query and instructions**. Putting the query at the end can improve response quality significantly in Anthropic's testing (up to 30% in tests with complex, multi-document inputs). For long-document tasks, also consider asking Claude to **quote the relevant passages first** before answering — this grounds the response in the actual text.

---

## Objective 1.2 — Apply task decomposition techniques to structure complex requests

### Why decompose

Anthropic's help center advice for prompts that aren't producing helpful answers includes a decomposition instruction directly: "Break down complex requests into substeps." Large, fuzzy requests ("build our Q3 marketing plan") force the model to make dozens of unstated decisions at once. Decomposition converts one unreliable mega-task into a sequence of small, checkable tasks — which also gives *you* checkpoints for review, a theme the exam returns to in Domain 2.

### Three decomposition patterns

**Pattern A — Steps within a single prompt.**
Keep one prompt, but enumerate the steps in order. Anthropic recommends providing instructions "as sequential steps using numbered lists or bullet points when the order or completeness of steps matters."

> "Analyze the attached customer survey export in three steps:
> 1. List the five most frequent complaint themes with approximate counts.
> 2. For each theme, quote two representative verbatim responses.
> 3. Only after steps 1–2, recommend the top three fixes, each tied to a theme."

The ordering matters: forcing evidence-gathering (steps 1–2) before conclusions (step 3) produces recommendations grounded in the data rather than generic advice.

**Pattern B — Sequential prompts (prompt chaining).**
Break the work into separate turns, reviewing each intermediate output before feeding it into the next request. Anthropic's docs note that explicit chaining is especially useful "when you need to inspect intermediate outputs or enforce a specific pipeline structure," and highlight **self-correction** as the most common chaining pattern: *generate a draft → have Claude review the draft against criteria → have Claude refine it based on the review.*

> Turn 1: "From these interview notes, extract every distinct client requirement as a numbered list. Don't interpret yet."
> Turn 2 (after you fix two misread requirements): "Group the corrected requirements into workstreams and flag conflicts."
> Turn 3: "Draft the statement of work for workstream 2 only."

**Pattern C — Decompose the *thinking*, not just the work.**
For analysis, ask Claude to reason step-by-step before concluding — Anthropic lists chain-of-thought style reasoning ("explain its reasoning step-by-step before giving a final answer") as a verification technique that "can reveal faulty logic or assumptions." Separating reasoning from the final answer (e.g., with `<thinking>` and `<answer>` style tags) keeps the deliverable clean while making the logic auditable.

### Choosing between one prompt and a chain

| Situation | Better approach |
|---|---|
| Steps are mechanical and low-risk; you'll review only the end product | Single prompt with numbered steps (Pattern A) |
| Errors in early steps would poison later steps; human review adds value mid-stream | Chain of prompts with review between turns (Pattern B) |
| The conclusion matters more than the artifact; you need to trust the logic | Step-by-step reasoning before the answer (Pattern C) |
| Output must pass a quality bar before use | Add a self-correction pass: draft → critique against criteria → revise |

**Exam signal:** When a scenario describes a complex, multi-part deliverable and a candidate who "asked for everything at once and got a shallow result," the credited response typically involves breaking the request into sequenced parts with review points — not simply asking again more forcefully or moving to a different tool.

---

## Objective 1.3 — Iterate prompts to improve output quality

### Iteration is the normal workflow, not a failure

Anthropic's help center describes the loop explicitly: give Claude feedback through "follow-up instructions, clarifications, or ask it to rewrite an answer." First outputs are drafts. A skilled associate treats the first response as diagnostic information about what the prompt failed to specify.

The prompt engineering overview adds an important precondition: effective iteration assumes you have **a clear definition of success criteria** and some way to test against them. If you can't say what "better" means, you can't iterate toward it — you can only regenerate and gamble.

### A practical iteration protocol

1. **Define success first.** What would make this output usable as-is? (Audience, length, format, accuracy bar, tone.)
2. **Run the prompt and diagnose the gap.** Name what's wrong specifically: wrong audience? too long? missing the pricing section? invented figures?
3. **Fix the prompt, not just the output.** Each gap usually maps to a missing element from the anatomy table in 1.1 — absent context, unstated format, no success criteria.
4. **Give targeted feedback in-conversation.** "Rewrite section 2 for a reader who has never seen our product; keep sections 1 and 3 unchanged" beats "make it better."
5. **Prefer additive precision over volume.** If Claude misread intent, clarify the intent; don't paste three more paragraphs of loosely related background.
6. **Carry the lesson forward.** When a phrasing finally works, reuse it — in Projects instructions or your team's prompt library (configuration is Domain 5's territory, but the habit starts here).

### Documented refinement techniques worth naming on the exam

From Anthropic's guardrail and best-practices documentation:

- **Allow uncertainty.** Explicitly give Claude permission to say "I don't know" when information is missing — Anthropic states this simple technique can drastically reduce false information. Iterating a fact-heavy prompt often means *adding* this permission.
- **Ground in quotes and citations.** For document-based tasks, ask Claude to extract word-for-word quotes before answering, and to cite support for each claim (retracting claims it cannot support). This makes outputs auditable and reduces hallucination.
- **Iterative refinement.** Use Claude's output as input to a follow-up prompt asking it to verify or expand on its previous statements — a documented technique for catching inconsistencies.
- **Self-check instructions.** Anthropic recommends appending an instruction like "Before you finish, verify your answer against [the criteria]" — a self-review pass catches errors reliably.
- **Positive framing.** When output format keeps drifting, restate constraints as what to do ("write flowing prose paragraphs") rather than what to avoid ("no bullet points"), and match your prompt's own style to the style you want back.

### Before/after example (iteration)

**First attempt:** "Summarize this 30-page vendor contract."
**Output problem:** A generic abstract; misses renewal terms; states a liability cap the associate can't find in the document.

**Iterated prompt:**
> "Summarize the attached vendor contract for our procurement director, who needs to decide by Friday whether to renew.
> - Organize by: term & renewal, pricing & escalators, liability & indemnity, termination rights, unusual clauses.
> - For every material claim, quote the relevant clause verbatim with its section number.
> - If the contract is silent on any of these topics, say 'not addressed' rather than inferring.
> - End with the three clauses most worth negotiating and why."

The revision adds audience and purpose, imposes a decision-oriented structure, grounds claims in quoted clauses, and explicitly authorizes "not addressed" — directly applying documented anti-hallucination techniques.

### When iteration is the wrong tool

The overview docs note that not every failure is best solved by prompt changes — some problems (e.g., latency or cost) are better addressed by a different model choice, and others by different features or by escalation. If three well-diagnosed prompt revisions haven't moved quality, reconsider the approach (Domains 3 and 7) rather than iterating indefinitely.

---

## Objective 1.4 — Adapt prompting strategies based on task type

The same associate uses different prompt shapes for analysis, research, drafting, and brainstorming. The exam tests whether you match the strategy to the task's nature — its need for accuracy, evidence, structure, or divergence.

### Analysis tasks (interpret data or documents; accuracy is paramount)

- Put the material to analyze **at the top**, question last (documented long-context guidance).
- Demand **evidence before conclusions**: quote or cite first, then interpret.
- Ask for **step-by-step reasoning** before the final judgment so the logic is inspectable.
- Explicitly allow **"I don't know" / "the data doesn't show this."**
- Specify the analytical frame: "compare Q1 vs Q2 by region," not "analyze the sales data."

> *Prompt skeleton:* "Here is [data/document]. First, extract the figures relevant to [question], quoting or citing where each comes from. Then reason through what they show step by step. Finally, answer [question]. If the data is insufficient, say so and state what's missing."

### Research tasks (gather and synthesize information; verification is paramount)

Anthropic's documented guidance for research-style work: **provide clear success criteria** for what counts as a complete answer, **encourage verification across multiple sources**, and for complex research use a **structured approach** — develop competing hypotheses, track confidence, and self-critique the plan as work proceeds.

- Define scope tightly: time period, geography, source types, depth.
- State the deliverable: comparison table? annotated source list? one-page brief?
- Require sourcing so every claim can be checked (Domain 2 picks up from here: research outputs still require human verification before high-stakes use).

> *Prompt skeleton:* "Research [question]. Success means: [criteria]. Consider multiple possibilities before settling on conclusions, and note your confidence in each finding. Present findings as [format], with the source of each claim, and flag anything you could not verify."

### Drafting tasks (produce a document; fit-for-audience is paramount)

- Lead with **audience and purpose** — these drive tone, length, and content selection more than any other factor.
- Specify **format constraints** precisely (length, sections, tone, subject line, what to exclude).
- Provide **exemplars** when a house style exists (few-shot prompting is the documented tool for steering format and tone).
- Plan for a **revision pass** as part of the workflow — draft, then targeted feedback, then refine (the documented self-correction pattern).

> *Prompt skeleton:* "Draft [document] for [audience] who will use it to [purpose]. Match the style of the examples in `<examples>`. Constraints: [length, structure, tone]. "

### Brainstorming tasks (generate options; useful divergence is paramount)

- Ask for **quantity and variety explicitly**: "20 options spanning conservative to unconventional." Without this, you get a safe, samey list.
- **Defer judgment**: generate first, evaluate in a separate step or turn — a natural use of decomposition.
- Constrain the **dimensions of variation** ("vary by budget level and channel"), not the ideas themselves.
- Then flip modes: "Now act as a skeptical CFO and critique the top five" — using role framing (a documented technique) to stress-test the shortlist.

> *Prompt skeleton:* "Generate [N] distinct ideas for [goal], varying by [dimensions]. Don't evaluate them yet. Include at least [k] unconventional options."

### Quick-reference matrix

| Task type | Primary risk | Key prompt moves |
|---|---|---|
| Analysis | Confident wrong conclusions | Data first / question last; quotes and citations before conclusions; step-by-step reasoning; permit "insufficient data" |
| Research | Unverified or fabricated claims | Success criteria; multi-source verification; confidence tracking; sourced deliverable |
| Drafting | Wrong fit for audience | Audience + purpose up front; explicit format constraints; exemplars; draft → critique → revise |
| Brainstorming | Premature convergence, bland output | Ask for volume and variety; separate generation from evaluation; vary along named dimensions; role-based critique |

---

## Trainer notes

### Teaching tips

- **Teach the golden rule physically.** Have each learner hand their written prompt to a neighbor who must say, without help, exactly what they would produce. The gaps the neighbor finds are the gaps Claude will hit. This one exercise internalizes Objective 1.1 faster than any lecture.
- **Always show before/after pairs.** Weak-prompt-plus-diagnosis-plus-fix is the atomic unit of this domain. Build a slide bank of pairs drawn from your learners' own functions (HR, marketing, ops) so relevance is immediate.
- **Frame iteration as diagnosis, not retry.** Learners' default failure mode is regenerating with slightly angrier wording. Drill the habit: *name the specific gap, then fix the prompt element that caused it.*
- **Connect forward.** Flag where Domain 1 hands off: evidence-and-verification habits feed Domain 2 (evaluation); "iteration isn't working" feeds Domains 3 and 7 (model/feature selection, troubleshooting); reusable instructions feed Domain 5 (Projects configuration).
- **Keep product claims conservative.** Teach techniques (structure, examples, decomposition, iteration) as documented by Anthropic; avoid asserting UI specifics that change between releases.

### Discussion prompts

1. "Think of the last disappointing AI output you received at work. Which element was missing from the prompt — task, context, inputs, constraints, or success criteria — and how would you rewrite it?"
2. "When is it worth breaking a request into a chain of prompts with review between steps, and when is that overkill? What's the cost of each choice in a real deadline situation?"
3. "Anthropic recommends explicitly allowing Claude to say 'I don't know.' Why might a business user be reluctant to add that instruction — and what does that reluctance cost them?"
4. "You've iterated a prompt three times and quality hasn't improved. What are three explanations that have nothing to do with the wording of your prompt?"

### Common misconceptions

- **"Longer prompts are better prompts."** Precision beats volume. Irrelevant context can bury the actual instruction; the goal is completeness of the five elements, not word count.
- **"Magic phrases do the work."** There is no incantation that substitutes for context, constraints, and success criteria. Techniques like XML tags work because they add *structure*, not because the tags are magic words.
- **"If the first answer is wrong, the tool is bad."** First outputs are diagnostic. The documented workflow is feedback and refinement — iteration is the normal path to quality.
- **"Telling Claude what NOT to do is the strongest control."** Anthropic's documented formatting guidance is the opposite: state what you *do* want ("flowing prose paragraphs") rather than only prohibitions.
- **"One giant, detailed prompt is always superior to multiple turns."** For complex work where early errors compound, chaining with human review between steps is the documented and safer pattern.

### Hands-on classroom exercise (30–40 minutes): "The Prompt Repair Shop"

1. **Setup (5 min).** Give each pair the same deliberately weak prompt and a realistic input, e.g.: *"Summarize this"* + a two-page fictional incident report. Run it once and capture the mediocre output.
2. **Diagnose (5 min).** Pairs list, against the five-element anatomy, everything the prompt failed to specify (audience? purpose? format? evidence requirements? permission to flag gaps?).
3. **Repair (10 min).** Pairs rewrite the prompt applying at least three techniques from this module (e.g., role, XML structure, quote-grounding, numbered steps, success criteria) and run it.
4. **Iterate (10 min).** Each pair must then improve the output *once more* using targeted in-conversation feedback — not a full rewrite — and note what the follow-up fixed.
5. **Debrief (5–10 min).** Compare outputs across pairs. Which single change moved quality most? (Typically: naming the audience and decision the summary must support.) Close by mapping each fix back to a blueprint objective.

---

## Practice questions

*The following items are original practice questions written in the style of the exam guide's Section 8 samples. They are not actual exam items. Each question states how many responses to select. Answers and rationales follow in the "Answers" subsection.*

**Q1.** A marketing associate asks Claude: "Write something about our product launch." The output is generic and unusable. Which revision best applies effective prompting practice? (Select ONE.)

- A. "Write something about our product launch. This is very important, do a good job."
- B. "Draft a 150-word launch announcement for existing customers of our invoicing app, highlighting the new auto-reminder feature and its main benefit (fewer late payments), with a friendly tone and one clear call to action to try it."
- C. "Write something about our product launch" submitted three times, keeping the best result.
- D. "You are the world's greatest marketer. Write something about our product launch."

**Q2.** A project manager must produce a vendor-selection recommendation involving requirements analysis, scoring of three proposals, and a final memo. She wants to be able to correct Claude's understanding of the requirements before any scoring happens. Which approach best fits her need? (Select ONE.)

- A. One comprehensive prompt requesting the analysis, scoring, and memo together, since Claude handles multi-part requests.
- B. A sequence of prompts: first extract and confirm the requirements, review them, then request scoring against the corrected requirements, then request the memo.
- C. Asking Claude to write the memo first, then work backward to justify it with scores.
- D. Submitting the three proposals in three parallel chats and combining whichever outputs look best.

**Q3.** An analyst asks Claude to assess a 40-page market report and gets a confident summary containing a statistic she cannot find in the report. Which TWO prompt changes most directly address this problem? (Select TWO.)

- A. Instruct Claude to quote the relevant passages verbatim, with locations, before stating conclusions.
- B. Explicitly permit Claude to say "the report does not address this" instead of inferring.
- C. Ask Claude to express more confidence so weak claims are filtered out.
- D. Shorten the prompt so Claude focuses better.
- E. Ask for the summary in a more formal register.

**Q4.** An associate's first draft prompt produced a report that was too technical for its executive audience. What is the most effective next step? (Select ONE.)

- A. Regenerate the response several times until a simpler version appears.
- B. Give targeted feedback specifying the audience and what to change — e.g., "Rewrite for executives with no technical background; keep the recommendations section as is."
- C. Start a new conversation with the identical prompt.
- D. Manually rewrite the whole report without changing the prompt, since prompts can't control tone.

**Q5.** A consultant is prompting Claude with a long client brief plus her instructions, examples, and a rubric, and Claude keeps confusing the client's text with her instructions. Which technique does Anthropic document for exactly this problem? (Select ONE.)

- A. Writing the entire prompt in capital letters for emphasis.
- B. Separating each kind of content with clearly named XML-style tags such as `<instructions>`, `<context>`, and `<input>`.
- C. Removing the examples, since examples always confuse the model.
- D. Splitting every sentence into its own message.

**Q6.** A team lead wants Claude to produce ticket summaries in the team's established house style, which is hard to describe in words. Which approach does official guidance most support? (Select ONE.)

- A. Provide 3–5 relevant, varied real examples of ticket-plus-ideal-summary pairs, wrapped in example tags, before the new ticket.
- B. Provide 25 examples so every possible case is covered.
- C. Describe the style using at least ten adjectives.
- D. Ask Claude to guess the style from the team's name.

**Q7.** An associate needs ideas for reducing meeting load across a department. Her prompt — "What's the best way to reduce meetings?" — returns one conventional recommendation. Which change best adapts her prompting strategy to a brainstorming task? (Select ONE.)

- A. Ask the same question again with "think harder" appended.
- B. Ask for a single, definitive answer with citations for each claim.
- C. Ask for 15 distinct ideas varying from low-effort to structural changes, with evaluation deferred to a follow-up step.
- D. Switch the request to a formal report format.

**Q8.** An associate is prompting Claude to answer questions about a lengthy uploaded policy document. According to Anthropic's long-context guidance, how should the prompt be arranged? (Select ONE.)

- A. Question first, then the document, so Claude knows what to look for.
- B. The document near the top of the prompt, with the question and instructions after it.
- C. The document split across many separate short messages.
- D. Only a paraphrase of the document, since full documents reduce quality.

### Answers

**Q1 — B.** Option B supplies task, audience, content focus, tone, length, and a call to action — the specificity and context that official guidance says drive quality. A adds urgency but no information; emphasis is not specification. C is regeneration without diagnosis: nothing about the prompt improved, so outputs stay generic. D adds a grandiose role but still specifies nothing about audience, content, or format; role prompting helps focus tone but cannot substitute for a defined task.

**Q2 — B.** Her stated need is to inspect and correct an intermediate result (the requirements) before it drives later steps — the documented reason to chain prompts with review between turns. A produces everything at once, so a requirements misreading silently poisons the scoring and memo. C reverses the logic: conclusions first, justification after, inviting motivated reasoning. D creates three inconsistent analyses with no requirements-correction point and no shared basis for comparison.

**Q3 — A and B.** Quote-grounding forces claims to be anchored in the actual text and makes them auditable; explicitly allowing "the report does not address this" removes the pressure to fabricate — both are techniques documented in Anthropic's hallucination-reduction guidance. C is counterproductive: self-expressed confidence is not an accuracy signal, and demanding confidence encourages assertiveness, not correctness. D removes context, which typically worsens accuracy. E changes tone, not truthfulness.

**Q4 — B.** Official guidance describes iteration as giving follow-up instructions, clarifications, or rewrite requests; naming the audience and scoping the change ("keep the recommendations section") is targeted, efficient feedback. A gambles on randomness without adding the missing information (the audience). C discards useful conversation context and repeats the same flawed prompt. D forfeits the tool's value and is false — audience and tone are among the most promptable attributes.

**Q5 — B.** Anthropic documents XML-style tags precisely for prompts that mix instructions, context, examples, and inputs: wrapping each content type in its own descriptive tag prevents Claude from misinterpreting one as another. A adds emphasis, not structure. C discards a documented, high-value technique; well-structured examples help rather than confuse. D destroys the coherence of the prompt without disambiguating anything.

**Q6 — A.** Official guidance identifies few-shot examples as one of the most reliable ways to steer format, tone, and structure, recommends 3–5 examples, and advises making them relevant, diverse, and wrapped in example tags. B exceeds documented guidance with diminishing returns and risks teaching accidental patterns. C is exactly the failure examples solve — hard-to-verbalize style is shown, not described. D provides no information at all.

**Q7 — C.** Brainstorming needs explicit volume, named dimensions of variation, and separation of generation from evaluation — otherwise the model converges on one safe answer, which is what happened. A adds effort language without changing the task's shape. B applies a research/verification strategy to a divergent task, further narrowing output. D changes packaging, not the generative behavior.

**Q8 — B.** Anthropic's long-context guidance is to place long documents near the top of the prompt with the query and instructions after them; in Anthropic's testing, putting the query at the end improved response quality on complex inputs. A is the intuitive but documented-suboptimal ordering. C fragments the document and loses coherence. D discards the source text, undermining accuracy and making claim verification impossible.

---

## Sources

Official Anthropic pages verified for this module (fetched July 2026):

- Prompt engineering overview — https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview (canonical: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview)
- Prompting best practices (clarity, context/motivation, examples, XML tags, roles, long context, chaining and self-correction, research guidance, formatting) — https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices
- Reduce hallucinations (allow "I don't know", quote grounding, citations, iterative refinement, chain-of-thought verification) — https://platform.claude.com/docs/en/test-and-evaluate/strengthen-guardrails/reduce-hallucinations
- Introduction to prompt design (Claude Help Center) — https://support.claude.com/en/articles/7996853-introduction-to-prompt-design
- My prompt isn't giving me a helpful answer (Claude Help Center: clarity, context, substeps, feedback) — https://support.claude.com/en/articles/7996857-my-prompt-isn-t-giving-me-a-helpful-answer

Exam structure, domain weighting, and candidate profile references: CCAO-F Exam Guide v1.0 (available from the Anthropic Partner Academy). Practice questions are original items in the style of the guide's Section 8 samples and are not drawn from any live item bank.
