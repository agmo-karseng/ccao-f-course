---
title: "6. Governance, Risk & Responsible Use"
nav_order: 8
---

# Module 6 — Governance, Risk, and Responsible Use (Domain 6, 15%)

> **Blueprint objectives covered in this module**
>
> 1. Identify appropriate and inappropriate use cases
> 2. Apply data sensitivity, regulatory, and privacy considerations
> 3. Follow organizational AI policies and governance standards
> 4. Understand the ethical implications of AI usage

## Why this domain matters

Domain 6 carries 15% of the CCAO-F exam — roughly 9 of 60 items — and it tests judgment, not memorization. The certified associate sits between casual AI users and technical practitioners, which means colleagues will follow their lead on what is safe to put into Claude, which tasks belong there at all, and when a human must stay in the loop. Exam items in this domain reward *policy-aligned pragmatism*: the best answer almost never refuses the task outright and almost never barrels ahead ignoring risk. It finds the compliant path that still delivers the business outcome — the pattern the official exam guide demonstrates in Sample 3, where the correct move is to anonymize the data, not abandon the analysis.

---

## Objective 6.1 — Identify appropriate and inappropriate use cases

### The three-zone model

Before starting any task with Claude, a competent associate mentally sorts it into one of three zones:

| Zone | Description | What to do |
|---|---|---|
| **Green — appropriate** | Routine business and productivity work: drafting, summarizing, brainstorming, analyzing non-sensitive data, research support, process design | Proceed, with normal output validation (Domain 2) |
| **Amber — appropriate with safeguards** | Work touching high-stakes domains (legal, health, finance, hiring) or sensitive data | Proceed only with required controls: qualified human review, AI disclosure, data minimization |
| **Red — inappropriate** | Uses prohibited by Anthropic's Usage Policy, law, or organizational policy | Do not proceed; escalate or decline |

### Green zone: what Claude is for

The certification's own definition of the credential is a good map of appropriate use: completing structured business tasks, streamlining workflows, improving processes, and adapting content for audiences. Concrete examples:

- Summarizing meeting notes and drafting follow-up actions
- Turning a rough outline into a first-draft proposal, then iterating
- Analyzing anonymized or non-sensitive datasets for trends
- Drafting internal communications, training materials, and documentation
- Researching and comparing options before a business decision (with verification)

### Red zone: prohibited uses under Anthropic's Usage Policy

Anthropic publishes a Usage Policy (also called the Acceptable Use Policy) that applies to everyone who submits inputs to its products. Its **Universal Usage Standards** apply to all users and all use cases. At a summary level, they prohibit using Claude to:

- Violate applicable laws or facilitate illegal activity
- Compromise critical infrastructure or computer/network systems (e.g., creating malware, exploiting systems without authorization)
- Develop or design weapons
- Incite violence or hateful behavior
- Compromise privacy or identity rights — including collecting private information without permission, or impersonating a human by presenting AI output as human-generated
- Compromise children's safety
- Create psychologically or emotionally harmful content (harassment, bullying, promotion of self-harm)
- Create or spread misinformation, including fake reviews and deceptive content
- Undermine democratic processes or run targeted campaign activities
- Perform prohibited criminal-justice, censorship, or surveillance functions (e.g., tracking people without consent, social scoring)
- Engage in fraudulent, abusive, or predatory practices — a business-relevant example: generating fake reviews or plagiarizing AI-assisted work without permission or attribution
- Abuse the platform (e.g., jailbreaking guardrails, scraping model outputs to train other models without authorization)

Anthropic states that its Safeguards team implements detection and monitoring to enforce this policy, and that violations can lead to throttled, suspended, or terminated access. An associate does not need to memorize every bullet, but must recognize the categories and the fact that "it's for internal use only" is never a defense for a prohibited use.

### Amber zone: high-risk use cases require human-in-the-loop and disclosure

This is one of the most exam-relevant parts of the Usage Policy. For consumer-facing **High-Risk Use Cases**, Anthropic requires two additional safety measures:

