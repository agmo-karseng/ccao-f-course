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

**1 — Correct: B · Domain 2**

- **Why B:** Asking "why is A right?" hands Claude a premise to argue, so the one-sided output reflects framing bias introduced by the prompt, not evidence about the decision; a neutral comparison including the case against Site A produces decision-grade analysis.
- **Why not A:** Mistakes persuasiveness for correctness.
- **Why not C:** Relies on self-reported confidence, which is not an accuracy signal.
- **Why not D:** Polishes tone without touching the bias.

**2 — Correct: B · Domain 3**

- **Why B:** A single, current, factual question is the documented fit for web search — one or two lookups.
- **Why not A:** Research spends minutes and heavier usage on a one-lookup answer.
- **Why not C:** Extended thinking adds reasoning depth but retrieves nothing current.
- **Why not D:** Last year's brochure cannot contain this morning's change.

**3 — Correct: B · Domain 6**

- **Why B:** The trend analysis does not need identities, so minimizing the data — stripping or tokenizing names and IDs — lets the task proceed within policy ("anonymize, don't abandon").
- **Why not A:** Ignores the stated policy; internal purpose is not a defense.
- **Why not C:** Treats a prompt instruction as a data-protection control, which it is not — handling is governed by account, settings, and agreements.
- **Why not D:** Forfeits legitimate value a compliant path can deliver.

**4 — Correct: A · Domain 1**

- **Why A:** Anthropic's documented formatting guidance is to tell Claude what to do instead of what not to do — "write in smoothly flowing prose paragraphs" — and to match the prompt's own style to the desired output.
- **Why not B/C:** Repetition (B) and capital letters (C) add emphasis, not specification, and prohibitions are the weaker control being replaced.
- **Why not D:** Switching platforms abandons a solvable prompt-level problem.

**5 — Correct: B · Domain 4**

- **Why B:** Strong Claude use cases are language-heavy information work; here the bottleneck is physical warehouse capacity, so AI targets the problem poorly and the honest analysis says so while keeping Claude on genuine language tasks like delay communications.
- **Why not A/D:** Apply features to a non-language bottleneck.
- **Why not C:** Misdiagnoses a use-case-fit problem as a model-capability problem.

**6 — Correct: A · Domain 5**

- **Why A:** Verified connector behavior: Gmail gives Claude email content and attachment *metadata*, not attachment content, so the file must be uploaded directly.
- **Why not B:** False — Google Workspace connectors are broadly available.
- **Why not C:** False — Claude reads spreadsheets supplied through supported routes.
- **Why not D:** Invented; authentication is not per-request.

**7 — Correct: B · Domain 2**

- **Why B:** Facts are correct but structure drifts across the batch — that is inconsistency (format drift), fixed by re-specifying the format and regenerating the drifted items, with smaller batches and spot-checks going forward.
- **Why not A:** Misuses "hallucination": nothing was fabricated.
- **Why not C:** The scenario involves no skewed framing of people or perspectives.
- **Why not D:** Wrong because no items are missing — they are present but off-template.

**8 — Correct: B · Domain 7**

- **Why B:** No rewording makes a model know post-cutoff events from training data alone; the fix is recognizing the knowledge boundary and supplying current information (web search or pasted sources).
- **Why not A/C:** Keep pulling the wrong lever.
- **Why not D:** Self-certification, which is never a validation step.

**9 — Correct: B · Domain 4**

- **Why B:** Honest measurement reports what improved and what did not, quantifies the net effect, and plans the fix — that is what earns stakeholder trust.
- **Why not A:** Spin that will surface later as a credibility failure.
- **Why not C:** Overcorrects: a net-positive pilot with a known cost is not a failure.
- **Why not D:** Deletes an accountability control to flatter the metrics.

**10 — Correct: B · Domain 6**

- **Why B:** Data handling is governed by account type, settings, and agreements — not by chat text — and the policy restriction applies to the act of uploading regardless of what the prompt says.
- **Why not A/C:** Treat prompt wording as a control.
- **Why not D:** Fails for the same reason: project instructions are behavioral guidance for Claude, not a data-protection mechanism.

