---
title: "Mock Exam Answer Key"
nav_order: 11
---

# CCAO-F Mock Exam — Answer Key and Rationales

Companion to `mock-exam.md`. For each item: correct answer(s), domain, and a rationale in the style of the exam guide's Section 8 — why the credited response is right and why each distractor fails. Multiple-response items are scored all-or-nothing. A per-domain scoring worksheet follows the rationales.

**Domain legend**

- D1 — Prompting and Task Execution
- D2 — Output Evaluation and Validation
- D3 — Product and Model Selection
- D4 — Workflow Integration and Solution Design
- D5 — Configuration and Knowledge Management
- D6 — Governance, Risk, and Responsible Use
- D7 — Troubleshooting and Optimization

---

## Rationales

**1 — B · D2.** Asking "why is A right?" hands Claude a premise to argue, so the one-sided output reflects framing bias introduced by the prompt, not evidence about the decision; a neutral comparison including the case against Site A produces decision-grade analysis. (A) mistakes persuasiveness for correctness. (C) relies on self-reported confidence, which is not an accuracy signal. (D) polishes tone without touching the bias.

**2 — B · D3.** A single, current, factual question is the documented fit for web search — one or two lookups. Research (A) spends minutes and heavier usage on a one-lookup answer; extended thinking (C) adds reasoning depth but retrieves nothing current; last year's brochure (D) cannot contain this morning's change.

**3 — B · D6.** The trend analysis does not need identities, so minimizing the data — stripping or tokenizing names and IDs — lets the task proceed within policy ("anonymize, don't abandon"). (A) ignores the stated policy; internal purpose is not a defense. (C) treats a prompt instruction as a data-protection control, which it is not — handling is governed by account, settings, and agreements. (D) forfeits legitimate value a compliant path can deliver.

**4 — A · D1.** Anthropic's documented formatting guidance is to tell Claude what to do instead of what not to do — "write in smoothly flowing prose paragraphs" — and to match the prompt's own style to the desired output. Repetition (B) and capital letters (C) add emphasis, not specification, and prohibitions are the weaker control being replaced. Switching platforms (D) abandons a solvable prompt-level problem.

**5 — B · D4.** Strong Claude use cases are language-heavy information work; here the bottleneck is physical warehouse capacity, so AI targets the problem poorly and the honest analysis says so while keeping Claude on genuine language tasks like delay communications. (A) and (D) apply features to a non-language bottleneck; (C) misdiagnoses a use-case-fit problem as a model-capability problem.

**6 — A · D5.** Verified connector behavior: Gmail gives Claude email content and attachment *metadata*, not attachment content, so the file must be uploaded directly. (B) is false — Google Workspace connectors are broadly available. (C) is false — Claude reads spreadsheets supplied through supported routes. (D) is invented; authentication is not per-request.

**7 — B · D2.** Facts are correct but structure drifts across the batch — that is inconsistency (format drift), fixed by re-specifying the format and regenerating the drifted items, with smaller batches and spot-checks going forward. (A) misuses "hallucination": nothing was fabricated. (C) involves no skewed framing of people or perspectives. (D) is wrong because no items are missing — they are present but off-template.

**8 — B · D7.** No rewording makes a model know post-cutoff events from training data alone; the fix is recognizing the knowledge boundary and supplying current information (web search or pasted sources). (A) and (C) keep pulling the wrong lever. (D) is self-certification, which is never a validation step.

**9 — B · D4.** Honest measurement reports what improved and what did not, quantifies the net effect, and plans the fix — that is what earns stakeholder trust. (A) is spin that will surface later as a credibility failure. (C) overcorrects: a net-positive pilot with a known cost is not a failure. (D) deletes an accountability control to flatter the metrics.

**10 — B · D6.** Data handling is governed by account type, settings, and agreements — not by chat text — and the policy restriction applies to the act of uploading regardless of what the prompt says. (A) and (C) treat prompt wording as a control. (D) fails for the same reason: project instructions are behavioral guidance for Claude, not a data-protection mechanism.

**11 — A · D1.** Numbered sequential steps that force evidence-gathering (themes with counts, verbatim quotes) before conclusions produce recommendations grounded in the data — the documented decomposition pattern. (B) reverses the logic and invites motivated reasoning. (C) adds untestable adjectives, not structure. (D) is regeneration without diagnosis.

