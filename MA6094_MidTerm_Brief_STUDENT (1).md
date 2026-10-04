# MA6094 — Agentic AI for Project Management
## Mid-Term Mini Project: Individual Prototype

**Weighting:** 30% of final grade · **Mode:** Individual · **Submission:** before Week 8
**Assesses:** ILO 1, 2, 3, 4 · **Rubric:** Analytic

---

## 1. What you are building

You will build and demonstrate **one** working AI-driven prototype that performs a single project
management function. Not a system. Not a suite. One function, built well enough that someone could
use it on a real project and defend the output to a sponsor.

The prototype must:

- perform a recognisable PM function end to end, from input to usable artefact
- read from or write to **at least one external tool or dataset** — it cannot live entirely inside a
  chat window
- apply agentic AI concepts from Weeks 1–7: structured prompting, chaining, tool calls, and at least
  one checkpoint where a human or a second step reviews the work
- be **evaluated by you**, against criteria you define, with the results reported honestly

The last point carries more marks than students expect. A prototype that works and is honestly
evaluated scores higher than a prototype that appears to work and is described uncritically.

---

## 2. Scope of the assignment

### In scope

| | |
|---|---|
| **One PM function** | Scheduling, risk, or communications — pick one from Section 4, or propose your own |
| **One project context** | Use the brief supplied with your chosen project type, or your own workplace project |
| **One integration** | Jira Cloud, Google Sheets, Google Docs, a CSV file, or an equivalent external system |
| **Multi-step reasoning** | At least three distinct steps, where each consumes the previous step's output |
| **One review mechanism** | A critic step, a schema check, a confirmation gate, or a structured human checkpoint |
| **Your own evaluation** | Criteria you define, a test you run, and results you report |

### Out of scope — do not attempt these

| | |
|---|---|
| **Multiple PM functions** | A scheduler *and* a risk agent *and* a reporting bot is three thin prototypes, not one good one. Marked as one, on the weakest. |
| **Custom code deployment** | No hosting, no servers, no CI. If it runs, it runs in a browser tool. |
| **Anything requiring a paid subscription** | See Section 6. The build must be reproducible by a marker on free tiers. |
| **Anything requiring an API key you generated** | Jira API tokens are the one exception, and only against your own free site. |
| **Live data from a real employer system** | See Section 6 on confidentiality. Use synthetic or supplied data. |
| **Team collaboration on the build** | You may discuss approach. The build, the evaluation, and the write-up are yours alone. |

### The scope test

Before you start, write one sentence in this form:

> *"This prototype takes ___ and produces ___, and I will know it worked if ___."*

If you cannot finish that sentence, your scope is not yet defined. If finishing it requires the word
"and" more than once, your scope is too wide.

---

## 3. Choosing your project

Pick **one** of the three types in Section 4. Each comes with a supplied project brief you will work
from. The briefs are deliberately incomplete — this is the same property as the briefs used in Weeks
2–3, and handling what the brief does not settle is part of what is assessed.

**Substituting your own context.** You may use a project from your own work instead of the supplied
brief, subject to Section 6 on confidentiality. If you do, submit a one-page anonymised brief
alongside your prototype so the marker can judge whether the output is any good. A prototype whose
input the marker cannot see cannot be assessed on output quality, and will lose marks in that band.

**Proposing a fourth type.** Permitted, with written approval by the end of Week 6. Your proposal
must name the PM function, the integration, and the evaluation criteria. Approval is not automatic.

---

## 4. The three project types

---

### Project 1 — Smart Scheduler

**PM function:** turning scope into a schedule with defensible dependency logic.

**Supplied brief: NTU Lecture Theatre AV Refresh**

> The University is replacing projection, audio, and lecture-capture hardware in its teaching
> theatres. The work must be complete before Semester 1 teaching begins. Budget is S$2.8M. The
> incumbent AV maintenance contractor holds a support agreement that runs to the end of the calendar
> year. Estates has asked that no theatre be out of service for more than five consecutive working
> days. The Centre for Teaching and Learning has requested that the new lecture-capture system
> integrate with the existing learning management system. Sponsor is the Office of Development and
> Facilities Management.

**What your prototype must do at minimum**