**11 — Correct: A · Domain 1**

- **Why A:** Numbered sequential steps that force evidence-gathering (themes with counts, verbatim quotes) before conclusions produce recommendations grounded in the data — the documented decomposition pattern.
- **Why not B:** Reverses the logic and invites motivated reasoning.
- **Why not C:** Adds untestable adjectives, not structure.
- **Why not D:** Regeneration without diagnosis.

**12 — Correct: B · Domain 3**

- **Why B:** On Enterprise plans, administrators can restrict which models and effort levels are available to a role, so a "missing" model is most likely a policy, not a bug — the right move is to ask the admin.
- **Why not A:** Misdiagnoses configuration as corruption.
- **Why not C:** Contradicts the friend still using the model.
- **Why not D:** Inverts how enterprise controls work: it's restriction by policy, not a smaller entitlement by definition.

**13 — Correct: B · Domain 2**

- **Why B:** Deadlines and fee amounts are time-sensitive, verifiable specifics that may post-date training data; the currency check against a live authoritative source is required before the memo ships.
- **Why not A:** Mistakes specificity for evidence — fabricated detail looks specific.
- **Why not C:** Model self-certification.
- **Why not D:** Uses a disclaimer as a substitute for verification, which manages blame, not accuracy.

**14 — Correct: C · Domain 5**

- **Why C:** On paid plans, Claude automatically switches project knowledge into RAG mode as it approaches context limits, loading only relevant content and expanding effective capacity. Pruning still matters for focus, which the credited option acknowledges.
- **Why not A:** No manual toggle exists.
- **Why not B:** Uploads don't simply stop.
- **Why not D:** Knowledge is not truncated oldest-first.

**15 — Correct: B · Domain 4**

- **Why B:** The scenario stacks every redesign-favoring factor: structural process problems, successful pilots as an evidence base, and sponsored change capacity — so "redesign from evidence" is the documented next step.
- **Why not A:** Ignores that the conditions for redesign have been met.
- **Why not C:** Abandons a needed process.
- **Why not D:** Removes human accountability, which no efficiency gain justifies.

**16 — Correct: B · Domain 7**

- **Why B:** Changing one variable at a time is the diagnostic discipline that lets you attribute improvements and make the fix repeatable; wholesale rewrites destroy attribution.
- **Why not A:** Throws capability at an unmeasured problem.
- **Why not C:** Confuses volume with precision.
- **Why not D:** Asks the model to evaluate prompts it cannot compare against her actual success criteria.

**17 — Correct: B · Domain 6**

- **Why B:** Insurance is a named high-risk domain: Anthropic's Usage Policy requires human-in-the-loop review by a qualified professional and disclosure to consumers that AI helped produce the recommendation.
- **Why not A/D:** Irrelevant to the policy.
- **Why not C:** Wrong — consumer-facing insurance recommendations are precisely the high-risk case the requirements target.

**18 — Correct: A and C · Domain 2**

- **Why A:** Contract language carries legal consequences beyond what output-level checks validate.
- **Why C:** A recommendation in a domain where the associate cannot tell right from plausible adds no value from self-review — the definition of needing an expert.
- **Why not B/D/E:** Low-stakes or already-verified content where the associate's own proportionate review suffices.

**19 — Correct: A · Domain 1**

- **Why A:** This is the documented "golden rule of clear prompting": show the prompt to a colleague with minimal context; the gaps they hit are the gaps Claude will hit.
- **Why not B:** Tests output length, not clarity.
- **Why not C:** Adds urgency, not information.
- **Why not D:** Invents a metric — precision, not word count, is the goal.

**20 — Correct: A and C · Domain 3**