1. **Human-in-the-loop:** when Claude output feeds advice, recommendations, or subjective decisions that directly affect individuals or consumers, a **qualified professional in that field must review** the content or decision before it is finalized or shared. The organization remains responsible for accuracy and appropriateness.
2. **Disclosure:** if outputs are presented directly to individuals or consumers, they must be told that AI helped produce the advice, decision, or recommendation — at minimum at the start of each session.

The high-risk domains named in the policy are: **legal, healthcare, insurance, finance, employment and housing, academic testing/accreditation/admissions, and automatically generated journalistic or media content**. Anthropic's guidelines also state that all consumer-facing chatbots must disclose to users that they are interacting with AI rather than a human.

**Business scenario — the amber zone in practice.** An HR team wants Claude to help screen résumés. This falls squarely into the employment high-risk category. The appropriate answer on an exam item is not "never use Claude for hiring" and not "let Claude rank candidates and act on the ranking." It is: use Claude as a drafting and summarization aid while a qualified human reviews every recommendation before it affects any candidate, with disclosure where outputs reach applicants — and confirm the workflow is permitted by internal policy.

### Agentic use cases

When Claude acts as an agent — performing multi-step tasks or taking actions on a user's behalf — the Usage Policy still applies in full. Anthropic's help-center guidance gives illustrative agentic prohibitions, including using agents for surveillance or unauthorized data collection, generating or distributing harmful content (phishing sites, impersonation), scaled abuse (spam, coordinated harassment, manipulating polls or engagement metrics), and unauthorized system access or manipulation. The practical takeaway for an associate: giving Claude the ability to *act* raises the stakes, so permissions should be scoped narrowly and consequential actions should stay behind human confirmation.

### A quick use-case screen (teachable checklist)

Before adopting any new Claude use case, ask in order:

1. **Legal?** Would this violate any law or regulation? → If yes, stop.
2. **Permitted by Anthropic?** Does it fall in a Usage Policy prohibited category? → If yes, stop.
3. **Permitted by my organization?** Does internal AI policy allow it, on this account, with this data? → If unclear, ask before proceeding.
4. **High-stakes?** Does it affect individuals' legal, financial, health, employment, or housing outcomes? → If yes, add qualified human review and AI disclosure.
5. **Data-safe?** Can it be done without exposing sensitive data, or with the data minimized first? → Apply Objective 6.2.

If the task passes the screen, proceed — and validate outputs per Domain 2.

---

## Objective 6.2 — Apply data sensitivity, regulatory, and privacy considerations

### Classify before you paste

The single most common governance failure is pasting or uploading data without thinking about what it contains. Teach a simple classification habit:

| Tier | Examples | Default handling with Claude |
|---|---|---|
| **Public** | Published reports, marketing copy, public website content | Freely usable |
| **Internal** | Meeting notes, process docs, non-sensitive drafts | Usable if organizational policy permits, on an approved account |
| **Confidential** | Unreleased financials, contracts, strategy documents, trade secrets | Only per policy, typically on enterprise/commercial plans with approved settings |
| **Regulated personal data** | Customer names + account numbers, health records, payroll data, government IDs — personal data protected under laws such as the GDPR, HIPAA-type health privacy rules, or PCI-type payment card standards | Remove, anonymize, or aggregate before use, or use an approved compliant environment; when in doubt, escalate |

Name regulations at this general level — the exam expects candidates to recognize *that* customer PII, health data, and payment data are regulated and require care, not to recite statute text.

### The "anonymize, don't abandon" pattern

This is the signature Domain 6 reasoning pattern, demonstrated in the exam guide's Sample 3. A project manager wants to upload a spreadsheet of customer names and account numbers for trend analysis, but policy restricts sharing regulated personal data. The four archetypal responses:

- **Upload as-is "because it's internal"** — wrong: internal use does not suspend data policy.
- **Upload but tell Claude not to retain it** — wrong: a prompt instruction is not a data-protection control and does not satisfy policy. Data handling is governed by account type, settings, and agreements — not by what you type in the chat.
- **Skip the analysis entirely** — wrong: over-refusal forfeits business value that a compliant path could deliver.
- **Remove or anonymize the identifiers first, then proceed** — correct: the identifiers are not needed for trend analysis, so strip names and account numbers (or replace them with tokens like `CUST-001`), upload the minimized dataset, and complete the task within policy.

