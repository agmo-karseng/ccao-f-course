---
title: "Mock Exam (60 Questions)"
nav_order: 10
---

# CCAO-F Full-Length Mock Exam

**Claude Certified Associate – Foundations (CCAO-F) · Practice Examination · Form A**

---

## Instructions

- **Time limit: 120 minutes.** Set a timer before you begin and stop when it expires — pacing is part of what this mock exam trains (about 2 minutes per item).
- **Closed book.** No notes, documentation, browser tabs, or AI assistance. The real exam is proctored with a clear workspace; simulate those conditions.
- **60 items.** The exam contains multiple-choice items (select ONE of four options) and multiple-response items (select TWO or THREE of five options). **Each item states how many responses to select.** Multiple-response items are scored all-or-nothing: you must select exactly the correct responses to earn credit.
- Answer every item. There is no penalty for guessing.
- Record your answers on paper or in a separate file, then score yourself with `mock-exam-answer-key.md`, which includes rationales and a per-domain scoring worksheet.

> **Important — about this practice exam.** This is an **original practice exam** written in the style of the official CCAO-F exam and its published sample questions. It is **not** real exam content: actual exam items are confidential and protected by the non-disclosure agreement every candidate accepts, and nothing here is drawn from any live item bank.
>
> **About scoring.** The real exam reports a **scaled score from 100 to 1,000 with a passing cut score of 720** — scaled scores are not raw percentages, so your raw percentage here is only a **rough readiness indicator**, not a predicted exam score. As a rule of thumb, candidates comfortably above ~75–80% raw on a full-length, timed practice exam — with no single domain far behind — are typically in a reasonable position to sit the real exam. Use the per-domain worksheet in the answer key to find weak domains and restudy those modules.

---

## Questions

**1.** A strategy analyst prompts Claude: "Explain why relocating our distribution center to Site A is the right decision." Claude returns a well-argued, persuasive case for Site A. Before presenting this to leadership, what should the analyst recognize? **(Select ONE.)**

- A. The persuasiveness of the output confirms that Site A is the correct choice.
- B. The prompt's one-sided framing biased the output; she should re-prompt for a neutral comparison of the sites, including the strongest case against Site A.
- C. She should ask Claude to rate its confidence in the recommendation and proceed if the rating is high.
- D. She should ask Claude to rewrite the case in a more formal, boardroom-ready tone before sharing it.

**2.** An event coordinator needs to confirm whether a conference venue announced a schedule change this morning. Which approach best matches the task? **(Select ONE.)**

- A. Run the Research feature to produce a comprehensive, multi-source report on the venue.
- B. Use web search in a plain chat, since this is a straightforward factual question answerable with one or two lookups.
- C. Enable extended thinking so Claude can reason more deeply about the schedule.
- D. Upload last year's venue brochure and ask Claude to infer the current schedule.

**3.** An academic program manager wants Claude to analyze course-completion trends in a spreadsheet that includes student names and student ID numbers. Institutional policy restricts sharing regulated personal data with external services. What is the most appropriate action? **(Select ONE.)**

- A. Upload the file as-is, since the analysis supports an internal academic purpose.
- B. Remove the name and ID columns (or replace them with anonymous tokens), keep only the fields the trend analysis needs, then upload and proceed.
- C. Upload the full file but instruct Claude in the prompt not to retain the student data.
- D. Conclude that Claude cannot be used for any analysis involving student records.

**4.** A client-services team instructs Claude, "Do NOT use bullet points or headings," yet Claude's client letters keep coming back with bulleted lists. Which change applies Anthropic's documented formatting guidance? **(Select ONE.)**

- A. Restate the instruction positively — "Write the letter in smoothly flowing prose paragraphs" — and match the prompt's own style to the output style wanted.
- B. Repeat the prohibition three times at the start, middle, and end of the prompt.
- C. Rewrite the prohibition in capital letters so Claude registers its importance.
- D. Switch to a different AI platform that handles negative instructions better.