1. Read the brief and produce a scope statement that separates what is settled from what is not
2. Decompose the scope into a WBS to Level 3
3. Derive milestones with explicit dependency relationships and a stated rationale for any buffer
4. Write the result into an external tool — Jira issues, or a structured Sheets schedule

**What a strong version adds**

- A second pass that checks the schedule against the constraints in the brief and reports conflicts
  rather than silently resolving them
- Relative time only, with the calendar anchoring done by a human — this removes most date invention
- A stable key per work package, so re-running the prototype updates rather than duplicates

**The failure mode to watch for.** Schedulers invent durations. The brief gives you no durations at
all. Any prototype that outputs confident day counts is fabricating, and your evaluation should say
so.

---

### Project 2 — Risk Agent

**PM function:** surfacing, scoring, and tracking risks against a plan.

**Supplied brief: NTU Research Data Platform Migration**

> Research computing storage is being migrated from on-premises infrastructure to a hybrid
> cloud platform. Approximately 40 research groups are affected, holding a mix of open, restricted,
> and human-subject data. Some datasets are subject to grant conditions on retention and location.
> Budget is S$1.9M over 14 months. Research groups control their own data schedules and cannot be
> compelled to migrate on a fixed date. The existing storage hardware goes out of vendor support
> partway through the migration window. Sponsor is the Office of Information, Knowledge and Library
> Services.

**What your prototype must do at minimum**

1. Read the brief and produce a risk register with a consistent scoring scheme you define
2. For each risk, identify an owner role, a trigger condition, and a response
3. Link each risk to the specific deliverable or work package it threatens
4. Write the register into an external tool, with the scores as a sortable field

**What a strong version adds**

- A critic step that challenges the register: which risks are restatements of each other, which are
  issues already occurring rather than risks, which have no owner
- Risks generated from what the brief *omits*, not just what it states
- A distinction between risks the brief supports and risks the model inferred, marked as such

**The failure mode to watch for.** Risk agents generate plausible-sounding generic risks — "scope
creep", "stakeholder resistance" — that would apply to any project. Your evaluation should measure
how many of your risks are specific to this brief and could not have been written without reading it.

---

### Project 3 — Communications Bot

**PM function:** producing audience-appropriate project reporting from underlying project data.

**Supplied brief: NTU Campus Sustainability Reporting Programme**

> The University reports annually on energy, waste, water, and emissions across its campuses. Data
> currently arrives from five separate sources at different times and in different formats. The
> programme aims to consolidate reporting into a single quarterly cycle. Budget is S$900k over 12
> months. The reporting deadline is fixed by an external framework the University has committed to.
> Three of the five data owners sit outside the programme's reporting line. Sponsor is the Office of
> Sustainability.

**What your prototype must do at minimum**

1. Read project status data from an external source — a Jira board, a Sheets tracker, or a supplied
   CSV — rather than from text you paste in
2. Produce a status report for **at least two distinct audiences** with genuinely different content,
   not the same content at two reading levels
3. Distinguish reported fact from inference, and mark anything it could not verify from the source
4. Produce output in a form that could be sent — a document, not a chat response

**What a strong version adds**

- A step that identifies what is *missing* from the source data and says so in the report
- Escalation logic: something in the data triggers a different report, or a flag
- A read-back check — the report is regenerated from the source and compared, to see whether it is
  stable

**The failure mode to watch for.** Communications bots smooth over bad news. Test yours by putting a
genuine problem in the source data and seeing whether it reaches the sponsor version of the report
intact, or gets softened into nothing.

---

## 5. Deliverables

Five items. Submit as a single ZIP or a single folder link. Missing items are marked as zero for the
criterion they support — the marker will not go looking.

| # | Item | Format | Notes |
|---|---|---|---|
| 1 | **Prototype access** | Link or export | A published workflow link, a Jira project with read access, or an export of your prompts and configuration. It must be inspectable, not just described. |
| 2 | **Demo recording** | Video, max 4 min | Hard cap. Screen recording with voice. Show it running on the supplied brief, start to finish. Recordings over 4 minutes are marked to the 4-minute point. |
| 3 | **Output artefact** | PDF or link | What your prototype actually produced — the schedule, the register, the report. Real output, not an idealised version. |
| 4 | **Evaluation report** | 2 pages max | Section 7. This is the highest-weighted single item. |
| 5 | **Design justification** | 2 pages max | Why you split the work the way you did, where you put the human checkpoint and why, what you chose not to automate. |