**12 — B · D3.** On Enterprise plans, administrators can restrict which models and effort levels are available to a role, so a "missing" model is most likely a policy, not a bug — the right move is to ask the admin. (A) misdiagnoses configuration as corruption. (C) contradicts the friend still using the model. (D) inverts how enterprise controls work: it's restriction by policy, not a smaller entitlement by definition.

**13 — B · D2.** Deadlines and fee amounts are time-sensitive, verifiable specifics that may post-date training data; the currency check against a live authoritative source is required before the memo ships. (A) mistakes specificity for evidence — fabricated detail looks specific. (C) is model self-certification. (D) uses a disclaimer as a substitute for verification, which manages blame, not accuracy.

**14 — C · D5.** On paid plans, Claude automatically switches project knowledge into RAG mode as it approaches context limits, loading only relevant content and expanding effective capacity — no manual toggle exists (A), uploads don't simply stop (B), and knowledge is not truncated oldest-first (D). Pruning still matters for focus, which the credited option acknowledges.

**15 — B · D4.** The scenario stacks every redesign-favoring factor: structural process problems, successful pilots as an evidence base, and sponsored change capacity — so "redesign from evidence" is the documented next step. (A) ignores that the conditions for redesign have been met. (C) abandons a needed process. (D) removes human accountability, which no efficiency gain justifies.

**16 — B · D7.** Changing one variable at a time is the diagnostic discipline that lets you attribute improvements and make the fix repeatable; wholesale rewrites destroy attribution. (A) throws capability at an unmeasured problem. (C) confuses volume with precision. (D) asks the model to evaluate prompts it cannot compare against her actual success criteria.

**17 — B · D6.** Insurance is a named high-risk domain: Anthropic's Usage Policy requires human-in-the-loop review by a qualified professional and disclosure to consumers that AI helped produce the recommendation. (A) and (D) are irrelevant to the policy. (C) is wrong — consumer-facing insurance recommendations are precisely the high-risk case the requirements target.

**18 — A and C · D2.** Contract language carries legal consequences beyond what output-level checks validate (A), and a recommendation in a domain where the associate cannot tell right from plausible adds no value from self-review — the definition of needing an expert (C). (B), (D), and (E) are low-stakes or already-verified content where the associate's own proportionate review suffices.

**19 — A · D1.** This is the documented "golden rule of clear prompting": show the prompt to a colleague with minimal context; the gaps they hit are the gaps Claude will hit. (B) tests output length, not clarity. (C) adds urgency, not information. (D) invents a metric — precision, not word count, is the goal.

**20 — A and C · D3.** Research is positioned for comprehensive, multi-source synthesis with citations (A) and can draw on connected internal context alongside the web (C). (B) is the web-search profile. (D) is the extended-thinking profile. (E) argues against Research, which consumes usage limits faster than normal chat.

**21 — B · D4.** A solution is durable when it survives its designer: proven prompts moved into shared project instructions, curated knowledge, and a usage note naming purpose, limits, and the review step. (A) leaves knowledge trapped in one person's chat history. (C) makes the workflow dependent on the departed person. (D) misuses memory — it is personal, inferred context, not team infrastructure.

**22 — A and B · D5.** Project instructions and project knowledge are exactly the two surfaces applied across every chat in a project. (C) and (E) fail because Claude has no access to the project name or description — they are metadata for humans. (D) fails because context is not shared between chats in a project; each chat starts fresh apart from instructions and knowledge.

**23 — B · D2.** Material inconsistency across runs of the same prompt is a documented hallucination warning: the figure needs verification against an external authoritative source. (A) averages contradictions into a manufactured number. (C) invents a reliability rule. (D) is still self-referential — a majority of model runs can be consistently wrong; repetition signals stability, not truth.

**24 — B · D6.** Submitting feedback can store the entire related conversation with Anthropic for an extended retention period, so conversations containing sensitive data should not be rated, and org settings (admins can disable feedback) should be followed. (A) and (D) misstate how feedback data is handled. (C) is invented — feedback stores data; it does not delete it.

**25 — A · D7.** Recurring similar small items are the documented batching case: one clear instruction set, a specified structure, batch sizes small enough to hold quality, and spot-checks. (B) over-provisions model capability without fixing the repeated-setup waste. (C) is task overload — the composite-prompt trap. (D) buys throughput by discarding the quality control.