**5.** An operations lead asks an associate to "use Claude to fix our late-delivery problem." Analysis shows deliveries are late because a warehouse is over capacity — the paperwork and communications around shipments are already fast. What is the most sound assessment? **(Select ONE.)**

- A. Configure a Project with all shipping documents so Claude can resolve the delays.
- B. Recognize that the bottleneck is physical and operational, not language work — Claude can assist peripheral tasks like customer delay communications, but the core fix lies outside an AI-assisted workflow.
- C. Select the most capable model family, since a harder problem needs a stronger model.
- D. Run the Research feature weekly to monitor the warehouse.

**6.** Using the Gmail connector, an associate asks Claude to "summarize the budget spreadsheet attached to yesterday's email from the client." Claude cannot produce the summary. What is the most likely reason? **(Select ONE.)**

- A. The Gmail connector provides access to email content and attachment metadata, but not attachment content — the associate should download the file and upload it to the chat directly.
- B. The Gmail connector is only available on Enterprise plans.
- C. Claude cannot process spreadsheet content under any circumstances.
- D. The associate must re-authenticate with Google before each request.

**7.** A merchandising team has Claude draft 40 product descriptions in one batch. Items 1–30 follow the required template exactly; the later items drift into a different structure, though their facts are correct. Which failure mode is this, and what is the right response? **(Select ONE.)**

- A. Hallucination — the drifting items are fabricated and the batch should be discarded.
- B. Inconsistency (format drift) — re-specify the format explicitly, regenerate the drifting items, and consider smaller batches with spot-checks.
- C. Bias — the later items frame the products unfairly.
- D. A completeness failure — some products were omitted from the batch.

**8.** A communications specialist keeps rewording a prompt asking Claude to summarize industry announcements from the past month. Web search is off, and every revision still produces outdated or wrong answers. What is the most appropriate next step? **(Select ONE.)**

- A. Keep refining the wording until the answers become current.
- B. Recognize this as a knowledge-boundary problem — the events may post-date the model's training data — and either enable web search or paste in current source material, rather than re-prompting harder.
- C. Add "use only the most recent information" to the prompt in bold.
- D. Ask Claude to double-check its answer and resend it if Claude confirms.

**9.** A pilot of Claude-assisted proposal drafting cut drafting time by 60%, but reviewers now spend 20% more time checking outputs. How should the associate report results to the sponsor? **(Select ONE.)**

- A. Report only the 60% drafting improvement, since it is the headline win.
- B. Report both figures honestly, quantify the net effect, and propose next steps to reduce the review burden.
- C. Declare the pilot a failure because a metric worsened.
- D. Remove the review step so the numbers improve before reporting.

**10.** A teammate says: "I added 'do not store or train on this data' to my prompt, so uploading the customer file is compliant with our data policy." Which response is correct? **(Select ONE.)**

- A. Correct — prompt instructions govern how Anthropic handles submitted data.
- B. Incorrect — a prompt instruction is not a data-protection control; data handling is governed by the account type, settings, and agreements, and the policy restriction still applies to the upload itself.
- C. Correct, provided the instruction appears in the first message of the conversation.
- D. Incorrect — but only because the instruction also needs to be added to the project instructions.

**11.** An operations manager asked Claude for recommendations from a customer survey export and got generic advice untethered to the data. Which restructured prompt best applies task-decomposition guidance? **(Select ONE.)**

- A. "Analyze the survey in three steps: (1) list the five most frequent complaint themes with counts, (2) quote two representative verbatim responses per theme, (3) only then recommend fixes, each tied to a theme above."
- B. "Give me your recommendations first, then work backward to justify them from the survey."
- C. "Analyze the survey. Be insightful, thorough, and world-class."
- D. "Analyze the survey" — submitted twice, merging the two outputs.

**12.** On an Enterprise plan, an analyst notices a model her friend uses on a personal Pro plan does not appear in her model menu at work. What is the most likely explanation? **(Select ONE.)**