**Page limits are enforced.** Content past the limit is not read.

---

## 6. Constraints

**Tools.** Everything must run on free tiers. Approved: Google AI Studio, Google Opal, Claude free
tier, Jira Cloud free plan (your own site), Google Sheets and Docs. Nothing requiring installation,
nothing requiring a paid subscription, nothing requiring an API key beyond a Jira token on your own
free site.

If you have a paid subscription personally, you may use it — but your prototype must still be
demonstrable to a marker without one. Build for the free path.

**Confidentiality.** Do not put employer or client material into any of these tools. Free tiers
may use prompts to improve the product. If you use your own project context, anonymise it: no
organisation names, no individual names, no commercial figures. This is a hard requirement, not a
suggestion.

**Jira safety.** Your own free site, a sandbox project, and never a work instance. Label agent-created
issues so you can bulk-delete them. No transitions, no deletions by the agent.

**Use of AI in producing the submission.** You are building an AI system, so the question is not
whether you used AI but whether you were in control of it. Two rules:

- The **prototype** may be built with any AI assistance you like. That is the point of the course.
- The **evaluation report and design justification** must represent your own judgement. You may use
  AI to improve your writing. You may not use it to generate the evaluation findings or the design
  rationale, because those are precisely what is being assessed.

Include a short note in your design justification stating what AI assistance you used and where. A
frank note costs no marks. A missing one, where the work suggests otherwise, is an academic integrity
matter under the NTU Honour Code.

---

## 7. The evaluation report — what is actually wanted

This is the part students most often get wrong, so it is spelled out.

You are not being asked whether your prototype worked. You are being asked to **define what "worked"
means for your prototype, test it against that definition, and report what you found.**

A complete evaluation report contains:

**1. Your criteria.** Three to five, specific to what you built. Not "accuracy" — something you could
actually count. Examples of the right shape:

- *Traceability:* what proportion of generated items can be traced back to a line in the brief?
- *Invention rate:* how many facts appear in the output that are not in the input?
- *Stability:* run it twice with identical input — how much does the output change?
- *Gap detection:* the brief has unresolved points. How many did it surface rather than fill in?
- *Schema compliance:* what proportion of generated items were accepted by the target tool
  unmodified?

**2. Your method.** How you tested. Sample size, even if it is small. "I checked all 34 WBS items" is
a method. "It seemed good" is not.

**3. Your results.** Numbers where you have them. Include the bad ones. A prototype with a 40%
invention rate, honestly measured and clearly reported, scores better than one claiming to be
flawless.

**4. What you would fix.** Two or three specific changes, with reasoning. This is where the marker
sees whether you understand your own system.

---

## 8. Submission and the Week 8 session

**There is no live presentation.** Your entire grade comes from the five submitted artefacts in
Section 5. The recording *is* the demonstration — treat those four minutes as the presentation you
would otherwise have given, because that is exactly what they are.

**Submit before the Week 8 session.** Exact date on NTULearn. Nothing submitted after the deadline is
demonstrated, discussed, or marked as on time.

**What Week 8 is instead.** A taught session on agent evaluation: how performance, reliability and
accountability are measured in agentic systems, and how the criteria you invented for your own
prototype compare with the frameworks used in practice. Common patterns from across the cohort's
submissions — including the interesting failures, anonymised — are worked through in class.

This is why your evaluation report must be finished before the session rather than after it. You will
get considerably more from Week 8 having already tried to measure your own system and found it
harder than expected.

---

## 9. Marking criteria (summary)

| Criterion | Weight | What it asks |
|---|---|---|
| **Agentic design and justification** | 30% | Is this a designed system with reasoned structure, or a long prompt? Are the checkpoints deliberate? |
| **Tool and data integration** | 20% | Does it genuinely read from or write to an external system? Does it handle what the target requires? |
| **Evaluation** | 25% | Are the criteria meaningful, the method real, and the reporting honest? |
| **PM fit and output quality** | 15% | Would the artefact survive contact with a sponsor? Is the PM reasoning sound? |
| **Demonstration and communication** | 10% | Is the recording clear, within time, and does it show the system rather than describe it? |

The full analytic rubric with band descriptors is on NTULearn.