**26 — B · D1.** Anthropic's guidance makes success criteria the precondition for iteration: without a definition of "better," you can only regenerate and gamble. (A) and (C) change inputs without creating a measuring stick. (D) is a real anti-hallucination technique but irrelevant to the stated problem, which is evaluating improvement.

**27 — A · D4.** The exam-rewarded decomposition keeps Claude on language and information work (extract, summarize, flag) and keeps decision authority with humans. (B) and (D) remove the human from an approval decision — exactly the step that requires human accountability. (C) over-refuses: the sub-steps are excellent Claude use cases with review.

**28 — B · D2.** Output feeding a system for sorting and filtering calls for structured data; a fixed schema also makes omissions immediately visible, doing double duty for evaluation. (A) and (D) deliver prose to a tool that needs fields. (C) picks a delivery window, not a data structure — a formatted memo still can't be sorted.

**29 — A · D3.** Incognito chats are excluded from memory and past-chat search — the designed mechanism for a sensitive one-off. (B) does not work; in-chat requests to "forget" are not a data or memory control. (C) makes the conversation *more* persistent, inside a project with its own memory space. (D) is concealment, not exclusion.

**30 — A and B · D6.** Tracking a person's private whereabouts and activity without consent is prohibited surveillance/privacy violation (A), and mass-generating fake grassroots comments to manipulate a poll is deceptive, scaled abuse that also undermines civic processes (B). (C), (D), and (E) are routine, appropriate business uses.

**31 — B · D5.** Verified behavior: archiving a project resets all sharing permissions to private for security, so after unarchiving the owner must deliberately re-share. (A) invents corruption. (C) is false — archived projects persist (and cannot be deleted until unarchived). (D) confuses project permissions with account status.

**32 — A, B, and C · D2.** The validation workflow for compliance-bound content is: completeness against the request, internal consistency of claims, and external verification of load-bearing facts against the authoritative text. (D) is self-reported confidence, which the official sample rationale explicitly rejects as an accuracy signal. (E) is a disclaimer — it labels risk instead of checking anything.

**33 — B · D4.** The credited answer is the Value–Limits–Controls pattern: measured pilot value, a plainly stated limitation, and the control that makes it manageable — review is what lets the speed gain be captured safely. (A) concedes a false premise. (C) offers to remove a needed control to please the stakeholder. (D) demands blind trust, the opposite of honest stakeholder communication.

**34 — B · D1.** Flipping to a critique mode via role framing — a skeptical CFO attacking costs, risks, and objections — is the documented way to stress-test a brainstormed shortlist after generation. (A) asks for preference, not scrutiny. (C) diverges again when the task now needs evaluation. (D) leans on self-assigned scores, which measure assertiveness, not merit.

**35 — B · D7.** Official guidance for cut-off responses: supply the previous prompt and partial response so Claude can continue where it left off, and request inherently large deliverables in sections. (A) is a blind retry. (C) removes context the plan may depend on. (D) abandons a task with a documented, routine fix.

**36 — A · D3.** "Start most capable, optimize down" is one of Anthropic's two documented starting strategies, and it fits when accuracy outweighs cost — the model establishes a quality ceiling, then evidence from testing justifies any step down. (B) skips evaluation in the risky direction for a high-stakes task. (C) is irrelevant to fit. (D) refuses the test-and-compare practice guidance calls for.

**37 — B · D2.** Adapting for a customer audience means confirmed facts in plain language — internal codenames removed, and the unconfirmed root-cause hypothesis excluded, since publishing speculation externally is a factual and legal risk. (A) confuses transparency with publishing unverified claims. (C) ignores that audiences legitimately need different outputs from the same validated facts. (D) makes the notice unverifiable, which is a defect, not a safeguard.

**38 — B · D6.** The verified contrast: commercial products do not train on customer inputs/outputs by default, while consumer plans may unless the user opts out, with exceptions such as explicitly reported (feedback) content. (A) and (C) are the two absolutist errors this fact corrects. (D) inverts the actual split, which is consumer/commercial, not free/paid.

**39 — A and B · D4.** Sound change management pilots small with a defined success measure (A) and names accountable reviewers and outcome owners (B). (C) skips the evidence-building step. (D) removes the control that makes the workflow trustworthy. (E) guarantees the process dies with staff turnover — documentation is part of integration.