- A. Her Claude installation is corrupted and should be reinstalled.
- B. Enterprise administrators can restrict which models and effort levels are available to a role — the "missing" model is likely a policy choice, so she should check with her admin.
- C. The model has been discontinued for all users.
- D. Enterprise plans always receive fewer models than consumer plans.

**13.** Claude drafts a client memo stating this year's statutory filing deadlines and fee amounts. The draft is fluent and specific. Before the memo is sent, what does sound validation require? **(Select ONE.)**

- A. Nothing further — the specificity of the dates and amounts indicates they came from real data.
- B. Verifying the deadlines and amounts against a current, authoritative source, since time-sensitive facts may post-date the model's training data.
- C. Asking Claude whether its information is up to date and sending the memo if it says yes.
- D. Adding "figures subject to change" at the bottom and sending it as-is.

**14.** A project manager on a paid plan worries that uploading more reference documents will "break" her project as the knowledge base approaches context limits. What actually happens? **(Select ONE.)**

- A. She must manually switch the project into retrieval mode before adding more files.
- B. The project stops accepting uploads once the context window is full.
- C. Claude automatically enables Retrieval Augmented Generation (RAG) mode as knowledge grows, loading only relevant content into context and expanding effective capacity — though pruning irrelevant files still keeps the project focused.
- D. All project knowledge is truncated to fit, starting with the oldest files.

**15.** A monthly reporting workflow suffers chronic rework and redundant handoffs. Two augmentation pilots with Claude have already demonstrated clear value in this process, and leadership has sponsored a quarter of change capacity. What is the most appropriate next step? **(Select ONE.)**

- A. Keep the workflow unchanged and continue small augmentations indefinitely, since redesign is always too risky.
- B. Redesign the workflow around the demonstrated wins — for example, contributors feed a shared Project, one owner generates the consolidated draft from standardized instructions, and reviewers shift to exception-checking.
- C. Abandon the reporting process and let each team report ad hoc.
- D. Redesign the workflow and remove the human review steps to maximize the efficiency gain.

**16.** An associate rewrites her entire prompt from scratch after every disappointing output. Quality fluctuates and she cannot tell which edits help. What troubleshooting discipline is she missing? **(Select ONE.)**

- A. Using a more capable model so that any prompt succeeds.
- B. Changing one thing at a time, so each change's effect can be attributed and the eventual fix is repeatable.
- C. Making each rewrite substantially longer than the last.
- D. Asking Claude which of her prompts was best.

**17.** An insurance company plans to have Claude generate claim-coverage recommendations delivered directly to policyholders. Under Anthropic's Usage Policy guidance for high-risk use cases, what is required? **(Select ONE.)**

- A. Recommendations must be kept under a fixed word count.
- B. A qualified professional must review the recommendations before they are finalized, and policyholders must be told that AI was used to help produce them.
- C. Nothing additional, because insurance is a routine business function.
- D. The company must use the most capable model family for all recommendations.

**18.** Which TWO of the following Claude outputs require review by a qualified human expert before use — beyond the associate's own verification? **(Select TWO.)**

- A. Drafted amendment language for a customer contract.
- B. A summary of the team's internal weekly meeting notes.
- C. A recommendation on the tax treatment of a transaction in a jurisdiction the associate knows nothing about.
- D. A brainstormed list of team-offsite activity ideas.
- E. A reformatted table of figures the associate has already verified.

**19.** Before sending Claude a long, multi-part prompt for an important deliverable, an associate wants a fast way to test whether the prompt is clear enough. Which documented technique fits? **(Select ONE.)**

- A. Show the prompt to a colleague with minimal context and ask what they would produce — if the colleague is confused, Claude will be too.
- B. Run the prompt three times and keep it if the outputs are all long.
- C. Append "this is very important, do your best work" to the prompt.
- D. Count the words: prompts over 200 words are reliably clear.

**20.** Which TWO signals in a scenario indicate the Research feature is a better fit than web search? **(Select TWO.)**