Generalize the pattern: **minimize → substitute → aggregate → proceed.** Delete fields the task doesn't need; pseudonymize the ones it does; aggregate when individual rows aren't required. Only when the task genuinely cannot be done without exposing protected data does the answer become "use an approved environment" or "escalate" — and only rarely "don't do it."

### Know how Claude handles data (verified against Anthropic sources)

Exam items may test whether a candidate understands the real controls that exist, versus imagined ones:

- **Consumer vs. commercial defaults differ.** For commercial products such as Claude for Work (Team/Enterprise) and the Claude API, Anthropic states that by default it does **not** use customer inputs and outputs to train its models (exceptions include content users explicitly report, e.g., via thumbs up/down feedback). For consumer products (Free/Pro/Max), inputs and outputs **may** be used to improve models unless the user opts out in privacy settings; safety-flagged or explicitly reported content may still be used even after opt-out.
- **Users have controls.** Consumer users can change model-training privacy settings at any time, use Incognito chats (which are not used to improve Claude), and delete conversations — deleted chats are removed from history immediately and deleted from back-end systems within 30 days, per Anthropic's privacy documentation.
- **Feedback is special.** Submitting thumbs up/down feedback can store the entire related conversation (retained up to 5 years, de-linked from user IDs). On Team/Enterprise plans, admins can disable members' ability to submit feedback. Practical rule: never rate a conversation containing sensitive data on a plan where feedback sharing is enabled, and follow your organization's setting.
- **Connectors send data to third parties.** When Claude connects to third-party services (Google Drive, Gmail, MCP servers, etc.), those services receive and process data under **their own** privacy policies. Anthropic's privacy policy also makes users responsible for ensuring they have the rights and permissions for content they upload or connect. Governance implication: enabling a connector is a data-sharing decision and belongs under organizational approval.
- **The consumer privacy policy is not the enterprise contract.** Anthropic's consumer Privacy Policy explicitly does not cover content processed for business offerings such as Enterprise accounts — that is governed by customer agreements. So "which rules apply" depends on which account you are using: one more reason organizational policies usually require work data to stay on the organization's sanctioned account.

### Pre-upload checklist (classroom handout)

Before uploading any file or pasting any block of data into Claude, confirm:

1. **What's in it?** Scan for names, contact details, IDs, account or card numbers, health information, credentials, API keys.
2. **Is it regulated or confidential?** If yes — does the task really need those fields?
3. **Can I minimize?** Strip, pseudonymize, or aggregate before upload.
4. **Am I on the right account?** Sanctioned org workspace, correct plan, approved settings — not a personal account.
5. **Does policy or a contract restrict this data?** NDAs and customer agreements bind you regardless of the tool.
6. **Would I be comfortable explaining this upload to my compliance team?** If not, ask first.

---

## Objective 6.3 — Follow organizational AI policies and governance standards

### Policy-first decision-making

When rules appear to conflict, apply the **strictest applicable rule**. The effective hierarchy for an associate:

1. **Law and regulation** — always binding.
2. **Organizational policy and contracts** — your employer's AI policy, security standards, NDAs, and customer agreements can be stricter than anything Anthropic requires, and they win over convenience every time.
3. **Anthropic's Usage Policy and terms** — the floor for what the platform permits.
4. **Personal judgment and efficiency** — legitimate only inside the space the first three allow.

An exam-style tell: any option that justifies an action *solely* because it is faster, "just internal," or "what the tool technically allows" is almost certainly wrong when a policy constraint is present in the scenario.

### What organizational AI governance typically covers

Candidates should recognize the standard components of a corporate AI policy (general guidance, not Anthropic-specific):