**40 — B · D5.** Instructions steer behavior; knowledge supplies reference material. Moving the style guide into project knowledge and keeping short, behavioral instructions that reference the file by name is the documented structure. (A) doubles the bloat. (C) fails because Claude cannot see the project description. (D) reintroduces the re-pasting problem Projects exist to solve.

**41 — B · D2.** Verification must be proportionate to stakes: brainstorms get light review; external, decision-bearing content gets the full workflow. This associate has the priorities inverted. (A) misreads a judgment problem as a speed problem. (C) rejects triage, which is the tested skill. (D) overcorrects — even ideation deserves a sanity pass.

**42 — B · D1.** Anthropic's guidance says examples must be relevant *and diverse*, covering edge cases so Claude doesn't learn unintended patterns — four same-type examples taught "everything is a refund." (A) misstates the guidance, which recommends 3–5 examples. (C) discards one of the most reliable steering techniques. (D) substitutes adjectives for the demonstration that examples provide.

**43 — B · D3.** Deep reasoning over material already provided, with no fresh information needed, is the documented extended-thinking (or higher-effort) profile. (A) and (C) add retrieval the task doesn't need. (D) misunderstands incognito — it affects memory and history, not reasoning quality.

**44 — B · D6.** Accountability stays with the human and organization that used the output; "Claude wrote it" never transfers responsibility, which is exactly why human review requirements exist. (A) mislocates responsibility in the vendor. (C) normalizes unreviewed errors. (D) shifts the sender's duty onto the recipient.

**45 — B · D4.** Claude's process analysis is a hypothesis generated from documents; the people who run the process validate it against operational reality before anything changes. (A) is the classic wrong answer — docs and reality diverge. (C) is model self-review, not validation. (D) over-refuses; the proposal is valuable input once verified.

**46 — B · D2.** Citations make verification easier; they are not verification. The associate must read the cited sources because synthesis can drop the context that made a claim accurate, and the output is only as good as its sources — especially for a public marketing claim. (A) and (D) treat citation presence or count as proof. (C) is self-certification.

**47 — B · D7.** Contradictory instructions are a documented cause of ignored-instruction failures; the fix is consolidating to one clear, conflict-free prompt with the surviving constraints stated prominently. (A) adds emphasis without resolving the contradiction — both instructions cannot be followed. (C) gambles on randomness. (D) splits one deliverable across contexts, guaranteeing neither chat sees the full requirement.

**48 — B · D5.** Memory is automatic and inferred — useful, but not a compliance mechanism; hard requirements belong explicitly in project instructions, which apply to every chat in the project. (A) overstates memory's reliability for must-follow rules. (C) fails because Claude has no access to the project title. (D) understates the platform — persistent instructions exist for exactly this.

**49 — B · D2.** A good escalation package — output, prompt and sources, what was verified and how, what couldn't be verified, and the specific question — respects the expert's time and demonstrates associate-level judgment. (A) and (C) transfer raw material without analysis, forcing legal to reconstruct the work. (D) wastes the verification already done; context is help, not contamination.

**50 — B · D6.** Coordinated fake engagement is scaled abuse and deception prohibited by the Usage Policy; the credited pattern declines the prohibited task while offering a compliant route to the underlying goal. (A) normalizes a prohibited practice. (C) adds policy evasion on top of the violation — the account doesn't change what the activity is. (D) makes the violation smaller, not permissible.

**51 — A and B · D1.** Two documented techniques fit: XML-style tags disambiguate content types so document text can't be mistaken for instructions (A), and long-context guidance places the document near the top with the query after it, which measurably improves quality on complex inputs (B). (C) adds emphasis, not structure. (D) fragments the document. (E) deletes required content instead of organizing it.

**52 — B · D4.** Contractual uptime and throughput guarantees on unattended, high-volume automation are the textbook signals that work has left Associate chat-workflow scope; the credited move is documenting requirements and handing off to engineering or Architect/Developer expertise. (A) promises what a chat-based workflow cannot deliver. (C) over-refuses a client with a legitimate need. (D) fakes a guarantee with a manual check.

**53 — B · D3.** Automatic context management summarizes earlier messages so most long conversations can continue — but it has documented edge cases, so restart/summarize/persist judgment remains the associate's job. (A) and (D) overstate the mechanism (and model family is irrelevant to it). (C) denies a real, documented feature.