- A. The task requires synthesizing many sources into an in-depth report with citations.
- B. The question can be answered with a single quick lookup.
- C. The task should draw on connected internal documents (e.g., Google Docs) alongside the web.
- D. No outside information is needed — only harder reasoning over material already provided.
- E. The team's priority is minimizing usage-limit consumption.

**21.** The associate who built her team's Claude drafting workflow is transferring to another department. What best keeps the workflow functioning after she leaves? **(Select ONE.)**

- A. Leave her chat history available as the documentation.
- B. Move the proven prompt into the shared Project's instructions, curate the knowledge files, and write a short usage note covering what the workflow does, what it must not be used for, and the human review step.
- C. Tell colleagues to message her in the new department whenever outputs look wrong.
- D. Rely on Claude's memory to keep producing consistent results for the team.

**22.** A team wants certain guidance and reference content to apply automatically in every chat within a project. Which TWO configuration surfaces persist across all chats in a project? **(Select TWO.)**

- A. The project instructions.
- B. Files uploaded to the project knowledge base.
- C. The project description field.
- D. The content of a previous chat in the same project.
- E. The project's title.

**23.** An analyst runs the same market-sizing prompt twice and gets materially different key figures in each run. What is the correct interpretation? **(Select ONE.)**

- A. Average the two figures, since the truth is probably in between.
- B. The inconsistency flags the figure as possibly fabricated — it must be verified against an external authoritative source before use.
- C. Use the first run's figure, since first responses are the most reliable.
- D. Run the prompt a third time and treat the majority value as verified.

**24.** An associate wants to give a thumbs-down to a disappointing response in a conversation that contains a client's confidential financial data. What should she consider first? **(Select ONE.)**

- A. Feedback has no effect on data handling, so she should rate the response.
- B. Submitting feedback can store the entire related conversation with Anthropic for an extended period, so she should not rate conversations containing sensitive data and should follow her organization's feedback policy.
- C. Thumbs-down deletes the conversation, protecting the data automatically.
- D. Ratings are anonymous, so the client data is not implicated.

**25.** A marketer writes 30 similar product blurbs per week, opening a new conversation for each and re-explaining the tone rules every time. Which change best optimizes the workflow while protecting quality? **(Select ONE.)**

- A. Batch the blurbs — provide the items together with one clear instruction set and a specified output structure, keeping batches small enough to hold per-item quality, and spot-check the results.
- B. Keep 30 separate conversations but switch each one to the most capable model.
- C. Combine the blurbs, a pricing strategy, and a launch email into one giant prompt to save time.
- D. Accept first drafts without review so throughput rises.

**26.** An associate has iterated a proposal prompt four times but says, "Honestly, I can't tell whether the drafts are getting better." According to Anthropic's guidance, what precondition for effective iteration is missing? **(Select ONE.)**

- A. A more creative model.
- B. A clear definition of success criteria to test outputs against — without knowing what "better" means, revision is just regeneration.
- C. A longer prompt with more background pasted in.
- D. Permission for Claude to say "I don't know."

**27.** A finance team wants Claude in its expense-approval workflow. Which division of labor is most appropriate? **(Select ONE.)**

- A. Claude extracts expense details, summarizes claims, and flags anomalies for a reviewer; the approval decision remains with a human.
- B. Claude automatically approves claims under a threshold, with no human involvement below that line.
- C. The workflow is unsuitable for Claude because it touches money.
- D. Claude approves all claims, and an auditor reviews a sample at month-end.

**28.** A procurement associate's output will be imported into a tracking tool where the team sorts and filters vendor data. Which output format should she request? **(Select ONE.)**

- A. Eloquent narrative prose describing each vendor.
- B. A structured format — a fixed-column table or CSV — which suits the downstream system and makes any missing fields immediately visible.
- C. A beautifully formatted memo delivered as an artifact.
- D. A series of short inline paragraphs, one per vendor.

**29.** An employee has a sensitive, one-off personal HR question and does not want the conversation to influence Claude's memory or appear in past-chat searches. Which approach fits? **(Select ONE.)**