- **Sanctioned tools and accounts** — which AI services are approved, and on which plans. Using a personal Claude account for company data ("shadow AI") typically violates policy even when the same task would be fine on the enterprise workspace, because the organization's contractual protections, admin controls, and data settings only apply to the sanctioned account.
- **Data rules** — what classifications may be used with AI, and under what conditions (ties to Objective 6.2).
- **Use-case approval** — new or high-stakes workflows may need review by a governance board, legal, or security before adoption.
- **Human oversight requirements** — which outputs need review, by whom, before they are relied on or shared externally.
- **Disclosure and attribution rules** — when AI assistance must be disclosed to clients, the public, or internally.
- **Escalation paths** — who to ask when the policy is silent or ambiguous.

### The escalation habit

"Ask before acting" is a scored behavior in this domain. The right response to an ambiguous situation is rarely to guess:

- Policy is silent on a new use case → ask the policy owner / governance contact before proceeding.
- A colleague requests something that seems to violate policy → do not comply quietly; raise it with the requester and, if needed, escalate.
- You discover sensitive data was already uploaded in error → report it promptly through your organization's incident process (and delete the conversation where controls allow); concealing an incident compounds it.
- A task exceeds your technical scope (API integrations, agentic system design) → escalate to Claude Architects/Developers per the certification's own scope boundary.

**Business scenario — policy first.** A marketing associate finds that the fastest way to analyze a customer survey is to paste raw responses (with emails) into a personal Claude account, because the corporate workspace requires a data-handling form. The policy-aligned answer: submit the form or strip the emails and use the corporate workspace — not the personal-account shortcut. Speed never outranks a control that exists precisely for this data.

---

## Objective 6.4 — Understand the ethical implications of AI usage

Beyond compliance, the exam tests whether candidates can reason about ethics in everyday use. Four dimensions cover most items:

### Transparency

People affected by AI-assisted work deserve to know when AI was involved, in proportion to the stakes. Anthropic's Usage Policy makes disclosure mandatory in specific cases (consumer-facing chatbots; high-risk advice presented to individuals) and prohibits impersonating a human by presenting AI output as human-generated. Ethically, the same logic extends further: passing off AI-assisted work as entirely your own where attribution is expected (e.g., academic or client contexts) is both an ethics problem and, in the case of plagiarism without permission or attribution, a Usage Policy violation.

### Accountability

**The human who uses the output owns the outcome.** "Claude wrote it" is never an accountability transfer — not for factual errors, not for biased recommendations, not for policy breaches. This is why human review requirements exist and why Domain 2 (output validation) and Domain 6 interlock: sending unverified AI output to a decision-maker is both a quality failure and a governance failure. In high-risk use cases, Anthropic's policy states explicitly that the deploying organization is responsible for the accuracy and appropriateness of the information.

### Bias and fairness

Models learn from human-generated data and can reproduce or amplify societal bias. Practical implications for an associate:

- Treat any AI ranking, scoring, or characterization of *people* (candidates, customers, employees) as high-risk by default; require human review.
- Watch for skewed patterns: does the summary systematically favor certain groups, framings, or demographics? Spot-check outputs across varied inputs.
- Do not use Claude for the discriminatory or social-scoring purposes the Usage Policy prohibits outright.

### Over-reliance and automation bias

Fluent, confident output invites uncritical acceptance — the failure mode behind the exam guide's Sample 1, where a fabricated-looking citation must be verified before it reaches a compliance team. Ethical use means calibrated reliance:

- Keep humans genuinely "in the loop," not rubber-stamping. A reviewer who approves everything is a control on paper only.
- Preserve skill and judgment: use Claude to draft and accelerate, while retaining the expertise to evaluate its work.
- Match verification effort to stakes: a brainstorm needs little; a regulatory summary needs authoritative-source checking.

A fifth, quieter dimension worth mentioning to trainees: **proportionality** — just because Claude *can* do a task doesn't mean it *should* (e.g., drafting a layoff notification or performance review with zero human authorship may be technically permitted yet ethically tone-deaf for the people affected). Judgment about human impact is part of responsible use.

---

## Trainer notes