**54 — B · D2.** Format selection follows the content: inline for short answers consumed in-conversation; artifacts for significant, self-contained, reusable content. Blanket artifact policy adds friction without value. (A) and (C) impose ceremony where none is needed. (D) swings to the opposite error — documents, diagrams, and reports are legitimate artifact content, not just code.

**55 — B · D6.** This is the proportionality/human-impact dimension of responsible use: policy permission is the floor, and consequential people-affecting communications warrant genuine human authorship and ownership, with Claude assisting rather than replacing the human. (A) treats compliance as the whole analysis. (C) reduces an ethical question to tone. (D) adds impersonation — presenting AI output under a fictitious human identity — to the original problem.

**56 — B · D5.** Superseded versions must be removed: outdated knowledge is worse than missing knowledge because Claude will confidently use it. (A) and (C) leave the contradiction in place and hope retrieval favors the right file. (D) shifts a configuration fix onto every user in every chat, which is exactly what knowledge maintenance exists to prevent.

**57 — A and B · D7.** Official guidance is explicit that not every problem is best solved by prompt engineering: after well-diagnosed revisions fail, the levers are feature fit (A) and model selection matched to quality/speed/cost (B). (C) iterates indefinitely on the wrong lever. (D) is product feedback, not a resolution step. (E) is brute-force repetition with no diagnosis.

**58 — B · D4.** AI-powered artifacts can be published and shared, with each user authenticating with their own Claude account and usage counting against their own subscription — the verified mechanism for exactly this need. (A) and (C) share a picture or code, not a working tool. (D) makes the associate the bottleneck the tool was built to remove.

**59 — B · D2.** Curation is an evaluation act: cut what doesn't serve the decision, order by importance, keep citations attached to the facts they support, and put caveats beside the claims they qualify. (A) transfers the filtering burden to the director. (C) strips the apparatus the next reviewer needs to re-verify. (D) treats raw conversation as a deliverable, which loses structure, curation, and verifiability.

**60 — B · D1.** The documented self-correction chaining pattern is generate → review against explicit criteria → refine; it turns the checklist into an enforceable step. (A) hopes one pass plus an adjective clears the bar. (C) selects by length, which is not a quality criterion. (D) gates publication on self-reported scoring, which is not an accuracy or quality signal.

---

## Score by domain worksheet

The real exam's score report shows percent-correct by domain. Recreate that here: mark each item right or wrong, then compute per-domain percentages. All-or-nothing scoring on multiple-response items (18, 20, 22, 30, 32, 39, 51, 57).

| Domain | Items | # Correct | / Total | % |
|---|---|---|---|---|
| D1 — Prompting and Task Execution | 4, 11, 19, 26, 34, 42, 51, 60 | ____ | / 8 | ____ |
| D2 — Output Evaluation and Validation | 1, 7, 13, 18, 23, 28, 32, 37, 41, 46, 49, 54, 59 | ____ | / 13 | ____ |
| D3 — Product and Model Selection | 2, 12, 20, 29, 36, 43, 53 | ____ | / 7 | ____ |
| D4 — Workflow Integration and Solution Design | 5, 9, 15, 21, 27, 33, 39, 45, 52, 58 | ____ | / 10 | ____ |
| D5 — Configuration and Knowledge Management | 6, 14, 22, 31, 40, 48, 56 | ____ | / 7 | ____ |
| D6 — Governance, Risk, and Responsible Use | 3, 10, 17, 24, 30, 38, 44, 50, 55 | ____ | / 9 | ____ |
| D7 — Troubleshooting and Optimization | 8, 16, 25, 35, 47, 57 | ____ | / 6 | ____ |
| **Total** | 1–60 | ____ | / 60 | ____ |

**Interpreting your result.** The real exam reports a scaled score (100–1,000, cut score 720), which is not a raw percentage — treat your raw score here only as a rough readiness indicator. A practical heuristic: aim for roughly 75–80%+ overall under timed, closed-book conditions, with no domain far below the others. Any domain under ~65% is a signal to restudy the matching module (Modules 1–7) before scheduling.

*Original practice material written in the style of the CCAO-F Exam Guide's Section 8 samples. Not actual exam content; not drawn from any live item bank.*