- **Why A:** Research is positioned for comprehensive, multi-source synthesis with citations.
- **Why C:** Research can draw on connected internal context alongside the web.
- **Why not B:** That is the web-search profile.
- **Why not D:** That is the extended-thinking profile.
- **Why not E:** Argues against Research, which consumes usage limits faster than normal chat.

**21 — Correct: B · Domain 4**

- **Why B:** A solution is durable when it survives its designer: proven prompts moved into shared project instructions, curated knowledge, and a usage note naming purpose, limits, and the review step.
- **Why not A:** Leaves knowledge trapped in one person's chat history.
- **Why not C:** Makes the workflow dependent on the departed person.
- **Why not D:** Misuses memory — it is personal, inferred context, not team infrastructure.

**22 — Correct: A and B · Domain 5**

- **Why A and B:** Project instructions and project knowledge are exactly the two surfaces applied across every chat in a project.
- **Why not C/E:** Fail because Claude has no access to the project name or description — they are metadata for humans.
- **Why not D:** Fails because context is not shared between chats in a project; each chat starts fresh apart from instructions and knowledge.

**23 — Correct: B · Domain 2**

- **Why B:** Material inconsistency across runs of the same prompt is a documented hallucination warning: the figure needs verification against an external authoritative source.
- **Why not A:** Averages contradictions into a manufactured number.
- **Why not C:** Invents a reliability rule.
- **Why not D:** Still self-referential — a majority of model runs can be consistently wrong; repetition signals stability, not truth.

**24 — Correct: B · Domain 6**

- **Why B:** Submitting feedback can store the entire related conversation with Anthropic for an extended retention period, so conversations containing sensitive data should not be rated, and org settings (admins can disable feedback) should be followed.
- **Why not A/D:** Misstate how feedback data is handled.
- **Why not C:** Invented — feedback stores data; it does not delete it.

**25 — Correct: A · Domain 7**

- **Why A:** Recurring similar small items are the documented batching case: one clear instruction set, a specified structure, batch sizes small enough to hold quality, and spot-checks.
- **Why not B:** Over-provisions model capability without fixing the repeated-setup waste.
- **Why not C:** Task overload — the composite-prompt trap.
- **Why not D:** Buys throughput by discarding the quality control.

**26 — Correct: B · Domain 1**

- **Why B:** Anthropic's guidance makes success criteria the precondition for iteration: without a definition of "better," you can only regenerate and gamble.
- **Why not A/C:** Change inputs without creating a measuring stick.
- **Why not D:** A real anti-hallucination technique but irrelevant to the stated problem, which is evaluating improvement.

**27 — Correct: A · Domain 4**

- **Why A:** The exam-rewarded decomposition keeps Claude on language and information work (extract, summarize, flag) and keeps decision authority with humans.
- **Why not B/D:** Remove the human from an approval decision — exactly the step that requires human accountability.
- **Why not C:** Over-refuses: the sub-steps are excellent Claude use cases with review.

**28 — Correct: B · Domain 2**

- **Why B:** Output feeding a system for sorting and filtering calls for structured data; a fixed schema also makes omissions immediately visible, doing double duty for evaluation.
- **Why not A/D:** Deliver prose to a tool that needs fields.
- **Why not C:** Picks a delivery window, not a data structure — a formatted memo still can't be sorted.

**29 — Correct: A · Domain 3**

- **Why A:** Incognito chats are excluded from memory and past-chat search — the designed mechanism for a sensitive one-off.
- **Why not B:** Does not work; in-chat requests to "forget" are not a data or memory control.
- **Why not C:** Makes the conversation *more* persistent, inside a project with its own memory space.
- **Why not D:** Concealment, not exclusion.

**30 — Correct: A and B · Domain 6**

- **Why A:** Tracking a person's private whereabouts and activity without consent is prohibited surveillance/privacy violation.
- **Why B:** Mass-generating fake grassroots comments to manipulate a poll is deceptive, scaled abuse that also undermines civic processes.
- **Why not C/D/E:** Routine, appropriate business uses.

**31 — Correct: B · Domain 5**