### Teaching tips

- **Anchor everything to Sample 3.** Open the session with the exam guide's Sample 3 item and have the class articulate *why* each wrong option fails. The "anonymize, don't abandon" pattern is the domain's skeleton key: exam answers reject both recklessness and over-refusal.
- **Teach the answer-elimination heuristics.** In Domain 6 items, options that (a) proceed while ignoring a stated policy, (b) rely on prompt instructions as data-protection controls, (c) abandon the task entirely, or (d) shift accountability to the model are almost always distractors. The credited answer usually *adapts the task* to fit the rules.
- **Distinguish "Anthropic's rules" from "your org's rules."** Candidates often blur them. Anthropic's Usage Policy is the platform floor; organizational policy is usually stricter and controls day-to-day decisions. Scenarios typically hinge on the organizational layer.
- **Use the consumer/commercial training-data contrast** as a memorable concrete fact: commercial products don't train on your data by default; consumer products may unless you opt out. It powerfully illustrates *why* companies mandate sanctioned accounts.
- Keep regulation talk general (GDPR-style personal data, health/payment data sensitivity). The exam does not require legal citations, and inventing them models exactly the wrong behavior.

### Discussion prompts

1. Your CFO asks you to run next quarter's unreleased financials through Claude on your personal Pro account "since the enterprise rollout is delayed." What are all the distinct governance issues in this one request, and what compliant alternative do you propose?
2. A teammate says: "I told Claude not to store or train on the data, so uploading the customer file is fine." Why is a prompt instruction not a data-protection control, and what actually governs how the data is handled?
3. Where is the line between using Claude to *inform* a hiring decision and letting it *make* one? What does Anthropic's high-risk guidance require, and what would your organization add on top?
4. Your team's "human review" step for AI-drafted customer advice has a 100% approval rate over three months. Is the human really in the loop? How would you redesign the control?
5. When should an associate *decline* a task entirely rather than find a compliant adaptation? Try to construct three realistic examples (hint: Usage Policy red-zone categories).

### Common misconceptions

- **"It's internal, so data rules don't apply."** Data classification and privacy obligations follow the data, not the audience.
- **"Telling Claude not to retain/train on data makes it safe."** Handling is governed by account type, settings, and agreements — not chat instructions.
- **"Anthropic doesn't train on any user data" / "Anthropic trains on all user data."** Both wrong: commercial products default to no training on inputs/outputs; consumer products may train unless the user opts out, with exceptions (feedback, safety-flagged content) either way.
- **"Deleting the chat is a substitute for not uploading."** Deletion helps (back-end removal within 30 days on consumer plans, per Anthropic), but prevention is the control; an upload may already have violated policy or a contract.
- **"If Claude produced it, Claude is responsible for it."** Accountability always stays with the human and organization using the output.
- **"Governance means saying no."** The domain's core skill is finding the compliant *yes* — minimize, adapt, add review, disclose.

### Hands-on classroom exercise: governance case debate

Split the class into groups of 3–4. Give each group one case card; they get 10 minutes to classify it (green/amber/red), name the governing rule layer (law / org policy / Anthropic Usage Policy), and design the *most permissive compliant* workflow — then 3 minutes to defend it while the class attacks the weakest point.