- A. Use an incognito chat, which is excluded from memory and past-chat search.
- B. Ask in a normal chat, then instruct Claude to forget the conversation.
- C. Create a dedicated project named "Private" for the question.
- D. Ask the question in an existing long-running chat so it gets buried.

**30.** Which TWO of the following requests must an associate decline under Anthropic's Usage Policy? **(Select TWO.)**

- A. Compile a dossier tracking a specific employee's personal whereabouts and private social-media activity without their consent.
- B. Mass-generate fake "grassroots" comments to manipulate an online poll about a proposed local regulation.
- C. Summarize anonymized customer survey results into themes.
- D. Draft an FAQ explaining a new internal expense policy.
- E. Brainstorm campaign slogans for a product launch.

**31.** A Team-plan project was archived during a reorganization and unarchived a month later. Teammates report they can no longer open it. What happened? **(Select ONE.)**

- A. Unarchiving corrupts project permissions and support must restore them.
- B. Archiving reset all sharing permissions to private, so the owner must deliberately re-share the project.
- C. Archived projects are automatically deleted after 30 days.
- D. The teammates' Claude accounts were deactivated by the archive action.

**32.** A Claude-drafted summary of a new safety regulation is about to go to the compliance team. Which THREE checks belong in the validation before it is sent? **(Select THREE.)**

- A. A completeness pass comparing the summary against everything the original request asked for.
- B. An internal-consistency pass confirming figures and claims agree with each other across the summary.
- C. External verification of the cited sections and load-bearing facts against the official regulation text.
- D. Asking Claude to rate its own confidence and proceeding if the rating is high.
- E. Appending an "AI-generated — please verify" disclaimer as the validation step.

**33.** A director challenges an associate: "If a human still has to review everything Claude produces, why bother?" Which response best reflects sound stakeholder communication? **(Select ONE.)**

- A. "You're right — if review is needed, the tool isn't adding value."
- B. "In our pilot, drafting fell from four hours to one. Outputs can contain errors, which is exactly why a named reviewer verifies facts — the review is the control that lets us capture the speed gain safely, and total cycle time is still down sharply."
- C. "Claude's outputs are accurate enough that we could drop the review if you prefer."
- D. "The technical details are hard to explain — leadership should trust the results."

**34.** A project manager used Claude to brainstorm 20 cost-reduction ideas and has shortlisted five. She now wants to stress-test the shortlist before proposing it. Which prompting move fits this stage? **(Select ONE.)**

- A. Ask Claude which ideas it likes most.
- B. Ask Claude to adopt the role of a skeptical CFO and critique each shortlisted idea — costs, risks, and likely objections.
- C. Regenerate the original brainstorm and compare the two lists.
- D. Ask Claude to assign each idea a confidence score and keep the top scorers.

**35.** Claude's response containing a long implementation plan stops abruptly mid-section. What does official guidance suggest? **(Select ONE.)**

- A. Resend the identical prompt and hope for a longer response.
- B. Provide the previous prompt and the partial response in the next message and ask Claude to continue where it left off — or request large deliverables in sections.
- C. Delete earlier context from the conversation so the response has room.
- D. Abandon Claude for the task, since the plan is evidently too long for any model.

**36.** A team is standing up a new workflow to analyze dense merger documents where errors would be very costly, and is unsure which model to use. Which approach aligns with Anthropic's model-selection guidance? **(Select ONE.)**

- A. Start with the most capable model to establish a quality ceiling, test against real documents, and only then consider optimizing down to a faster model if quality holds.
- B. Start with the cheapest model and commit to it, since cost discipline matters most.
- C. Choose whichever model has the newest version number.
- D. Pick any model and never revisit the choice, to keep results comparable.

**37.** A communications manager is adapting an internal incident post-mortem — which contains precise timestamps, internal system codenames, and an unconfirmed root-cause hypothesis — into a customer-facing notice. What should the customer version do? **(Select ONE.)**