- **Why B:** Verified behavior: archiving a project resets all sharing permissions to private for security, so after unarchiving the owner must deliberately re-share.
- **Why not A:** Invents corruption.
- **Why not C:** False — archived projects persist (and cannot be deleted until unarchived).
- **Why not D:** Confuses project permissions with account status.

**32 — Correct: A, B, and C · Domain 2**

- **Why A, B, and C:** The validation workflow for compliance-bound content is: completeness against the request, internal consistency of claims, and external verification of load-bearing facts against the authoritative text.
- **Why not D:** Self-reported confidence, which the official sample rationale explicitly rejects as an accuracy signal.
- **Why not E:** A disclaimer — it labels risk instead of checking anything.

**33 — Correct: B · Domain 4**

- **Why B:** The credited answer is the Value–Limits–Controls pattern: measured pilot value, a plainly stated limitation, and the control that makes it manageable — review is what lets the speed gain be captured safely.
- **Why not A:** Concedes a false premise.
- **Why not C:** Offers to remove a needed control to please the stakeholder.
- **Why not D:** Demands blind trust, the opposite of honest stakeholder communication.

**34 — Correct: B · Domain 1**

- **Why B:** Flipping to a critique mode via role framing — a skeptical CFO attacking costs, risks, and objections — is the documented way to stress-test a brainstormed shortlist after generation.
- **Why not A:** Asks for preference, not scrutiny.
- **Why not C:** Diverges again when the task now needs evaluation.
- **Why not D:** Leans on self-assigned scores, which measure assertiveness, not merit.

**35 — Correct: B · Domain 7**

- **Why B:** Official guidance for cut-off responses: supply the previous prompt and partial response so Claude can continue where it left off, and request inherently large deliverables in sections.
- **Why not A:** A blind retry.
- **Why not C:** Removes context the plan may depend on.
- **Why not D:** Abandons a task with a documented, routine fix.

**36 — Correct: A · Domain 3**

- **Why A:** "Start most capable, optimize down" is one of Anthropic's two documented starting strategies, and it fits when accuracy outweighs cost — the model establishes a quality ceiling, then evidence from testing justifies any step down.
- **Why not B:** Skips evaluation in the risky direction for a high-stakes task.
- **Why not C:** Irrelevant to fit.
- **Why not D:** Refuses the test-and-compare practice guidance calls for.

**37 — Correct: B · Domain 2**

- **Why B:** Adapting for a customer audience means confirmed facts in plain language — internal codenames removed, and the unconfirmed root-cause hypothesis excluded, since publishing speculation externally is a factual and legal risk.
- **Why not A:** Confuses transparency with publishing unverified claims.
- **Why not C:** Ignores that audiences legitimately need different outputs from the same validated facts.
- **Why not D:** Makes the notice unverifiable, which is a defect, not a safeguard.

**38 — Correct: B · Domain 6**

- **Why B:** The verified contrast: commercial products do not train on customer inputs/outputs by default, while consumer plans may unless the user opts out, with exceptions such as explicitly reported (feedback) content.
- **Why not A/C:** The two absolutist errors this fact corrects.
- **Why not D:** Inverts the actual split, which is consumer/commercial, not free/paid.

**39 — Correct: A and B · Domain 4**

- **Why A:** Sound change management pilots small with a defined success measure.
- **Why B:** Sound change management names accountable reviewers and outcome owners.
- **Why not C:** Skips the evidence-building step.
- **Why not D:** Removes the control that makes the workflow trustworthy.
- **Why not E:** Guarantees the process dies with staff turnover — documentation is part of integration.

**40 — Correct: B · Domain 5**

- **Why B:** Instructions steer behavior; knowledge supplies reference material. Moving the style guide into project knowledge and keeping short, behavioral instructions that reference the file by name is the documented structure.
- **Why not A:** Doubles the bloat.
- **Why not C:** Fails because Claude cannot see the project description.
- **Why not D:** Reintroduces the re-pasting problem Projects exist to solve.