- **Card A:** Support team wants Claude to draft replies to customer complaints, sent after a quick agent skim. (Amber: disclosure question, review quality, PII in tickets.)
- **Card B:** Analyst wants to upload the full customer database to find churn patterns. (Amber: minimize/pseudonymize first; approved account.)
- **Card C:** Sales rep wants Claude to write LinkedIn outreach posing as a human colleague's personal notes, at scale. (Red flags: impersonation/deception, spam-like scaled outreach.)
- **Card D:** HR wants Claude to produce a first-pass ranking of 400 internal applicants. (Amber-to-red: employment high-risk; qualified human review mandatory; bias monitoring; check org policy.)
- **Card E:** An employee discovers a colleague pasted patient records into a personal Claude account last week. (Incident response: report, don't conceal; remediation and settings review.)

Debrief by mapping each group's answer to the objectives: use-case screen (6.1), data minimization (6.2), policy hierarchy and escalation (6.3), ethics dimensions (6.4).

---

## Practice questions

*Original items written in the style of the CCAO-F exam. They are not actual exam questions. Unless an item states otherwise, select ONE response.*

**Q1.** An operations associate wants Claude to analyze a spreadsheet of employee salaries, names, and bank details to find payroll anomalies. Company policy prohibits sharing regulated personal data with external services. What is the most appropriate action?

A. Upload the file, since payroll review is a legitimate business purpose.
B. Replace names and bank details with anonymous IDs, remove unneeded fields, then upload for analysis.
C. Upload the file but add a prompt instructing Claude to delete the data afterward.
D. Conclude that Claude cannot be used for any payroll-related work.

**Q2.** A financial services firm plans to use Claude to generate personalized investment recommendations delivered directly to retail customers. Under Anthropic's Usage Policy guidance for high-risk use cases, which TWO measures are required? (Select TWO.)

A. A qualified professional reviews the advice before it reaches customers.
B. Recommendations are limited to 500 words each.
C. Customers are told that AI is used to help produce the recommendations.
D. The firm uses only the fastest available model to reduce cost.
E. Customer names are converted to uppercase before processing.

**Q3.** A marketing manager asks an associate to use Claude to write dozens of five-star product reviews to post on retail sites, written as if from real customers. What should the associate do?

A. Comply, since promoting the company's own product is a normal marketing task.
B. Comply, but disclose the reviews internally to the legal team afterward.
C. Decline and explain that generating fake reviews is a deceptive practice prohibited by Anthropic's Usage Policy, and propose compliant alternatives such as drafting requests inviting real customers to review.
D. Use a personal account so the company workspace is not implicated.

**Q4.** An associate's organization has an approved Claude Enterprise workspace. The associate finds it more convenient to use a personal Claude Pro account for summarizing internal strategy documents. What is the primary governance problem?

A. Personal accounts produce lower-quality summaries.
B. Company data leaves the organization's sanctioned environment, losing its contractual protections, admin controls, and data-handling settings — and consumer plans have different training-data defaults.
C. The Enterprise workspace is always cheaper per message.
D. Personal accounts cannot upload files.

**Q5.** While preparing a dataset, an associate realizes a colleague already uploaded a file containing customer health information to Claude last week, against policy. What is the most appropriate first action?

A. Quietly delete the conversation and say nothing, since the risk has passed.
B. Report the incident through the organization's incident/escalation process so it can be assessed and remediated.
C. Wait to see whether anyone notices before deciding what to do.
D. Post a warning in the team channel naming the colleague.

**Q6.** A company deploys a Claude-powered chatbot on its public website to answer customer questions. According to Anthropic's Usage Policy guidance for consumer-facing chatbots, what must the company do?

A. Disclose to users that they are interacting with AI rather than a human, at minimum at the start of each chat session.
B. Give the chatbot a human name and persona to build trust.
C. Restrict the chatbot to business hours.
D. Route every single response through a lawyer before it is sent.

**Q7.** An HR team uses Claude to summarize candidate résumés into a comparison table, and a recruiter reads each summary and the underlying résumé before any decision. Which additional ethical risk most needs ongoing attention in this workflow?

A. The summaries may be too short to be useful.
B. The model may reflect or amplify bias in how it characterizes candidates, so outputs should be monitored for skewed patterns across demographic groups.
C. Claude may refuse to summarize résumés.
D. The table format may not match the company's brand colors.

**Q8.** An associate's team has begun approving Claude-drafted client advisory notes so quickly that the review step averages under 20 seconds per note, with no edits in months. From a governance standpoint, what is the main concern?

A. The team is wasting time on an unnecessary review step.
B. Automation bias has hollowed out the human-in-the-loop control — review exists on paper but no longer provides genuine oversight or accountability.
C. Claude's drafts should be slowed down to match review speed.
D. The team should switch to a more expensive model so reviews feel more substantial.

**Q9.** An organization's AI policy is silent about connecting Claude to a third-party cloud-storage connector that would give it access to a shared drive containing client contracts. What is the most appropriate action?

A. Enable the connector, since the policy does not explicitly forbid it.
B. Enable the connector but only during off-peak hours.
C. Ask the policy owner or governance contact for approval first, noting that connectors send data to third-party services governed by their own privacy policies.
D. Manually paste the contracts into the chat instead, to avoid the connector question.

### Answers

**Q1 — B.** Minimizing and pseudonymizing the data lets the analysis proceed within policy — the "anonymize, don't abandon" pattern. A ignores the stated policy; C treats a prompt instruction as a data-protection control, which it is not; D abandons legitimate business value that a compliant path can deliver.

**Q2 — A and C.** Anthropic's high-risk use case requirements for finance (among other domains) are human-in-the-loop review by a qualified professional and disclosure of AI involvement to the individuals receiving the advice. B, D, and E are irrelevant to the policy requirements.

**Q3 — C.** Generating fake reviews falls under deceptive/fraudulent practices prohibited by the Usage Policy, regardless of who benefits or which account is used (D would add a policy-evasion problem, not remove one). The best answer declines the prohibited task while offering a compliant route to the underlying business goal.

**Q4 — B.** The core issue is shadow AI: outside the sanctioned workspace, the organization's contractual terms, admin controls, and data settings do not apply, and consumer-plan defaults differ (for example, consumer products may use chats for model improvement unless the user opts out, whereas commercial products do not train on inputs/outputs by default). A, C, and D are factually unfounded or beside the point.

**Q5 — B.** Incidents must be surfaced through proper channels so the organization can assess exposure and remediate; concealment (A, C) compounds the violation, and public blaming (D) is neither an incident process nor constructive. Deleting the conversation may be part of remediation, but only after reporting.

**Q6 — A.** Anthropic's Usage Policy guidance states that consumer-facing chatbots must disclose that users are interacting with AI, at minimum at the beginning of each session. B works against transparency; C and D are not requirements.

**Q7 — B.** Employment decisions are a high-stakes domain where model bias can skew characterizations of people; the human review already in place must be paired with ongoing monitoring for biased patterns. A, C, and D are not governance risks.

**Q8 — B.** A review step that never changes anything and takes seconds is a rubber stamp: over-reliance/automation bias has neutralized the control, undermining both the oversight it was designed to provide and (in high-risk contexts) the substance of a human-in-the-loop requirement. A draws the wrong conclusion — the fix is to strengthen review, not delete it.

**Q9 — C.** When policy is silent, the governed behavior is to escalate before acting — especially for connectors, which share data with third-party services processing it under their own privacy policies. A treats silence as permission; D smuggles the same sensitive data in through a different door without resolving the approval question.

---

## Sources

Official Anthropic pages verified for this module (accessed July 2026):

- Anthropic Usage Policy (Acceptable Use Policy) — Universal Usage Standards, High-Risk Use Case Requirements, chatbot disclosure, enforcement: https://www.anthropic.com/legal/aup
- Anthropic Privacy Policy — inputs/outputs, training uses and opt-out, third-party integrations, user responsibility for uploaded content, scope vs. business offerings: https://www.anthropic.com/legal/privacy
- Claude Help Center — "Using Agents According to Our Usage Policy" (agentic prohibitions): https://support.claude.com/en/articles/12005017-using-agents-according-to-our-usage-policy
- Anthropic Privacy Center — "How long do you store my data?" (consumer retention, deletion within 30 days, model-improvement setting, Incognito chats): https://privacy.claude.com/en/articles/10023548-how-long-do-you-store-my-data
- Anthropic Privacy Center — "Is my data used for model training?" (commercial products: no training on inputs/outputs by default; feedback handling; admin controls): https://privacy.claude.com/en/articles/7996868-is-my-data-used-for-model-training

Exam structure, objectives, and Sample 3 style reference: CCAO-F Exam Guide v1.0 (available from the Anthropic Partner Academy).