- A. Include the root-cause hypothesis, since customers value transparency about internal thinking.
- B. State only confirmed facts in plain language, removing internal codenames and the speculative hypothesis, which would be a factual and legal risk to publish.
- C. Use identical text for both audiences to guarantee consistency.
- D. Make the notice deliberately vague so no statement can be checked.

**38.** Which statement accurately reflects Anthropic's data-training defaults? **(Select ONE.)**

- A. Anthropic trains its models on all user conversations regardless of plan.
- B. By default, commercial products (such as Claude for Work and the API) do not use customer inputs and outputs for training, while consumer plans may use them unless the user opts out — with exceptions such as explicitly reported content.
- C. Anthropic never uses any user data in any circumstances, on any plan.
- D. Only paid plans are used for model training; free plans are exempt.

**39.** An associate is rolling out a Claude-assisted proposal workflow across the sales organization. Which TWO practices reflect sound change management? **(Select TWO.)**

- A. Pilot with one willing team and a defined success measure before scaling.
- B. Name who reviews Claude-assisted outputs and who owns the outcomes in the new workflow.
- C. Deploy organization-wide on day one to maximize impact.
- D. Remove the review step after two weeks of good results to capture the full efficiency gain.
- E. Keep the workflow undocumented so teams can stay flexible.

**40.** A team pasted its full 8,000-word style guide, plus assorted business facts, into a project's instructions. Claude follows the guidance inconsistently and responses feel unfocused. What is the best restructuring? **(Select ONE.)**

- A. Paste the style guide a second time in the instructions for emphasis.
- B. Move the style guide (reference material) into project knowledge, and keep the instructions short and behavioral — role, audience, format rules — referencing the knowledge file by name.
- C. Move everything into the project description so it is always visible.
- D. Repeat the entire style guide at the start of every chat instead.

**41.** An associate spends hours fact-checking every line of internal brainstorm lists — and is missing deadlines — while client-bound summaries go out after a quick skim. What is the core problem? **(Select ONE.)**

- A. The associate needs a faster model for brainstorming tasks.
- B. Verification effort is not triaged by stakes: low-stakes internal ideation needs only light review, while external, decision-bearing content needs the full validation workflow.
- C. All outputs deserve identical scrutiny, so only the deadlines are the problem.
- D. Brainstorms should never be reviewed at all.

**42.** A support lead gave Claude four example ticket summaries — all short refund requests — and now Claude writes every summary in refund-request style, even for outage tickets. What went wrong, per Anthropic's guidance on examples? **(Select ONE.)**

- A. Four examples is too many; one example is the documented optimum.
- B. The examples were relevant but not diverse — they should cover varied cases (refunds, outages, complaints) so Claude doesn't learn unintended patterns.
- C. Examples should never be used for summarization tasks.
- D. The examples needed at least ten descriptive adjectives about style.

**43.** A consultant must reason through a complex staffing-allocation problem using data she has already uploaded — no fresh outside information is needed. Which capability fits best? **(Select ONE.)**

- A. The Research feature, to gather many external sources.
- B. Extended thinking (or a higher effort setting), so Claude reasons more deeply before responding.
- C. Web search, to keep the answer current.
- D. An incognito chat, to improve reasoning quality.

**44.** A Claude-assisted analysis containing an uncaught error was sent to a client under an associate's name. Who is accountable? **(Select ONE.)**

- A. Anthropic, since the model generated the erroneous content.
- B. The associate and their organization — using AI assistance never transfers accountability for work product to the tool.
- C. No one — errors from AI tools are an accepted category of blameless incident.
- D. The client, for failing to catch the error on receipt.

**45.** Claude reviews a team's written process documentation and proposes eliminating two "redundant" steps. Before implementing the change, what should the associate do? **(Select ONE.)**

- A. Implement immediately — Claude's analysis of the documents is sufficient evidence.
- B. Validate the proposal with the people who actually run the process, since documentation may not reflect operational reality and Claude's output is a hypothesis, not a finding.
- C. Ask Claude to double-check its own recommendation and proceed if it confirms.
- D. Reject the proposal, since process advice from AI cannot be useful.

