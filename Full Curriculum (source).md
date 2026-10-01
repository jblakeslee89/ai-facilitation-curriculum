# RAND AI Facilitation Group: Curriculum

Six biweekly sessions from September to December, with a seventh slot in January for a topic the group picks. Each session has a facilitator plan followed by a one-page participant handout. The first five sessions are sequenced so that participants can use AI as a study aid for the qualifying exams in November.

**Working assumptions** (edit if wrong):
- 90-minute sessions; each plan flags what to cut for 60.
- Sessions are scheduled on Thursday and Friday pairs, every other week. A session that needs more room (the build session, especially) can use both days.
- Participants have enterprise access to a frontier model with file upload, code execution, and a deep-research mode. Plans are written tool-agnostic; swap in the RAND-approved product.
- Sessions run virtually. Everyone joins from a machine they can screen-share from, with one live project open (thesis chapter, RAND task, lit review, qual reading). Breakout rooms handle pair work; a shared doc or Miro board stands in for the whiteboard. Each plan carries ready-made materials for anyone who arrives without a project.
- A shared running document ("the Playbook") captures what worked, what broke, and what the model lied about. By the last session it is the group's own RAND-specific reference.

**Schedule**
| Dates | Session | Topic |
|---|---|---|
| Sep 17 & 18 | 1 | Prompting as Spec-Writing, and Attribution |
| Oct 1 & 2 | 2 | Documents, Context Rot, and How Models Fail |
| Oct 15 & 16 | 3 | Code Over Arithmetic |
| Oct 29 & 30 | 4 | Agents, Subagents, and Cost |
| Nov 12 & 13 | 5 | Skill Docs, with Quals in View |
| Nov 26 & 27 | No session | Quals and Thanksgiving |
| Dec 10 & 11 | 6 | Build Something, and the Critic in the Room |
| Dec 24 & 25 | No session | Holiday |
| Jan 7 & 8 | 7 | Topic the group picks |

**Standing structure**
| Block | Time | What happens |
|---|---|---|
| Cold open | 10 min | One pre-assigned person demos something they did with AI since last session. Real work only. |
| Core | 45–60 min | One technique, hands-on, on each person's own project. Facilitator drops into breakout rooms. |
| Debrief | 10–15 min | What worked, what broke, where the model lied. Every failure gets a bin from the taxonomy in Handout 2. Someone logs it in the Playbook. |
| Homework | 2 min | Apply the technique to something real before next session. |

**Facilitation notes**
- Assign the cold-open demo at the *end* of the prior session, not the start of the current one.
- When someone asks a question you don't know, put it to the room first, then to the model, then to the Playbook as an open item.
- Keep a "Lies Log" section in the Playbook. Every confident, wrong model output goes in it with the prompt that produced it and its bin. This becomes the best teaching material you have.

**Changes from the first draft** (reviewer notes, September 10)
- Sessions reordered so documents and code come before agents, and the foundation is in place before quals.
- Attribution and disclosure (old Session 7) now sit in Session 1, since they are ground rules.
- The failure taxonomy and pre-flight checklist (old Session 8) now live in Session 2's handout and in every debrief.
- The editing passes (old Session 7) now sit in Handout 6, as a way to evaluate a build's output.
- The critic moves (old Session 5) now run inside the build session as the critique format.
- Tiering, effort, and cost (old Session 2) now pair with agents in Session 4.

---

## Session 1: Prompting as Spec-Writing, and Attribution

**When:** Sep 17 & 18

**Goal:** Participants stop writing one-line prompts and start writing specifications: context, constraints, examples, output format, success criteria. They also leave knowing what RAND's AI-use policy says about attribution and disclosure.

**Why first:** Everything downstream (documents, data, agents) fails quietly if the ask is vague. Most people who "know the basics" have never seen their own prompt history critiqued. And nobody should spend a term guessing what they are allowed to do.

### Ready-made materials

*Use these when nobody has their own. Everything here is public or was written for this course.*

- **The policy:** Screen-share the current RAND AI-use policy and read the relevant passages aloud.
- **Bad prompt for the cold open:** `Summarize this report.` Run it on the GAO High-Risk Series update (free at gao.gov/high-risk-list; also the document for Session 2).
- **The rewrite:** `I'm a RAND policy analyst drafting a two-page brief for congressional appropriations staff. Attached is GAO's latest High-Risk Series update. Summarize what changed since the previous update: areas added, removed, or with a changed rating. Under 250 words. Only claims GAO itself makes; no recommendations of your own. Output: a three-column table (area, what changed, page cite), then one paragraph on the overall trend.`
- **Three bad prompts for anyone with no history to excavate:** `Is this methodology sound?` with nothing attached. `Write a lit review on sanctions effectiveness.` `Make this better,` followed by any paragraph.

### Plan (90 min)

**Cold open (10):** You demo, since nobody has homework yet. Show one prompt you wrote badly and the rewrite. Set the tone: this group is about failure as much as success.