**41 — Correct: B · Domain 2**

- **Why B:** Verification must be proportionate to stakes: brainstorms get light review; external, decision-bearing content gets the full workflow. This associate has the priorities inverted.
- **Why not A:** Misreads a judgment problem as a speed problem.
- **Why not C:** Rejects triage, which is the tested skill.
- **Why not D:** Overcorrects — even ideation deserves a sanity pass.

**42 — Correct: B · Domain 1**

- **Why B:** Anthropic's guidance says examples must be relevant *and diverse*, covering edge cases so Claude doesn't learn unintended patterns — four same-type examples taught "everything is a refund."
- **Why not A:** Misstates the guidance, which recommends 3–5 examples.
- **Why not C:** Discards one of the most reliable steering techniques.
- **Why not D:** Substitutes adjectives for the demonstration that examples provide.

**43 — Correct: B · Domain 3**

- **Why B:** Deep reasoning over material already provided, with no fresh information needed, is the documented extended-thinking (or higher-effort) profile.
- **Why not A/C:** Add retrieval the task doesn't need.
- **Why not D:** Misunderstands incognito — it affects memory and history, not reasoning quality.

**44 — Correct: B · Domain 6**

- **Why B:** Accountability stays with the human and organization that used the output; "Claude wrote it" never transfers responsibility, which is exactly why human review requirements exist.
- **Why not A:** Mislocates responsibility in the vendor.
- **Why not C:** Normalizes unreviewed errors.
- **Why not D:** Shifts the sender's duty onto the recipient.

**45 — Correct: B · Domain 4**

- **Why B:** Claude's process analysis is a hypothesis generated from documents; the people who run the process validate it against operational reality before anything changes.
- **Why not A:** The classic wrong answer — docs and reality diverge.
- **Why not C:** Model self-review, not validation.
- **Why not D:** Over-refuses; the proposal is valuable input once verified.

**46 — Correct: B · Domain 2**

- **Why B:** Citations make verification easier; they are not verification. The associate must read the cited sources because synthesis can drop the context that made a claim accurate, and the output is only as good as its sources — especially for a public marketing claim.
- **Why not A/D:** Treat citation presence or count as proof.
- **Why not C:** Self-certification.

**47 — Correct: B · Domain 7**

- **Why B:** Contradictory instructions are a documented cause of ignored-instruction failures; the fix is consolidating to one clear, conflict-free prompt with the surviving constraints stated prominently.
- **Why not A:** Adds emphasis without resolving the contradiction — both instructions cannot be followed.
- **Why not C:** Gambles on randomness.
- **Why not D:** Splits one deliverable across contexts, guaranteeing neither chat sees the full requirement.

**48 — Correct: B · Domain 5**

- **Why B:** Memory is automatic and inferred — useful, but not a compliance mechanism; hard requirements belong explicitly in project instructions, which apply to every chat in the project.
- **Why not A:** Overstates memory's reliability for must-follow rules.
- **Why not C:** Fails because Claude has no access to the project title.
- **Why not D:** Understates the platform — persistent instructions exist for exactly this.

**49 — Correct: B · Domain 2**

- **Why B:** A good escalation package — output, prompt and sources, what was verified and how, what couldn't be verified, and the specific question — respects the expert's time and demonstrates associate-level judgment.
- **Why not A/C:** Transfer raw material without analysis, forcing legal to reconstruct the work.
- **Why not D:** Wastes the verification already done; context is help, not contamination.

**50 — Correct: B · Domain 6**

- **Why B:** Coordinated fake engagement is scaled abuse and deception prohibited by the Usage Policy; the credited pattern declines the prohibited task while offering a compliant route to the underlying goal.
- **Why not A:** Normalizes a prohibited practice.
- **Why not C:** Adds policy evasion on top of the violation — the account doesn't change what the activity is.
- **Why not D:** Makes the violation smaller, not permissible.

**51 — Correct: A and B · Domain 1**