**46.** A Research report cites web sources for a statistic that will anchor a public marketing claim. What must happen before the claim is used? **(Select ONE.)**

- A. Nothing — the presence of citations means the content has been verified.
- B. The associate opens and reads the cited sources, because synthesis can drop context and the response is only as good as the sources behind it.
- C. Ask Claude to confirm its own citations are real.
- D. Count the citations; more than three sources makes a claim reliable.

**47.** After weeks of edits, a team's mega-prompt now contains both "keep the report under 300 words" and "cover all twelve evaluation criteria in detail." Claude obeys one instruction or the other unpredictably. What is the right fix? **(Select ONE.)**

- A. Add "follow ALL instructions" to the end of the prompt.
- B. Consolidate the prompt: resolve the contradiction, remove superseded instructions, and state the surviving constraints prominently and unambiguously.
- C. Run the prompt repeatedly until a run satisfies both instructions.
- D. Split the prompt across two chats, one per instruction.

**48.** A regulatory disclaimer must appear in every draft produced within a project. A colleague suggests, "Just tell Claude once in a chat — memory will keep it." What is the correct assessment? **(Select ONE.)**

- A. The colleague is right; memory guarantees persistent compliance behavior.
- B. Memory is automatic and inferred, not a compliance mechanism — a hard requirement like this belongs explicitly in the project instructions so it reliably applies to every chat.
- C. The disclaimer should go in the project title, where Claude will always see it.
- D. The disclaimer must be retyped manually in every message; nothing persists.

**49.** An associate has hit a wall verifying a regulatory question and must escalate to the legal team. Which escalation is most useful? **(Select ONE.)**

- A. Forward the raw chat link and let legal read the whole conversation.
- B. Send the Claude output together with the prompt and source materials used, what was already verified and how, what could not be verified, and the specific question legal needs to answer.
- C. Send only the final Claude output, to keep the request short.
- D. Ask legal to redo the entire analysis from scratch without context, to avoid biasing them.

**50.** A growth lead asks an associate to use Claude to mass-generate comments and upvotes across community forums to inflate the product's apparent buzz. What should the associate do? **(Select ONE.)**

- A. Comply — engagement marketing is a normal growth activity.
- B. Decline, explaining that scaled manipulation of engagement metrics is prohibited under Anthropic's Usage Policy, and propose legitimate alternatives such as drafting genuine community content and outreach.
- C. Comply, but run the activity from a personal account so the company workspace is not implicated.
- D. Comply at a smaller scale so the activity is less noticeable.

**51.** A consultant's prompt mixes a 60-page client report, her own instructions, and a grading rubric. Claude keeps conflating the report's text with her instructions and misses the actual question. Which TWO documented techniques address this? **(Select TWO.)**

- A. Separate the content types with clearly named XML-style tags (e.g., `<instructions>`, `<document>`, `<rubric>`).
- B. Place the long report near the top of the prompt, with the question and instructions after it.
- C. Rewrite the instructions in capital letters so they stand out from the report.
- D. Split the report into twenty separate messages sent one at a time.
- E. Delete the rubric, since prompts should contain only one kind of content.

**52.** A client asks a consultant to commit to a Claude chat-based workflow with a contractual 99.9% uptime guarantee, processing thousands of documents unattended every night. What is the appropriate response? **(Select ONE.)**

- A. Accept — a well-configured Project can meet contractual uptime and throughput guarantees.
- B. Recognize that unattended, guaranteed-SLA automation at volume is beyond Associate-level, chat-based workflow scope; document the validated requirements and bring in engineering or Claude Architect/Developer expertise.
- C. Decline all further work with the client.
- D. Accept, but plan to check the chat manually each morning as the "guarantee."

**53.** A colleague says: "Claude now summarizes older messages automatically when a chat gets long, so conversations never degrade and we never need to restart." What is the accurate assessment? **(Select ONE.)**