**Core (55):**
1. *Policy and attribution (10).* Screen-share the RAND AI-use policy. Read the relevant passages together. Answer: what must be disclosed, to whom, and when? What is prohibited? What data cannot go into which tools? Where is it silent? Nobody should leave guessing.
2. *Excavation (10).* Everyone opens their chat history and copies their three most recent real prompts into a scratch doc. No cleanup.
3. *The five parts (10).* Introduce the spec frame on a shared screen. A good prompt usually has: **Role/context** (who is the reader, what is the project), **Task** (one verb, one object), **Constraints** (length, sources, tone, what to exclude), **Examples** (one good, one bad if possible), **Output shape** (table, memo, bullets, JSON). Not every prompt needs all five; every prompt should have consciously skipped the ones it skips.
4. *Rewrite (15).* Each person rewrites one of their three prompts against the frame and runs both versions. Same model, same session type.
5. *Pairs (10).* Breakout rooms in pairs; each person shares their screen. Partner reads both outputs cold and says which is better and why, before seeing which prompt produced it.

**Debrief (10):** Round the room: what changed most? Usually it's output shape or the missing "who is this for." Log two or three before/after pairs in the Playbook.

**Homework:** Rewrite one real prompt per day this week. Bring the one where the rewrite made the *smallest* difference; that's the interesting case.

**For 60 min:** Cut the pairs step; do rewrites solo and debrief directly. Cut the policy block to five minutes and assign the rest as reading from the handout.

### Facilitator watch-outs
- Someone will say "I just iterate in conversation instead." Fine, but ask them to count turns. A spec upfront usually saves five.
- Pushback on "examples" as too much work. Point out that one example of the output shape often beats three paragraphs of description.
- Someone will ask whether using the model as an editor requires disclosure. Answer from the policy, not from opinion. If the policy is unclear, log it as a question to raise upward.

---

### HANDOUT 1: Prompting as Spec-Writing, and Attribution

**The idea in one line:** You are briefing a very fast, very literal colleague who has never met you.

**The five parts**
| Part | Ask yourself | Example fragment |
|---|---|---|
| Context | Who is this for? What project? | `I'm drafting a RAND research brief for a congressional staffer audience.` |
| Task | One verb, one object | `Summarize the methodological limitations of this study.` |
| Constraints | Length, sources, tone, exclusions | `Under 300 words. Only limitations the authors themselves acknowledge. No recommendations.` |
| Examples | What does good look like? | `Here is a paragraph in the house style: [paste].` |
| Output shape | Table? Memo? Bullets? | `Three-column table: limitation, page cite, severity.` |

**Quick wins**
- Say who the reader is. It changes vocabulary, length, and what gets left out.
- Give the model permission to say "not in the document." Otherwise it will invent.
- Ask for the output shape you will paste into your own work. Reformatting is wasted time.
- If you'd need to give a human an example, give the model one.

**Attribution and disclosure**
RAND's AI-use policy governs what you may do, and we read it together in Session 1. Know: what must be disclosed, where, and to whom; what's prohibited; what data can't go into which tools. If it's unclear, ask before you're asked. The words under your name are yours.

**Pitfalls**
- Compound asks ("summarize, critique, and rewrite") get mediocre results on all three. Split them.
- "Be concise" without a number means nothing. Say 200 words.
- Politeness costs nothing but adds nothing. Clarity is the courtesy.

**Go deeper**
- The RAND AI-use policy, as read in Session 1.
- Anthropic prompt engineering guide: https://docs.claude.com/en/docs/build-with-claude/prompt-engineering/overview
- OpenAI prompt engineering guide: https://platform.openai.com/docs/guides/prompt-engineering
- Ethan Mollick, *One Useful Thing* (practical, non-engineer): https://www.oneusefulthing.org

---

## Session 2: Documents, Context Rot, and How Models Fail

**When:** Oct 1 & 2

**Goal:** Participants learn that "the model accepted the file" and "the model read the file" are different claims, and that a bigger context window is a bigger bucket, not a better reader. They leave with the group's taxonomy of model failure, which every later debrief uses.

**Why:** Half of RAND inputs are long PDFs with tables, footnotes, and scanned pages. This is where confident, wrong answers come from, so it is the right place to learn the patterns those answers follow.

### Ready-made materials

*Use these when nobody has their own. Everything here is public or was written for this course.*

- **The document:** GAO's latest High-Risk Series update (gao.gov/high-risk-list). Long, with summary tables, dense footnotes, and an appendix. Download the PDF, then get the text layer with copy-paste or a converter.
- **The three questions:** Before the session, pick one table cell and one footnote and write down the answers. Table: `How many high-risk areas are on the list this cycle, and how many were added?` Footnote: ask about the one you picked. Argument: `In one paragraph, what is GAO's overall assessment of progress since the last update?`
- **Filler for the context rot demo:** Forty pages of the report's own appendix, or any long Federal Register notice. Bury the page with the table in the middle for the second run.
- **Reproducible failures, one per bin:** Fabrication: `Give me five peer-reviewed papers on sanctions and remittance flows, with DOIs.` Open two. Misreading: the table question above, asked of the PDF. Overreach: ask the GAO report about a topic you have confirmed it does not cover. Drift: the long thread from the context rot demo, with a new question. Sycophancy: `Since the Federal Reserve sets fiscal policy, how should it respond to the deficit?` Silent substitution: `Summarize only the footnotes on pages 10 to 20.` Watch it summarize the body.

