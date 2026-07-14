---
title: "5. Configuration & Knowledge Management"
nav_order: 7
---

# Module 5 — Configuration and Knowledge Management (Domain 5, 12%)

> **Blueprint objectives covered in this module**
>
> 1. Configure Claude Projects with instructions and knowledge sources
> 2. Manage uploaded knowledge and connectors (e.g., Google Drive, Gmail)
> 3. Create effective system-level instructions
> 4. Inform, maintain, and update Claude configurations, knowledge sources, and instructions

> **Note on currency:** Claude's product features evolve quickly. Every product fact in this
> module was verified against the official Anthropic Help Center articles listed in the
> Sources section at the end. Before the exam — and before teaching this module — skim those
> articles again, because UI labels, plan availability, and connector behaviors can change.

---

## Why this domain matters

Domain 5 covers the "set it up once, benefit every day" side of Claude: Projects,
project knowledge, instructions at the account and project level, connectors such as
Google Drive and Gmail, and the discipline of keeping all of it current. It is worth 12%
of the exam — roughly 7 of the 60 items — and it separates candidates who merely chat
with Claude from those who configure reusable, well-governed workspaces for themselves
and their teams. A candidate who cannot decide what belongs in project instructions
versus project knowledge versus a one-off chat upload will struggle with the
scenario-style items this domain uses.

---

## 5.1 Configure Claude Projects with instructions and knowledge sources

### What a Project is

Per Anthropic's Help Center, Projects are **self-contained workspaces with their own chat
histories and knowledge bases**. Within a project you can upload documents, provide
context, and have focused chats with Claude. Projects are available to all users,
including free accounts (free users can create a maximum of five projects).

Two configuration surfaces matter for the exam:

1. **Project knowledge** — files and content you upload to the project's knowledge base.
   Claude uses this material as context **across all chats within that project**.