- A. Correct — automatic context management fully eliminates context limitations.
- B. Partly correct — automatic context management lets most long conversations continue, but it has edge cases, so judgment about when to restart, summarize, or persist context is still the associate's job.
- C. Incorrect — no such mechanism exists, so every long chat must be abandoned.
- D. Correct, but only when using the fastest model family.

**54.** A colleague insists that every Claude answer — including two-sentence factual replies — be turned into an artifact "for consistency." What is the right guidance? **(Select ONE.)**

- A. Agree: artifacts are always the more professional format.
- B. Short answers consumed within the conversation belong inline; artifacts are for substantial, self-contained content that will be edited, reused, or referenced later — forcing them on trivial answers adds friction without value.
- C. Agree, but only if each artifact is also exported to PDF.
- D. Disagree: artifacts should be reserved exclusively for code.

**55.** An HR manager plans to have Claude fully generate individualized layoff notification messages and send them verbatim, with no human authorship. Organizational policy technically permits AI-assisted internal drafting. What consideration should guide the associate's advice? **(Select ONE.)**

- A. Since policy permits it, there is nothing further to weigh.
- B. Beyond compliance, proportionality and human impact matter: communications this consequential to individuals warrant genuine human authorship and ownership, with Claude at most assisting drafts that a human substantially shapes and reviews.
- C. The only concern is choosing a model capable of an empathetic tone.
- D. The messages should be generated but signed with a fictitious human name.

**56.** A project's knowledge base contains both the 2025 and 2026 versions of the travel policy, and Claude keeps citing the outdated one. What is the correct maintenance action? **(Select ONE.)**

- A. Add a third file explaining which of the two policies is current.
- B. Remove the superseded 2025 version from project knowledge — outdated knowledge is worse than missing knowledge because Claude will confidently use it.
- C. Rename the 2026 file to "IMPORTANT" so Claude prefers it.
- D. Ask users to mention the correct year in every chat.

**57.** After three well-diagnosed prompt revisions, a document-analysis workflow is still too shallow and too slow. Which TWO next steps align with official guidance? **(Select TWO.)**

- A. Evaluate whether a different capability fits the task — for example, extended thinking for deeper reasoning, or retrieval features if current information is the gap.
- B. Reassess model selection against the task's quality, speed, and cost requirements instead of continuing to tweak wording.
- C. Keep iterating the prompt wording indefinitely until it works.
- D. Submit a thumbs-down on each poor response and wait for the product to improve.
- E. Resend the original prompt with stronger emphasis words.

**58.** An operations associate built an interactive capacity-planning tool as an artifact and wants roughly 40 colleagues to use it — without the usage counting against her own subscription. Which approach fits? **(Select ONE.)**

- A. Screenshot the tool and circulate the image.
- B. Publish and share it as an AI-powered artifact: colleagues authenticate with their own Claude accounts, and their usage counts against their own subscriptions.
- C. Paste the underlying code into an email for colleagues to read.
- D. Keep the artifact private and run every colleague's scenario for them on request.

**59.** A 20-page Claude research output must inform a director's single go/no-go decision. How should the associate prepare it? **(Select ONE.)**

- A. Send the full 20 pages so no information is lost.
- B. Curate it: cut what doesn't serve the decision, order findings by importance, keep source citations attached to the facts they support, and surface caveats next to the claims they qualify.
- C. Strip the citations and caveats so the document reads cleanly.
- D. Send the chat link so the director can scroll the conversation.

**60.** A monthly newsletter must pass the team's quality checklist before publishing. Which documented prompting pattern applies? **(Select ONE.)**

- A. One giant prompt ending with "make it perfect."
- B. A self-correction chain: have Claude generate the draft, then review the draft against the checklist criteria, then refine it based on that review.
- C. Generate five independent drafts and publish the longest.
- D. Ask Claude to rate the draft's quality out of ten and publish if it scores high.

---

*End of exam. Score yourself with `mock-exam-answer-key.md`.*