### Plan (90 min)

**Cold open (10):** Prompt rewrite homework demo.

**Core (55):**
1. *Same document, three formats (15).* Each person uploads the GAO report as PDF, pastes the text as plain text, and (if possible) converts it to markdown. Ask the same three questions of each: one about a table value, one about a footnote, one about the overall argument. Compare. The table question usually breaks the PDF version.
2. *Context rot, live (15).* Take a short question the model answered correctly in a fresh chat. Now paste 40 pages of unrelated material first, then ask again. Then try with the relevant page buried in the middle of the 40. Show the degradation. Name it: performance falls as context grows, and information in the middle gets lost.
3. *Hygiene (10).* Three habits: (a) start a fresh conversation when the topic shifts; (b) ask the model to write a summary of state before continuing a long thread, then start a new thread from that summary; (c) extract first, reason second: pull the relevant sections into a clean document before asking the hard question.
4. *Six ways it goes wrong (15).* Introduce the bins: **fabrication** (invented citation, number, quote); **misreading** (table, footnote, scanned page); **overreach** (answered a question the source didn't address); **drift** (long conversation, stale instruction); **sycophancy** (agreed with a bad premise); **silent substitution** (did a different, easier task). Run two or three of the reproducible failures live. Then the room sorts everything that went wrong in steps 1 and 2 into bins, and proposes one catch per bin.

**Debrief (10):** Which format won for which question? Log a "file format guide" in the Playbook. Every misread goes in the Lies Log with its bin. Write the bins and catches into the Playbook as a one-page checklist; this is the group's first real artifact.

**Homework:** Take one document you'd normally just upload. Convert it, chunk it, or extract from it first. Note whether the answers change. Use the pre-flight on everything for two weeks, and bring the failure it didn't catch.

**For 60 min:** Cut the hygiene block to a five-minute talk; assign it as reading from the handout. Introduce the bins from the handout table without the live demos.

### Facilitator watch-outs
- Scanned PDFs (image-only) are the extreme case. If you have one, show it; the model may see nothing and still answer.
- Someone will note their tool has a million-token window. Point them to the Chroma study: every model tested degraded with length.
- Some failures will be user error dressed as model error. Handle gently; ask "what would the spec have needed to say?" rather than assigning blame.

---

### HANDOUT 2: Documents, Context Rot, and How Models Fail

**The idea in one line:** Accepting a file is not reading it, and models fail in patterns you can learn.

**File formats, roughly**
| Format | What happens | Use when |
|---|---|---|
| Plain text / markdown | Cleanest read; structure preserved if headers are marked | Always, if you can get it |
| PDF (text layer) | Usually fine for prose; tables, footnotes, and multi-column layouts often scramble | Prose-heavy documents |
| PDF (scanned image) | Model may see little or nothing and still answer confidently | Avoid; OCR first |
| .docx / .odt / spreadsheets | Depends on the tool's converter; check a known value | Confirm before trusting |

**Three habits**
1. **Fresh threads.** New topic, new conversation. Long chats accumulate stale instructions.
2. **Summarize and restart.** In a long thread: `Write a 200-word summary of where we are and what's decided.` Paste that into a new chat.
3. **Extract, then reason.** Pull the relevant pages or table into a clean document first. Ask the hard question of the small document.

**Six ways it goes wrong**
| Failure | What it looks like | The catch |
|---|---|---|
| Fabrication | Invented citation, quote, number, URL | Verify two citations at random. If one fails, verify all. |
| Misreading | Table value wrong, footnote missed, scan unread | Ask one question you know the answer to. |
| Overreach | Answers a question the source doesn't address | `What in the source supports this? Quote it.` |
| Drift | Long conversation, old instruction still active | Fresh thread. Summarize and restart. |
| Sycophancy | Agrees with your bad premise | `Argue that my premise is wrong.` |
| Silent substitution | Did an easier, adjacent task | `Restate the task you completed in one sentence.` |

**The pre-flight**
Before trusting any output you'll use:
1. Does it answer what I asked, or something nearby?
2. Can I point to where each key claim came from?
3. Did I check one thing I already knew?
4. Is this conversation older than the topic?

**Pitfalls**
- Uploading twelve documents and asking one question. Retrieval gets worse with each file.
- Assuming the failure was the model's. Often the spec was missing a constraint. Check the spec first.
- Not telling anyone. A failure you hide is a failure the next person repeats. Log it.

**Go deeper**
- Chroma, "Context Rot" (the study): https://www.trychroma.com/research/context-rot
- Liu et al., "Lost in the Middle" (the earlier paper): https://aclanthology.org/2024.tacl-1.9/
- Anthropic, "Effective context engineering for AI agents" (why context is a finite resource): https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- The group Playbook, Lies Log section.

---

## Session 3: Data Work, and Deterministic Code Over Model Arithmetic

**When:** Oct 15 & 16

**Goal:** Participants stop asking the model to count, compute, or aggregate in its head, and start asking it to write code that does so. Then they learn to read the code.

**Why:** This is the single best hallucination defense for quantitative work. The model's reasoning is probabilistic; a script is checkable. It also opens code execution to non-programmers, which is where students get the most out of an hour.

### Ready-made materials

*Use these when nobody has their own. Everything here is public or was written for this course.*

- **The dataset:** SIPRI Military Expenditure Database (sipri.org/databases/milex), the share-of-GDP sheet: one row per country, one column per year. Real, free, and policy-relevant. Fallback if SIPRI is down: the World Bank indicator MS.MIL.XPND.GD.ZS as CSV.
- **The counting question:** `How many countries spent more than 2% of GDP on the military in the latest year?` Ask in prose three times, then `Write and run code that counts them, and print the list.` Then a chart: the fifteen highest shares as a bar chart.
- **For anyone without their own data:** Same file, different question: median share by region, or which countries crossed 2% in the last decade.

### Plan (90 min)

**Cold open (10):** Document homework demo, and the failure the pre-flight didn't catch.

**Core (50):**
1. *The demonstration (10).* Give the model a spreadsheet of 200 rows and ask "how many rows have value X in column Y?" in plain prose. Then ask it to write and run code that counts. Compare. Do it three times; the prose answer drifts, the code doesn't.
2. *Your own data (20).* Everyone brings a dataset (a CSV, a table pulled from a report, survey results). Task: get one descriptive statistic and one chart via code execution. Non-coders are told to ask the model to explain each line.
3. *Read the code (10).* Breakout pairs. Each person explains their partner's generated script back to them without running it. If you can't explain it, you can't trust it.
4. *Where the trick doesn't apply (10).* Discussion: a lot of RAND work is judgment (framing, synthesis, argument). The code trick fixes arithmetic, not thinking. Which of your tasks this week were arithmetic in disguise? Which were judgment?

**Debrief (10):** Log the "count in prose vs. count in code" discrepancy in the Lies Log. Start a "useful snippets" section in the Playbook.

**Homework:** Redo one analysis you've already done by hand or in Excel using generated code. Do the numbers match?

**For 60 min:** Cut step 4 to a two-minute framing statement; fold "read the code" into the debrief.

### Facilitator watch-outs
- Non-coders will freeze. The fix is the phrase "explain this to me one line at a time." Model it early.
- Someone will get a result that contradicts their Excel. That's the best possible outcome; spend the debrief there.

---

### HANDOUT 3: Data Work, and Deterministic Code Over Model Arithmetic

**The idea in one line:** Ask the model to write the thing that counts, then read what it wrote.

**Why it works**
The model produces text by prediction. When it "computes" in prose, it is predicting what the answer looks like. When it writes a script and runs it, the script does the computing. The script is deterministic: same input, same output, every time, and you can read it.

**The pattern**
1. `Write code that does X.` (Not "do X.")
2. `Run it and show me the output.`
3. `Explain each line in plain English.`
4. Spot-check one value against the source.

**Useful phrasings**
- `Before computing, print the column names and the first five rows so I can confirm you loaded it correctly.`
- `Add a sanity check: the counts should sum to the total row count.`
- `If any value is missing or malformed, stop and tell me rather than dropping it silently.`

**Where the trick applies**
Counting, filtering, joining, aggregating, plotting, reshaping, date math, string cleanup, anything Excel can do and then some.

**Where it doesn't**
Deciding what to count. Framing the question. Judging whether a result matters. Writing the paragraph that explains it. That's still your job, and the model is a critic there, not a calculator.

**Pitfalls**
- Trusting a chart you didn't inspect the code for. Axis choices lie.
- Letting the model "handle" missing data. Ask what it did.
- Skipping the read-the-code step because it worked. It worked *this time*.

**Go deeper**
- The code execution or data analysis documentation for the RAND-approved tool.
- Simon Willison on using LLMs for code, including for non-programmers: https://simonwillison.net
- Ethan Mollick, *One Useful Thing*, on the "jagged frontier" of what models do well: https://www.oneusefulthing.org

---

## Session 4: Agents, Subagents, and Cost

**When:** Oct 29 & 30

**Goal:** Participants understand what an agentic workflow is, when splitting work across subagents helps, and why parallelism buys speed rather than judgment. Before typing, they ask three questions: What is this task worth? Which model or effort setting fits it? How much verification will the output demand?

**Why:** This is where "chatbot" becomes "tool," and also where errors multiply. Nate's point: firing off ten agents makes the work faster and harder to check, and no better. The same judgment applies one level down. Students default to one model at one setting for everything; fast cheap models are right for half of research work, and slow expensive ones are wrong for half of it too. "Cost" means money, wall-clock time, and how much checking the output will need.

### Ready-made materials

*Use these when nobody has their own. Everything here is public or was written for this course.*

- **The three documents:** The last three annual editions of the Department of Defense report to Congress on Military and Security Developments Involving the People's Republic of China (public, on defense.gov). Same topic, same structure, changing numbers.
- **The agentic task:** `Read these three reports. Extract every quantitative claim about the size of the PLA Navy into a table: claim, report year, page cite. Flag every place the editions disagree with each other.` The implicit decision to catch: what counts as a ship.
- **Manual version for tools without agents:** Assign one report per person, same table, then merge. The merge is where the parallel-reads lesson lands.
- **Question to run at two settings:** `A mid-sized city is considering a 1% payroll tax to fund a homelessness program. What are the three strongest objections an economist would raise, and what evidence would settle each?` Cheapest model, then highest effort. Time both.
- **Five tasks for the cost estimation game, with the tier to argue toward:** (1) Turn this bulleted list into a table: A. (2) Find the five most-cited papers on secondary sanctions since 2018: B, since you will verify every one. (3) Draft the limitations section of a survey-based study: C. (4) Explain fixed effects versus random effects in two sentences: A, or B if you are going to teach it. (5) Read these three DoD reports and tell me where they disagree: B and agentic; the disagreements need checking. Expect a fight over 4 and 5.

### Plan (90 min)

**Cold open (10):** Data homework demo.

**Core (60):**
1. *What an agent is (10).* Screen-share a simple diagram: an agent is a model in a loop with tools. It reads, acts, observes, repeats. Every step is a chance to be wrong; every step is also something you can inspect.
2. *One task, agentically (15).* Everyone gives the model the three-report extraction task with file access. Watch it work. Note where it skipped. Show how to read the trace, step by step; if your tool hides it, that's a limitation worth knowing.
3. *The intern analogy (10).* When would you split a research task across five interns? (Independent reads: five countries, five years.) When would that make it worse? (Anything requiring a shared understanding of the argument.) Subagents are the same. Reading parallelizes; writing and judgment don't. The real win connects to Session 2: each subagent gets a fresh context, so the main thread doesn't rot, and that only holds if the subtasks are truly independent.
4. *The three tiers (15).* Build a task ladder live in the shared doc. **Tier A, disposable:** reformatting, quick definitions, "what's another word for." Cheapest, fastest model, minimal checking. **Tier B, consequential but checkable:** lit search scoping, first-draft summaries, code you'll run and inspect. Mid-tier model or extended thinking; verify the parts you'll use. **Tier C, judgment-heavy:** methods critique, framing a research question, anything going into a deliverable under your name. Best model, high effort, and the output is a draft you own, not an answer. Then everyone runs one real question at the cheapest setting and the highest, and times both. Note the differences honestly; sometimes there aren't any.
5. *Cost estimation game (10).* Read out five tasks; everyone types a tier (A, B, or C) into chat at the same time. Argue the borderline ones. Where does "agentic" sit on the ladder? Usually B, sometimes C, never A.

**Debrief (10):** What did the agent skip? Where did it decide something you'd have wanted to decide? Where did the expensive setting earn its cost, and where was it identical? Log both. Start a "tiering guide" section in the Playbook.

**Homework:** Run one agentic task and one manual version of the same task. Which was faster? Which was right? Tag each AI task you do this week A/B/C before you run it, and notice when you were wrong.

**For 60 min:** Cut the cost game; fold the tiers into a five-minute framing statement after the intern analogy.

### Facilitator watch-outs
- The agent will make an implicit decision (which claims count as "quantitative," how to resolve a conflict). Catch one live; that's the lesson.
- If participants don't have agentic tools, simulate: run the steps manually in sequence and discuss where a loop would have helped and where it would have hidden a mistake.
- The interesting finding on tiers is usually that the cheap model was fine for more than expected. Let that land; don't rush to defend the frontier model.
- If RAND's tool exposes only one model, run the tier exercise on effort/thinking settings and conversation length instead.

---

### HANDOUT 4: Agents, Subagents, and Cost

**The idea in one line:** Loops multiply both capability and error, so decide what a task is worth before you choose the tool.

**When agentic helps**
- The task has steps a human would also take (find, read, extract, compare).
- Each step produces something inspectable.
- You'd rather review a trace than do the steps yourself.

**When it hurts**
- The task is one judgment call dressed up as a process.
- You can't see what the agent did between input and output.
- Speed is the only benefit, and you'll spend the saved time checking.

**Subagents: the intern test**
Would you split this across five interns who can't talk to each other? Five independent reads (countries, years, documents): yes. One argument that needs shared understanding: no. Reading parallelizes. Writing and judgment don't. Parallel agents make implicit, conflicting decisions, and someone has to reconcile them: you. The real benefit is that each subagent gets a fresh context, so the main thread doesn't rot (Handout 2).

**Three tiers**
| Tier | What it is | Right tool | Checking required |
|---|---|---|---|
| A: Disposable | Reformatting, quick lookups, phrasing | Fastest, cheapest model | Glance |
| B: Consequential, checkable | Scoping a lit search, first-pass summaries, code you'll run, agentic extraction | Default model or extended thinking | Verify what you'll use |
| C: Judgment | Methods critique, framing, anything under your name | Best model, high effort | Treat as a draft you own |

**Cost has three parts**
1. Money and tokens (usually the smallest).
2. Your wall-clock time waiting.
3. Verification burden: how long it takes to confirm the output is right. This dominates for Tier C, and for every agentic run.

**Inspection habits**
- Read the trace. If your tool doesn't show one, treat the output as Tier C.
- Ask the agent to list every decision it made that wasn't in your instructions.
- Spot-check the step most likely to fail (usually extraction from a table or a scanned page).

**Pitfalls**
- Assuming parallel means thorough. It means fast.
- Letting the agent resolve a disagreement between sources. That's your call.
- Ten agents, one reviewer. The reviewer is the bottleneck.
- Using the frontier model for reformatting, or the cheap model for anything you'll cite.
- Believing that more compute fixes a bad spec. It amplifies it.

**Go deeper**
- Anthropic, "Building effective agents": https://www.anthropic.com/research/building-effective-agents
- Anthropic, "How we built our multi-agent research system" (the case for parallel reads): https://www.anthropic.com/engineering/multi-agent-research-system
- Cognition, "Don't Build Multi-Agents" (the case against parallel writes): https://cognition.com/blog/dont-build-multi-agents
- LangChain, "How and when to build multi-agent systems" (reconciling the two): https://www.langchain.com/blog/how-and-when-to-build-multi-agent-systems
- Simon Willison's blog (running notes on model capabilities and costs): https://simonwillison.net

---

## Session 5: Skill Docs, with Quals in View

**When:** Nov 12 & 13

**Goal:** Participants build two reusable configurations: a "RAND analyst" skill (style, citation conventions, standard caveats, preferred workflows) and a "qual study partner" skill that quizzes them from their own readings without inventing anything. Both are files the model loads every time.

**Why:** Everything the group has learned lives in people's heads and the Playbook. A skill document puts it in the model's context on demand. It's also the closest thing to institutional memory a chat tool has. With quals two weeks out, the study-partner skill is the most immediately useful thing the group can build, and it exercises every rule from Sessions 1 through 4.

### Ready-made materials

*Use these when nobody has their own. Everything here is public or was written for this course.*

- **Starter RAND analyst skill doc, for the room to edit:**

```
# RAND analyst
Use when: drafting any RAND memo, brief, or summary.
Reader: a policy generalist with ten minutes.
Format: headers no deeper than three levels. Page-cite every factual claim as (Author, p. X).
Always: flag uncertainty. Separate what the source says from what you infer.
Never: invent a statistic. Resolve a conflict between sources without flagging it.
Lit review: extract claims to a table first, synthesize second.
```

- **Starter qual study partner skill doc:**

```
# Qual study partner
Use when: I am studying for the qualifying exam.
Sources: only the readings I attach. If the answer is not in them, say so.
Mode: quiz me. One question at a time. Do not give the answer until I have attempted it.
After each attempt: what I got right, what I missed, and the page in the reading that covers it.
Never: invent a citation. Agree with a wrong answer. Summarize a reading I have not attached.
```

- **Test task:** The Session 1 rewrite prompt on the GAO report, with and without the analyst skill loaded. Diff the two outputs. For the study partner: attach one qual reading and ask for five questions; check every page cite.

### Plan (90 min)

**Cold open (10):** Agentic-vs-manual homework demo.

**Core (50):**
1. *What a skill doc is (10).* A markdown file with instructions the model reads when relevant: who the reader is, what the output looks like, what to always do (page cites), what to never do (invent a number). Shown as a Project system prompt, a style file, or a formal skill folder depending on the tool. Progressive disclosure: a short description tells the model when to load it; the full file loads only then.
2. *Draft together (20).* Draft the "RAND analyst" skill live in the shared doc, one person driving. Sections: **Audience** (policymaker, researcher, public). **Output conventions** (headers, length, citation format). **Always** (flag uncertainty, cite page, distinguish source claims from inference). **Never** (invent statistics, resolve source conflicts silently, use jargon without defining). **Workflows** (for a lit review, do X then Y). Pull directly from the Playbook.
3. *The study partner (10).* The room edits the starter qual skill. The rules that matter: only attached readings; quiz mode, one question at a time; page cite with every correction. Everyone attaches one real qual reading and runs it.
4. *Load and test (10).* Each person installs one of the drafts in their tool and runs a task from earlier in the term with and without it. Did the output change? Where?

**Debrief (10):** What did the skill fix? What did it make worse (over-constrained, verbose caveats)? Iterate one round in the Playbook.

**Homework:** Write a personal skill doc for your own project, or refine the study partner for your quals. Bring it to the build session; it's your build, or the seed of one.

**For 60 min:** Skip drafting the analyst skill from scratch; the room edits the starter. Keep the study partner block.

### Facilitator watch-outs
- Skill docs bloat fast. Keep each draft under one page. The model reads long instructions the way it reads long documents: badly (Session 2).
- Someone will ask if this is just a long prompt. Sort of, with two differences: it's reusable, and it only loads when relevant, so it doesn't rot every conversation.
- Security note for the handout: only use skill files you wrote or trust. A skill is instructions the model will follow.

---

### HANDOUT 5: Skill Docs, with Quals in View

**The idea in one line:** Write down what you keep telling the model. Make it load automatically.

**What goes in a skill doc**
| Section | Example |
|---|---|
| When to use | `For any RAND deliverable, memo, or brief.` |
| Audience | `Default reader: a policy generalist with 10 minutes.` |
| Output conventions | `Headers, no more than 3 levels. Page-cite every factual claim as (Author, p. X).` |
| Always | `Flag uncertainty. Distinguish what the source says from what you infer.` |
| Never | `Invent a statistic. Resolve a conflict between sources without flagging it.` |
| Workflows | `Lit review: extract claims to a table first, synthesize second.` |

**For quals: the study partner**
Three rules do most of the work. Only the readings you attach, and "not in the readings" is an allowed answer. Quiz mode: one question at a time, no answer until you have tried. Every correction cites the page, and you check the page. Everything from Handouts 1 through 4 applies: it is a spec, the readings are documents, and the model will agree with a wrong answer unless told otherwise.

**Where it lives (depends on your tool)**
- A Project or custom instruction block.
- A style file you paste or attach.
- A formal skill folder (SKILL.md plus optional scripts and references) for tools that support the open Agent Skills format.

**Keep it short**
One page. The model reads long instructions the way it reads long documents: worse as they grow. If the file is getting long, split it: one skill per task type.

**Test it**
Run the same task with and without. If nothing changed, the skill isn't doing anything. If the output got verbose and caveat-heavy, you over-constrained.

**Security**
A skill is a set of instructions the model will follow. Only use skill files you wrote yourself or got from a source you trust, and read every file in the folder before installing.

**Pitfalls**
- Encoding preferences you haven't tested. Every line should have earned its place.
- One giant skill for everything. Split by task.
- Forgetting to update it. Revisit after every failure story.

**Go deeper**
- Anthropic Agent Skills documentation: https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview
- Anthropic skills repository, with a template: https://github.com/anthropics/skills
- Agent Skills open specification: https://agentskills.io
- Anthropic, "Effective context engineering" (why short, on-demand instructions beat long always-on ones): https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents

---

## Session 6: Build Something, and the Critic in the Room

**When:** Dec 10 & 11. This session can use both days: demos on the first, critique and the Playbook on the second.

**Goal:** Each participant ships one small artifact that uses what the group learned, demos it, and gets critiqued, with the model used as a reviewer rather than an author: steelman the opposing view, find the weakest claim, name what would change the conclusion. The group finalizes the Playbook.

**Why:** Ten weeks of technique are worth little without a made thing. The demos also give you evidence of what the group produced, useful for whoever asks whether it was worth running. And RAND has a peer-review culture: the model is a tireless, tactless first reviewer, and using it this way keeps the words yours.

### Ready-made materials

*Use these when nobody has their own. Everything here is public or was written for this course.*

- **Sample paragraph for the four moves:** Written for this course, deliberately hedged and contestable. `Export controls on advanced chips will likely slow China's frontier AI development for several years. Chinese labs currently depend on Nvidia hardware for large training runs, and domestic alternatives appear to lag by at least a generation. Although smuggling and cloud access may blunt the effect somewhat, it seems unlikely that these channels can substitute at scale. The controls therefore probably buy the United States meaningful lead time, which policymakers should use to build governance capacity. Some analysts argue the controls accelerate Chinese self-sufficiency, but this concern may be overstated given the difficulty of replicating the semiconductor supply chain.`
- **Reviewer to name:** `Review this as a RAND quality assurance reviewer would, then as a skeptical House Appropriations staffer would. Quote the sentence you are criticizing each time.`
- **Default build for anyone who arrives empty-handed:** The Session 5 skill doc plus the Session 3 script, turned into a repeatable workflow on the SIPRI data: load, count, chart, one paragraph of findings with page cites. Small enough to finish, real enough to critique.

### Plan (90 min)

**Cold open:** Skip; the session is the demo.

**Core (65):**
1. *The four moves (10).* Demo on the sample paragraph: (a) `Argue the opposite thesis as persuasively as you can.` (b) `Identify the three weakest claims and why a hostile reviewer would attack each.` (c) `What evidence would change this conclusion?` (d) `Rewrite this as the strongest version of the argument I am not making.` Show how "be brutal" produces performed brutality and "what would a reviewer who wanted to reject this say" produces substance.
2. *Ground rules (5).* Each demo: what problem, what you built, what the model did vs. what you did, what failed, three minutes. Then two minutes of critique: the demo's output goes through one of the four moves, live, and the builder says whether the critique is right and why.
3. *Demos (40).* Facilitator keeps time hard. Rule: nobody accepts a suggestion without being able to say why it's right.
4. *Playbook finalization (10).* Walk the Playbook as a group. Delete what didn't hold up. Tighten the failure checklist and the tiering guide. Decide who owns it going forward.

**Debrief (15):** Round the room: one thing you do differently now than in September. One thing you still don't trust. Close on the second list; it's the more honest one.

**Homework:** None. Or: teach one of these sessions to someone else. Pick the January topic.

**For 60 min:** Three-minute demos, one-minute critique, no Playbook walk (do it async). **Over two days:** demos on day one; critique round, editing passes from the handout, and the Playbook walk on day two.

### Facilitator watch-outs
- Demos run long. Share a timer on screen. Be the person who cuts off the demo, gently, every time.
- Sycophancy is the enemy. If the model praises the build, the prompt was wrong.
- Someone will find the model's critique wrong. Great: articulating why sharpens the argument anyway.
- The temptation is to end on triumph. End on the "still don't trust" list. It's what they'll remember.

---

### HANDOUT 6: Build Something, and the Critic in the Room

**The idea in one line:** Technique is worthless until it makes something, and a build isn't finished until someone has tried to break it.

**Your build, in five parts**
1. **Problem:** what recurring task did this fix?
2. **Build:** what did you make? (skill doc, script, pipeline, template)
3. **Division of labor:** what did the model do, what did you do, what did you check?
4. **Failure:** what went wrong along the way?
5. **Next:** what would you do with another week?

**Four moves**
| Move | Prompt | What it exposes |
|---|---|---|
| Steelman the opposition | `Argue the opposite thesis as persuasively as you can.` | Gaps in your case |
| Weakest claims | `Name the three weakest claims and how a hostile reviewer attacks each.` | Where to add evidence or cut |
| What would change your mind | `What evidence would overturn this conclusion?` | Whether your claim is falsifiable |
| The argument you're not making | `Write the strongest version of the case I've left out.` | Missing framing |

**Making critique specific**
- Name the reviewer: "a RAND QA reviewer," "a skeptical appropriations staffer," "a labor economist."
- Forbid praise: `Do not tell me what works. Only what doesn't.`
- Demand location: `Quote the sentence you're criticizing.`

**Editing the output**
| Pass | Prompt | Watch for |
|---|---|---|
| Compression | `Cut 30% without losing any claim.` | It cuts your best sentence |
| Hedge audit | `Flag every hedge. Which ones does the argument depend on?` | Some hedges are the finding |
| First 90 seconds | `Rewrite the opening for a reader with 90 seconds.` | Loss of nuance the reader needs |
Ask for a marked-up list, not a rewrite. Track what you reject.

**What you should now do differently**
- Write a spec, not a question. Know the disclosure rules. (Session 1)
- Extract before you reason; start fresh threads; run the pre-flight. (Session 2)
- Ask for code, not arithmetic; read the code. (Session 3)
- Parallelize reads, never judgment. Tier the task before choosing the tool. (Session 4)
- Put what you keep saying into a skill doc. (Session 5)
- Run an adversarial pass before you send. (Session 6)

**What you should still not trust**
- Any number the model computed in prose.
- Any citation you haven't opened.
- Any table read from a PDF you haven't spot-checked.
- Any conversation older than the topic.
- Any output that agrees with you too readily.

**Keeping it going**
- The Playbook has an owner, chosen in Session 6.
- Add to the Lies Log when the model gets you. Someone else will thank you.
- Re-run the failure sort in six months. The failure modes will have changed.

**Go deeper**
- Anthropic engineering blog: https://www.anthropic.com/engineering
- Simon Willison: https://simonwillison.net
- Ethan Mollick, *One Useful Thing*: https://www.oneusefulthing.org
- RAND's quality assurance standards for peer review.
- The group Playbook.

---

## Session 7: Topic the Group Picks

**When:** Jan 7 & 8

**Goal:** Decided by the group at the end of Session 6.

**Why:** By January the Lies Log, the tiering guide, and the quals will have shown where the real gaps are. Candidates, in rough order of likelihood: a second show-and-tell day for builds that weren't ready in December; a writing session that runs the editing passes and voice preservation on real drafts, with the policymaker one-pager (finding, so what, what to do, what we don't know) as the exercise; a re-run of the failure sort on the term's Lies Log; whatever quals revealed about the study partner skill.