- **Why A and B:** Two documented techniques fit: XML-style tags disambiguate content types so document text can't be mistaken for instructions (A), and long-context guidance places the document near the top with the query after it, which measurably improves quality on complex inputs (B).
- **Why not C:** Adds emphasis, not structure.
- **Why not D:** Fragments the document.
- **Why not E:** Deletes required content instead of organizing it.

**52 — Correct: B · Domain 4**

- **Why B:** Contractual uptime and throughput guarantees on unattended, high-volume automation are the textbook signals that work has left Associate chat-workflow scope; the credited move is documenting requirements and handing off to engineering or Architect/Developer expertise.
- **Why not A:** Promises what a chat-based workflow cannot deliver.
- **Why not C:** Over-refuses a client with a legitimate need.
- **Why not D:** Fakes a guarantee with a manual check.

**53 — Correct: B · Domain 3**

- **Why B:** Automatic context management summarizes earlier messages so most long conversations can continue — but it has documented edge cases, so restart/summarize/persist judgment remains the associate's job.
- **Why not A/D:** Overstate the mechanism (and model family is irrelevant to it).
- **Why not C:** Denies a real, documented feature.

**54 — Correct: B · Domain 2**

- **Why B:** Format selection follows the content: inline for short answers consumed in-conversation; artifacts for significant, self-contained, reusable content. Blanket artifact policy adds friction without value.
- **Why not A/C:** Impose ceremony where none is needed.
- **Why not D:** Swings to the opposite error — documents, diagrams, and reports are legitimate artifact content, not just code.

**55 — Correct: B · Domain 6**

- **Why B:** This is the proportionality/human-impact dimension of responsible use: policy permission is the floor, and consequential people-affecting communications warrant genuine human authorship and ownership, with Claude assisting rather than replacing the human.
- **Why not A:** Treats compliance as the whole analysis.
- **Why not C:** Reduces an ethical question to tone.
- **Why not D:** Adds impersonation — presenting AI output under a fictitious human identity — to the original problem.

**56 — Correct: B · Domain 5**

- **Why B:** Superseded versions must be removed: outdated knowledge is worse than missing knowledge because Claude will confidently use it.
- **Why not A/C:** Leave the contradiction in place and hope retrieval favors the right file.
- **Why not D:** Shifts a configuration fix onto every user in every chat, which is exactly what knowledge maintenance exists to prevent.

**57 — Correct: A and B · Domain 7**

- **Why A and B:** Official guidance is explicit that not every problem is best solved by prompt engineering: after well-diagnosed revisions fail, the levers are feature fit (A) and model selection matched to quality/speed/cost (B).
- **Why not C:** Iterates indefinitely on the wrong lever.
- **Why not D:** Product feedback, not a resolution step.
- **Why not E:** Brute-force repetition with no diagnosis.

**58 — Correct: B · Domain 4**

- **Why B:** AI-powered artifacts can be published and shared, with each user authenticating with their own Claude account and usage counting against their own subscription — the verified mechanism for exactly this need.
- **Why not A/C:** Share a picture or code, not a working tool.
- **Why not D:** Makes the associate the bottleneck the tool was built to remove.

**59 — Correct: B · Domain 2**

- **Why B:** Curation is an evaluation act: cut what doesn't serve the decision, order by importance, keep citations attached to the facts they support, and put caveats beside the claims they qualify.
- **Why not A:** Transfers the filtering burden to the director.
- **Why not C:** Strips the apparatus the next reviewer needs to re-verify.
- **Why not D:** Treats raw conversation as a deliverable, which loses structure, curation, and verifiability.

**60 — Correct: B · Domain 1**

- **Why B:** The documented self-correction chaining pattern is generate → review against explicit criteria → refine; it turns the checklist into an enforceable step.
- **Why not A:** Hopes one pass plus an adjective clears the bar.
- **Why not C:** Selects by length, which is not a quality criterion.
- **Why not D:** Gates publication on self-reported scoring, which is not an accuracy or quality signal.

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