2. **Project instructions** — behavioral guidance you set once per project ("Set project
   instructions" in the project). Claude applies these instructions to **every chat in
   that project** — for example, using a more formal tone or answering from the
   perspective of a specific role or industry.

Two details that exam items like to probe:

- The project **name and description are organizational metadata only — Claude does not
  have access to them**. If Claude needs to know something, it must be in the
  instructions or the knowledge base, not the project title.
- **Context is not shared across chats within a project** unless the information is added
  to the project knowledge base. Each chat starts fresh; the knowledge base and
  instructions are what persist.

### Scaling knowledge: RAG for Projects

On paid plans (Pro, Max, Team, Enterprise), when project knowledge approaches the context
window limit, Claude **automatically enables Retrieval Augmented Generation (RAG) mode**,
expanding the project's effective capacity by up to 10x while maintaining response
quality. You do not switch it on manually — it engages as knowledge grows. (This enhanced
RAG capacity is a paid-plan feature; free projects are bounded by the context window.)

### Writing good project instructions vs. bad ones

Project instructions are the closest thing Domain 5 has to a craft skill. Compare:

**Weak instructions (too vague, mixes content into instructions):**

> "Be helpful and professional. Here is our whole style guide: [8,000 words pasted].
> Also remember our Q3 numbers were good."

Problems: "helpful and professional" gives Claude nothing actionable; the style guide is
*reference material* that belongs in project knowledge, not instructions; "Q3 numbers
were good" is a fact (knowledge), not a behavior (instruction).

**Strong instructions (role, audience, format, constraints, escalation):**

> "You are a communications assistant for AGMO Studio's client-success team.
> - Audience: enterprise clients; tone is warm but concise, no slang.
> - Always structure replies as: 1-line summary, details, next steps.
> - Follow the style guide in project knowledge ('style-guide.pdf'); when it conflicts
>   with these instructions, the style guide wins.
> - Never invent pricing or contract terms; if asked, say the account manager will
>   confirm.
> - Draft in English unless the source email is in Malay."

Rules of thumb to teach:

- **Instructions describe *how to behave*; knowledge supplies *what to know*.**
- Keep instructions short, specific, and testable ("structure replies as X" is testable;
  "be professional" is not).
- Point instructions *at* knowledge files by name so Claude knows what each file is for.
- Include negative constraints ("never invent pricing") and escalation guidance — this
  connects to Domain 6 (responsible use).

### Project knowledge vs. a single-chat upload

A recurring exam discriminator: **where should a file live?**

| Put it in **project knowledge** | Attach it to **a single chat** |
|---|---|
| Reference material needed across many chats (style guides, product specs, glossaries, policies) | One-off inputs (this week's meeting transcript to summarize once) |
| Stable documents the whole project should "know" | Drafts you are iterating on in one conversation |
| Content teammates should share (Team/Enterprise shared projects) | Sensitive material you don't want persisting in a shared workspace |
| Material you want available without re-uploading | Quick experiments before promoting a file to knowledge |

Heuristic: if you would be annoyed to re-upload it in tomorrow's chat, it belongs in
project knowledge. If it's disposable input for one task, keep it in the chat.

### Sharing and collaboration (Team and Enterprise plans)

On Claude for Work (Team and Enterprise) plans, projects can be shared:

- **Permission levels:** *Can use* (see contents, knowledge, and instructions, and chat —
  but not edit) vs. *Can edit* (modify instructions and knowledge, manage members,
  contribute).
- **Sharing options:** individual sharing by email, bulk sharing via email lists, or
  organization-wide sharing (which an Owner/Primary Owner can disable org-wide).
- Shared projects appear in a **"Shared with me"** tab, with email notifications.
- **Archiving a project resets all sharing permissions to private** and wipes prior
  sharing context for security. Archived projects cannot be deleted until unarchived.

Exam angle: shared projects turn instructions and knowledge into *team infrastructure* —
which is why maintenance (5.4) and connector hygiene (5.2) matter.

---

## 5.2 Manage uploaded knowledge and connectors (e.g., Google Drive, Gmail)

### What connectors are

Connectors let Claude **access your apps and services, retrieve your data, and take
actions within connected services**. Two governing principles from the Help Center:

1. **Permission inheritance:** Claude inherits each person's permissions from the
   connected service. If you can't access a file, channel, or record in the source
   system, the connector can't reach it from Claude either. Restrictions in Claude can
   *narrow* access but never *grant more* than the source system permits.
2. **Explicit setup and authentication:** you browse the Connectors Directory, connect,
   and authenticate with the service. On Team and Enterprise plans, an Owner or Primary
   Owner must first enable a connector at the organization level, and **each user still
   authenticates individually** before using it (enterprise-managed auth, in beta, can
   authorize once for the whole org).

You can also add **custom connectors** to any service that supports MCP (Model Context
Protocol). Custom connectors are reached from Anthropic's cloud, so the MCP server must
be reachable over the public internet; free users are limited to one custom connector.

### The Google Workspace connectors (verified behaviors)

The Gmail, Google Calendar, and Google Drive connectors are available for all users on
Claude and Claude Desktop. Key verified capabilities and limits:

**Gmail**
- Search and read emails with natural-language queries.
- **Draft** emails — Claude creates drafts in your Gmail account but **cannot send
  emails on your behalf**; all sending is manual in Gmail. (Google's OAuth screen may
  mention send permissions, but the send function is not enabled.)
- Access email metadata, including attachment metadata — **not attachment content**.
- Manage labels and threads; list saved drafts.

**Google Calendar**
- View events and calendars; create, update, and delete events; find mutual
  availability; manage attendees and respond to invitations; set up recurring meetings.

**Google Drive**
- Search and retrieve Google Docs; read Sheets, Slides, PDFs, images, and MS Office
  files; upload files; create folders; view permissions; list recent changes.
- **Add Google Docs directly to chats and projects** by pasting URLs or selecting recent
  documents. Docs added this way **sync directly from Google Drive**, so Claude always
  works with the latest version — unlike a static file upload.
- Claude extracts **text content only**: embedded images, comments, and suggestions in
  Docs are not processed.
- In Projects, the Google Drive connector is only available when adding to Files in
  **private** projects — the option is disabled for shared projects.

**Cross-cutting behaviors**
- Claude automatically detects which connector tools a request needs; **each action
  Claude takes on your behalf requires your explicit approval**.
- Responses include **citations** to the emails, events, or documents used as sources.
- Claude retrieves the minimum information needed, only when you ask something that
  requires it; retrieved data is stored with the chat (delete the chat to delete it),
  and Anthropic states it does not train models on Gmail/Drive/Calendar connector data.

### GitHub as a knowledge source (illustrative of "sync" hygiene)

The GitHub integration adds selected repository files/folders to project knowledge. It
syncs **file names and contents on a specific branch only** (no commit history or PRs).
A **Sync** control fetches the latest version, and **Configure files** adjusts which
files Claude analyzes. Anthropic's own best practices: start small, select files
strategically to stay within token limits, and **refresh the sync regularly** —
especially before a new analysis or after significant repo changes. If you lose access
to a repo, its preview disappears from the project, though chat history remains.

### Connector hygiene (teach this as a checklist)

- **Least footprint:** connect only the services you actually need; the Help Center
  advises disconnecting services you no longer use.
- **Review scopes at connect time:** check what access the service requests before
  approving.
- **Restrict actions (Team/Enterprise):** Owners can set org-wide tool permissions per
  connector — *Always allow*, *Needs approval*, or *Blocked* per permission category —
  e.g., allow Claude to search and summarize email but block sending; allow reading
  Drive files but block creating or editing. Individual users can't override org
  restrictions.
- **Mind context load:** with roughly 10 or more connectors active, switch the Tool
  access mode from the default *Auto* to *On demand* to give conversations more room.
- **Sharing boundaries (Team/Enterprise):** connectors are only available in private
  projects, and chats with synced content can't be shared.
- **Third-party processing:** connected services process data on their own
  infrastructure under their own terms — org settings that control where *Claude's*
  inference runs do not change where third-party services operate.

---

## 5.3 Create effective system-level instructions

Claude offers layered, persistent instruction surfaces. The Help Center's
personalization article distinguishes:

| Layer | Scope | Set where | Use for |
|---|---|---|---|
| **Instructions for Claude** (profile/account-wide) | All your conversations | Settings ("Instructions for Claude") | Preferred approaches/methods, common terms you use, typical scenarios, general communication preferences |
| **Project instructions** | All chats in one project | "Set project instructions" in the project | Project-specific context, workflow guidelines, task requirements, roles/perspectives for that project |
| **Styles / Skills** | Formatting and specialized behaviors | Personalization settings | How Claude formats and delivers responses; repeatable specialized behaviors |
| **In-chat prompt** | One conversation | The message itself | Task-specific, one-off direction |

The layering rule to teach: **put an instruction at the narrowest scope that covers all
the places you need it.** Account-wide instructions that say "always answer as a
marketing expert" will contaminate your legal-review project; a per-chat instruction you
retype daily should be promoted to project instructions.

### Qualities of effective persistent instructions

1. **Specific and behavioral.** "Open every draft with a one-sentence summary" beats
   "write clearly."
2. **Scoped correctly.** Account-wide = things true of *you* everywhere (role,
   terminology, tone). Project = things true of *this work*.
3. **Prioritized.** When instructions could conflict, say which wins ("If the client
   style guide conflicts with these instructions, follow the style guide").
4. **Bounded.** Include what Claude should *not* do and when to defer to a human —
   e.g., "flag, don't fix, anything that looks like a legal claim."
5. **Maintained.** Instructions are configuration, not prose art: date them, review them
   when the underlying process changes (see 5.4).

### Common anti-patterns (frequent wrong-answer bait)

- **Stuffing knowledge into instructions:** pasting a 40-page policy into project
  instructions instead of uploading it to project knowledge and referencing it.
- **Contradictory layers:** account instructions say "be brief," project instructions
  say "be exhaustive," and nobody said which wins.
- **Untestable adjectives:** "be smart, insightful, and world-class."
- **Relying on the project title:** remember, Claude cannot see the project name or
  description.
- **Expecting cross-chat carryover:** deciding something in one project chat and
  assuming other chats in the project now know it. They don't — update the instructions
  or knowledge base.

### Memory: a related persistence surface (know the boundaries)

Claude's **memory from chat history** generates a summary of key context from your
conversations (role, projects, communication and technical preferences, ongoing work).
Verified behaviors worth knowing for the exam:

- The memory synthesis is **updated every 24 hours**; you can also tell Claude in-chat
  what to remember, which applies immediately to your next conversation.
- **Each project has its own separate memory space and summary**, distinct from
  non-project chats — moving a chat into or out of a project changes which summary it
  feeds.
- Users can **view and edit** the memory summary (Settings > Capabilities > "View and
  edit memory"), **pause** memory (kept but unused), or **reset** it (permanent,
  irreversible deletion, including project memories).
- **Incognito chats** are not saved to history, don't contribute to memory, and aren't
  pulled into past-chat searches.
- Enterprise Owners can disable memory org-wide; doing so **permanently deletes all
  memory data for all users** in the organization. (Plan availability for memory and
  chat search has shifted over time — check the current help article.)

Distinguish for learners: **memory is automatic and inferred; instructions and project
knowledge are deliberate and curated.** For anything that must be reliably true in every
chat (a compliance rule, a format requirement), configure it explicitly — don't hope
memory picks it up.

---

## 5.4 Inform, maintain, and update configurations, knowledge sources, and instructions

Configuration is a lifecycle, not a one-time act. The exam frames this as *keeping
Claude's context trustworthy over time*.

### Keeping knowledge sources current

- **Static uploads go stale silently.** A PDF uploaded in January still says January in
  July. Establish a review cadence: after any process/policy change, and on a schedule
  (e.g., quarterly), re-upload changed documents and **remove superseded versions** —
  outdated knowledge is worse than missing knowledge because Claude will confidently
  use it.
- **Prefer syncing sources for volatile content.** Google Docs added via the Drive
  connector sync to the latest version automatically; GitHub project knowledge updates
  when you click Sync. For fast-changing material, a synced source beats a static
  upload; for point-in-time material (a signed contract), a static upload is correct.
- **Name and describe files meaningfully** and reference them from the project
  instructions so users (and Claude) know what each source is for and which is
  authoritative.
- **Prune.** Anthropic's GitHub guidance applies generally: avoid unnecessary files to
  stay within token limits and keep the project focused. On paid plans RAG expands
  capacity, but irrelevant content still degrades focus and makes maintenance harder.

### Maintaining instructions

- Treat instructions like versioned configuration: keep a change log (even a dated line
  at the top), and update them when the team's workflow, audience, or standards change.
- In shared projects, restrict *Can edit* to designated maintainers; everyone else gets
  *Can use*. Remember that **archiving resets sharing to private** — re-share
  deliberately if you unarchive.
- When behavior drifts (Claude stops following an instruction it used to follow), first
  check for **conflicts between layers** and for knowledge files that contradict the
  instructions — then simplify.

### Maintaining connectors and access

- Periodically review Customize > Connectors: disconnect unused services; re-check tool
  permissions after org policy changes.
- If a connected document or repo becomes inaccessible (permissions revoked), its
  content stops being viewable in the project — previews are removed while chat history
  remains. Broken sources should be replaced or removed, not left dangling.
- After team changes (offboarding, role changes), verify project sharing lists and
  connector authorizations still match reality.

### Informing users of the configuration

"Inform" in the objective means making the configuration **legible**: document in the
project description (for humans — Claude can't read it) or in a knowledge file what the
project is for, what sources it contains, who maintains it, and when it was last
reviewed. On Team/Enterprise plans, shared projects are the distribution mechanism —
users find them in "Shared with me" and get email notifications when added.

---

## Trainer notes

### Teaching tips

- **Anchor everything to the two-question test:** "Is this *how to behave* (instruction)
  or *what to know* (knowledge)? Is it needed *everywhere* (account), *in this project*
  (project), or *just now* (chat)?" Most Domain 5 items reduce to these two questions.
- Show, don't tell: put a weak instruction set and a strong one side by side and have
  the class predict failure modes of the weak one before revealing them.
- Use the Gmail "draft but never send" behavior and the "each action needs explicit
  approval" pattern as memorable examples of Anthropic's human-in-the-loop design —
  they recur as correct-answer logic in connector questions.
- Be candid that plan availability and UI labels change; teach the *concepts*
  (permission inheritance, sync vs. static, scope layering) as the durable knowledge
  and the Help Center as the source of truth for details.
- Cross-link domains: connector permissions and data handling foreshadow Domain 6;
  "why is Claude ignoring my instruction?" foreshadows Domain 7.

### Discussion prompts

1. Your team pasted the entire employee handbook into project instructions "so Claude
   never forgets it." What problems do you predict, and how would you restructure it?
2. A colleague wants to connect Gmail and Drive to a *shared* Team-plan project so
   everyone can use their mailbox context. What actually happens, and what would you
   propose instead? (Hint: connectors are only available in private projects on
   Team/Enterprise, and permission inheritance means each user only sees their own data.)
3. When is a static file upload *better* than a synced Google Doc as a knowledge
   source? When is it worse? Give one real example of each from your own work.
4. Memory, account-wide instructions, project instructions, project knowledge: for each,
   name one piece of information from your job that belongs there — and one that
   definitely does not.
5. An Enterprise Owner is considering disabling memory org-wide. What are the
   irreversible consequences, and what would you want them to communicate first?

### Common misconceptions

- **"Claude reads the project name and description."** It does not — that metadata is
  for humans. Context must be in instructions or knowledge.
- **"Chats inside a project share context with each other."** They don't; only project
  knowledge and instructions persist across a project's chats.
- **"Connecting Gmail lets Claude send email for me."** Verified: Claude creates drafts
  only; sending is always manual.
- **"A connector can reach files I can't."** Never — Claude inherits your permissions
  from the source system; Claude-side restrictions only narrow access further.
- **"Uploaded knowledge stays current."** Static uploads are snapshots; only connector-
  synced sources (e.g., Google Docs, GitHub with Sync) track the source.
- **"Memory is a reliable place for must-follow rules."** Memory is inferred and
  editable but not a compliance mechanism; hard requirements belong in explicit
  instructions.
- **"Instructions and knowledge are interchangeable."** Instructions steer behavior;
  knowledge supplies facts. Misplacing one as the other is the classic Domain 5 error.

### Hands-on classroom exercise: live-build a Project (30–40 min)

1. **Scenario (5 min):** the class is the "RFP Response Desk" for a fictional agency.
   Provide three seed files: a style guide, a boilerplate company profile, and last
   quarter's (now partly outdated) pricing sheet.
2. **Build (10 min):** live-create a Project. Have the class dictate project
   instructions; deliberately accept a bad first draft ("be professional and use our
   documents"), run a test prompt, critique the output.
3. **Iterate (10 min):** rewrite instructions with role, audience, format, file
   references, and a "never invent pricing; flag for account manager" constraint.
   Upload the two stable files to project knowledge; keep a sample RFP as a
   *single-chat* upload and discuss why it doesn't go in knowledge.
4. **Maintenance twist (5–10 min):** announce "pricing changed this morning." Ask the
   class what must happen (remove/replace the stale sheet; note why a synced Google Doc
   might have been the better choice; who on a shared project has *Can edit* to do it).
5. **Debrief:** map each step back to the four blueprint objectives.

---

## Practice questions

> These are original practice items written in the style of the CCAO-F exam guide's
> sample questions. **They are not real exam items** and are not drawn from any live
> item bank. Each item states how many responses to select.

**Q1.** (Select ONE) An operations lead creates a project named "Vendor Contracts —
Follow the escalation rules in the description" and writes detailed escalation rules in
the project description field. In chats, Claude never applies the rules. What is the
most likely cause?

A. The project needs to be archived and unarchived to refresh its configuration.
B. Claude does not have access to the project name or description; the rules must go in
project instructions or knowledge.
C. Escalation rules are only supported on Enterprise plans.
D. The rules must be repeated in every chat because projects cannot store instructions.

**Q2.** (Select ONE) A marketing team keeps a 60-page brand guide, a glossary, and
each week's one-off campaign brief. Which placement best follows configuration best
practices?

A. Paste all three into project instructions so they are never forgotten.
B. Upload all three to project knowledge, replacing the campaign brief weekly.
C. Put the brand guide and glossary in project knowledge, keep the weekly brief as a
single-chat upload, and use project instructions to define tone, format, and how to use
the knowledge files.
D. Attach all three files to each individual chat to keep the project lightweight.

**Q3.** (Select ONE) An associate connects the Gmail connector and asks Claude to
"reply to the client confirming the meeting." What will Claude do?

A. Send the reply immediately from the associate's Gmail address.
B. Send the reply only after the associate approves the send action in Claude.
C. Create a draft in the associate's Gmail account; the associate must send it manually
from Gmail.
D. Refuse, because the Gmail connector is read-only.

**Q4.** (Select ONE) On a Team plan, an Owner enables the Google Drive connector for
the organization. A new analyst opens Claude and asks it to search Drive, but nothing is
retrieved. What is the most likely reason?

A. Drive connectors require an Enterprise plan.
B. The analyst has not yet authenticated individually with their Google account;
enabling a connector at the org level does not grant user access by itself.
C. The Owner must also upload the analyst's Drive files to a shared project.
D. Claude can only access Drive files created after the connector was enabled.

**Q5.** (Select TWO) A compliance officer wants Claude to help staff summarize email
and reference policy documents, while minimizing the risk of Claude modifying anything
in connected systems. Which TWO measures directly support this on a Team/Enterprise
plan?

A. Configure org-wide tool permissions on the connectors so write/delete actions are
Blocked or Needs approval while read tools remain allowed.
B. Ask each user to add "please don't modify anything" to their account-wide
instructions as the enforcement mechanism.
C. Rely on the fact that Claude inherits each user's source-system permissions, and
disconnect connectors that are no longer needed.
D. Enable memory so Claude remembers not to modify systems.
E. Share one manager's authenticated connector session with the whole team.

**Q6.** (Select ONE) A project's knowledge base contains a pricing PDF uploaded in
January and a pricing Google Doc added via the Drive connector. Prices changed in June.
In July, which statement is accurate?

A. Both sources reflect June prices, because project knowledge refreshes automatically.
B. Neither source reflects June prices until the project is re-created.
C. The Google Doc reflects the latest version because connector-added Docs sync from
Drive, while the static PDF still shows January prices and should be replaced or removed.
D. The PDF updates automatically, but the Google Doc is frozen at the moment it was
added.

**Q7.** (Select ONE) A consultant wants Claude to always use her preferred
methodology terminology in every conversation, and additionally to adopt a strict
plain-language style only for chats in her "Community Newsletter" project. What is the
best configuration?

A. Put both requirements in the newsletter project's instructions.
B. Put both requirements in account-wide "Instructions for Claude."
C. Put the terminology preference in account-wide instructions and the plain-language
requirement in the newsletter project's instructions.
D. Repeat both requirements at the start of every chat, since persistent instructions
are unreliable.

**Q8.** (Select ONE) In one chat inside a project, a team agrees with Claude on a new
report format. The next day, a colleague opens a new chat in the same project and Claude
uses the old format. What is the most appropriate fix?

A. Report the issue as a memory synchronization bug.
B. Update the project instructions (or add the format spec to project knowledge), since
context from one chat does not carry over to other chats in the project.
C. Tell the colleague to continue working inside the original chat forever.
D. Reset Claude's memory so it rebuilds with the new format.

### Answers

**Q1 — B.** Anthropic's help documentation states Claude will not have access to the
project name and description; those fields are for human organization. Behavioral rules
belong in project instructions (applied to all chats in the project) or, if lengthy
reference material, in project knowledge. A and C are invented mechanics; D is false —
storing instructions is exactly what projects do.

**Q2 — C.** Stable, reusable reference material (brand guide, glossary) belongs in
project knowledge; disposable weekly input stays a single-chat upload; instructions
define behavior and point at the knowledge files. A confuses instructions with
knowledge; B churns the knowledge base with one-off content; D forfeits the persistence
benefit projects exist to provide.

**Q3 — C.** Verified connector behavior: Claude can create drafts in Gmail but cannot
send email on the user's behalf — the send function is not enabled, and all emails must
be sent manually from Gmail. B is wrong because no approval flow enables sending; D is
wrong because drafting/labeling are write-ish capabilities, so the connector is not
purely read-only.

**Q4 — B.** On Team and Enterprise plans, an Owner enabling a connector makes it
available but grants no one access; each person must authenticate with the third-party
service individually (except under enterprise-managed auth, which the scenario doesn't
describe). A is false (Google Workspace connectors are broadly available); C misreads
how connectors work; D is invented.

**Q5 — A and C.** Owners can restrict connector actions org-wide (Always allow / Needs
approval / Blocked per permission category), e.g., allow reading email but block writes
— and these restrictions can't be overridden by individual users. Connector hygiene
(least footprint, permission inheritance from the source system) is the complementary
control. B and D rely on soft, non-enforcing mechanisms; E violates the per-user
authentication model and basic access hygiene.

**Q6 — C.** Google Docs added to chats and projects via the Drive connector sync
directly from Google Drive, so Claude works with the latest version; a static PDF upload
is a snapshot that must be manually replaced. This is the core "keep knowledge sources
current" behavior: prefer synced sources for volatile content and prune stale uploads.

**Q7 — C.** Scope each instruction at the narrowest level that covers all needed
contexts: account-wide "Instructions for Claude" apply to all conversations
(terminology), while project instructions apply only to chats in that project
(plain-language style for the newsletter). A leaks nothing to other chats where
terminology is needed; B forces plain language everywhere; D discards the persistence
features entirely.

**Q8 — B.** Context is not shared across chats within a project unless it is added to
the project knowledge base (or instructions). The durable fix is to encode the agreed
format in project instructions or knowledge so every chat inherits it. A and D
mislocate the issue in memory; C doesn't scale and defeats the purpose of project-level
configuration.

---

## Sources

Official Anthropic Help Center articles verified for this module (fetched July 2026):

- What are projects? — https://support.claude.com/en/articles/9517075-what-are-projects
- How can I create and manage projects? — https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects
- Understanding Claude's personalization features — https://support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features
- Use connectors to extend Claude's capabilities — https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities
- Use Google Workspace connectors (Gmail, Google Calendar, Google Drive) — https://support.claude.com/en/articles/10166901-use-google-workspace-connectors
- Use the GitHub integration — https://support.claude.com/en/articles/10167454-use-the-github-integration
- Use Claude's chat search and memory to build on previous context — https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context

Product details evolve; learners should confirm current behavior against these articles
before the exam.
