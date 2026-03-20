# Building Safer Systems: A Path to Reducing Client-Impacting Incidents
## STAMP/STPA Senior Manager Presentation

---

## Context & Goal

**Objective:** Get sponsorship from 1-2 senior managers to pilot STAMP/STPA in their organizations.

**Audience:** Senior technical managers. Technical background. Control engineering teams and budgets. Little to no prior STAMP/STPA exposure. Head of Engineering also present.

**Format:** Slide deck, 45-60 minutes, 22 slides.

**Key narrative thread:**
> "Our incidents are increasing because our analysis method only finds individual causes, not system causes. We are fixing symptoms while underlying control gaps remain. STAMP/STPA makes those gaps visible and addressable. We have already found evidence of this in our own systems. We are asking for two sponsors to prove it at scale."

---

## Key Assets

| Asset | Why It Matters |
|---|---|
| Incident trend data | Creates urgency before any methodology is introduced |
| Head of Engineering mandate | Reframes ask from grassroots pitch to strategic alignment |
| Poison pill library example | Makes control loop principle concrete and internal |
| Publication-quality case study | Scientific credibility, internal relevance |
| Human vs. system feedback finding | Answers "what will this tell me I don't know" |
| Postmortem wedge strategy | Neutralizes time/resources objection |
| STPA scoping flexibility | Neutralizes "boiling the ocean" fear |
| LLM acceleration in development | Shows practical cost reduction path |

---

## Objection Responses

**"You can't eliminate all bugs"**
You don't need to. The poison pill library example: doesn't know all corruption types, just detects repeated crash on same offset and moves past it. STPA designs control structures that handle unknown failures — not just enumerated ones.

**"What will this tell me I don't already know?"**
Engineers learned system dangers by living through failures — at high cost to company and customers. STPA surfaces these before the outage. That knowledge is also tacit, unevenly distributed, and leaves when engineers leave. STPA makes it explicit and transferable. Case study finding: human vs. system feedback divergence — RCA would never find this until catastrophic failure.

**"How much time does this take?"**
Entry point is postmortems — time already allocated. STPA framing upgrades existing practice, doesn't add new overhead. LLM tooling in development to further reduce burden. Full system analysis comes later after value is demonstrated.

**"Is this systematic / does it find all failure modes?"**
STPA follows a defined process — doesn't depend on analyst knowing what to look for. Unlike FMEA/fault trees, you scope what matters to you — no boiling the ocean. No technique finds all failure modes; the goal is controlling the hazards most important to your system and customers.

**"We already do postmortems"**
Postmortems find what broke. STPA finds what's about to break and why the system keeps producing the same failure categories. Complementary, not competitive.

**Political defensiveness**
Frame managers as sponsors of the solution, not subjects of the diagnosis. STAMP would analyze their control structure too — handle carefully.

---

## Slide Outline

### Section 1: The Burning Platform

**Slide 1 — Title**
- Title: "Building Safer Systems: A Path to Reducing Client-Impacting Incidents"
- Subtitle: presenter name, date, org
- Do NOT lead with "STAMP/STPA" — lead with the problem

**Slide 2 — The Trend**
- Title: "Our Incident Profile Is Getting Worse"
- Single chart: incident trend over time — volume, severity, client impact
- No methodology yet. Let the data speak.

**Slide 3 — What This Costs**
- Title: "This Is Not Just an Engineering Problem"
- Qualitative impact areas:
  - Client trust — repeated incidents erode confidence
  - Reputation — severity and frequency are visible externally
  - Engineering capacity — incident response diverts time from delivery
  - Compounding cost — systemic issues grow more expensive over time
- Close: "The cost of not addressing this grows with every incident."

---

### Section 2: Why Our Current Approach Isn't Working

**Slide 4 — What We Do Today**
- Title: "Our Current Process: React, Investigate, Fix"
- Simple flow: Incident → Postmortem → RCA → Tickets → Fix
- Acknowledge what works before introducing the "but"

**Slide 5 — The Limits of RCA**
- Title: "RCA Tells Us What Broke. Not Why We Keep Breaking."
- Three structural limitations:
  1. Finds proximate cause — stops at first plausible answer
  2. Scope depends on investigator — inconsistent by design
  3. Only triggers after failure — never surfaces latent hazards
- "RCA is a rear-view mirror."

**Slide 6 — The Time Bomb Problem**
- Title: "We Know Where Some of the Dangers Are. We Can't Act on Them."
- Known issues go unaddressed because they're infrequent
- Business pressure structurally outcompetes safety investment
- These are system design failures, not people failures
- "The pressure to deliver is itself a control problem."

**Slide 7 — The Result**
- Title: "Whack-a-Mole at Scale"
- Vicious cycle diagram: Incident → fix symptom → pressure resumes → next incident → repeat
- Each cycle: more clients affected, higher severity, less time to fix properly
- Bridge into solution

---

### Section 3: A Different Way to Look at the System

**Slide 8 — A Shift in Mental Model**
- Title: "What If the Problem Isn't the Components — It's the Control?"
- Traditional view: systems fail because components fail
- STAMP view: systems fail because control over interactions breaks down
- Key insight: ensure control structures handle failure regardless of form
- One diagram maximum

**Slide 9 — The Poison Pill Example**
- Title: "You've Already Built This Way. You Just Didn't Have a Framework for It."
- Walk through poison pill library:
  - Problem: corrupted messages cause crashes
  - Solution: controller detects repeated crash on same offset, moves past it
  - Doesn't enumerate all corruption types — detects condition, applies control action
  - Unknown failures handled by design
- Bridge: "STPA is how you find everywhere else in your system that needs this — systematically, before the outage."

**Slide 10 — Introducing STPA**
- Title: "STPA: Systematic, Scoped, Proactive"
- Three differentiators from RCA:
  1. Systematic — defined process, doesn't depend on analyst intuition
  2. Scoped by you — no boiling the ocean like FMEA/fault trees
  3. Proactive — finds unsafe control gaps before failure
- One simple control loop diagram

**Slide 11 — What STPA Produces**
- Title: "Concrete, Actionable, Transferable Knowledge"
- Documented control structure for your system
- Identified unsafe control actions and missing constraints
- Clear targets for developers — no relying on tribal knowledge
- Knowledge that stays when engineers leave
- "Your developers stop guessing what might break a rollout. They have a map."

**Slide 11a — The Control Loop You Already Have**
- Title: "Every System Already Has a Control Loop. Here's Yours."
- The existing loop: Client sees problem → calls support → support contacts engineering → engineering fixes → support confirms with client
- This is a textbook control loop — but it starts with the client
- The client is the sensor. The client is detecting failures before we do.
- Goal of STPA: pull the loop inside so the client never has to be the one who tells us something is broken

---

### Section 4: What We Found in Our Own System

**Slide 12 — The Case Study**
- Title: "We Ran This on [System Name]"
- Brief system description — what it does, why it matters, scope of analysis
- Note: written to publication quality with scientific rigor

**Slide 13 — The Control Structure**
- Title: "What the System Actually Looks Like as a Control Structure"
- Control diagram from case study
- High-level walk through — no exhaustive detail

**Slide 14 — What We Found**
- Title: "What STPA Surfaced That RCA Never Would Have"
- Lead finding: human operators and automated systems work off different feedback → different responses and outcomes → systemic gap RCA would never surface until catastrophic failure
- Additional findings from case study (quantified where possible, with concrete examples)
- Prioritize findings that: map to past incidents, cross team boundaries, survive "we already knew that"
- Frame each: "This gap exists today. An incident hasn't forced us to find it yet."

**Slide 15 — The Cost of Not Knowing**
- Title: "These Are Not Hypothetical Risks"
- Connect case study findings back to incident trend from slide 2
- Map findings to past incidents where possible
- "This is the category of issue contributing to the trend you saw at the start."

---

### Section 5: The Virtuous Cycle

**Slide 16 — The Cycle We're Building Toward**
- Title: "What Sustained Investment Produces"
- Virtuous cycle diagram: STPA analysis → hazards visible → targeted fixes → fewer incidents → more capacity → deeper analysis → repeat
- Contrast with vicious cycle from slide 7

**Slide 17 — What Makes It Stick**
- Title: "This Only Works With Sponsorship"
- Three requirements:
  1. Visibility — STPA makes hazards concrete and documented, not abstract
  2. Measurement — track findings against incident trend, quarterly checkpoints
  3. Organizational commitment — partner with us on the pilot, prove it out together
- Reference Head of Engineering mandate
- "We are not asking you to take this on faith. We are asking you to run the experiment."

---

### Section 6: The Ask

**Slide 18 — The Entry Point**
- Title: "We're Not Asking for New Time. We're Asking to Use Existing Time Better."
- Postmortem wedge: time already allocated when incident occurs
- Apply STPA framing to postmortem analysis — same meeting, better output
- LLM tooling in development to guide practitioners through STPA steps

**Slide 19 — The Pilot**
- Title: "One Org. One Team. Measurable Results."
- STPA-framed postmortems for 6-12 months
- Training cohort in sponsor's org
- Learning curve chart: analysis time decreases as practitioners gain experience (cite instructor data)
- LLM tooling further accelerates the curve
- Quarterly review of findings vs. incident trend
- Success metric: measurable reduction in incident categories in pilot org
- Key message: "The cost of this investment front-loads. The benefit compounds."

**Slide 20 — What Sponsorship Means**
- Title: "What We're Asking From You"
- Named point of contact in your org
- Protected time for training cohort (hours TBD)
- Quarterly 30-min check-in on results
- Signal to teams that this is a priority
- "That signal costs nothing and is worth everything."

**Slide 21 — The Beachhead Effect**
- Title: "We Don't Need Everyone. We Need Two."
- Results in one org visible to others
- Trained cohort spreads methodology organically
- Pilot data makes the case for broader adoption better than any presentation
- Close with Head of Engineering mandate as organizational direction

**Slide 22 — Close**
- Title: "The Trend Doesn't Have to Continue"
- Echo opening incident trend chart
- Close: "We are looking for two sponsors to run this pilot. Who's in?"

---

## Narrative Script

### Section 1: The Burning Platform

**Slide 1 — Title**

"Thank you for your time today. What I want to talk about is something that affects all of our organizations — and frankly, something that is getting worse, not better. I'm not here to point fingers. I'm here to show you a different way of looking at a problem we all share, and to make a specific ask at the end. Let's start with the data."

---

**Slide 2 — The Trend**

"This chart shows our incident profile over the past [X months/years]. What you're seeing is not noise — it's a trend. The number of incidents is increasing. The severity is increasing. The number of clients affected is increasing. And importantly, this trend is not abating.

We are not standing still. Our teams are working hard, our postmortems are happening, tickets are being cut, fixes are being deployed. And yet the line keeps going up.

That tells us something important: the way we are currently responding to incidents is not addressing what is causing them."

---

**Slide 3 — What This Costs**

"Before we get into the how, I want to make sure we're aligned on the stakes.

Every incident that reaches a client costs us in four ways.

First, client trust. Each incident is a withdrawal from an account that takes a long time to build back up.

Second, reputation. Clients talk to each other. Severity and frequency don't stay internal.

Third — and this one I want you to sit with — engineering capacity. Every hour your teams spend in incident response is an hour not spent on delivery. Safety and delivery are not competing priorities. Every incident makes delivery slower.

Fourth, compounding cost. The longer systemic issues go unaddressed, the more expensive they become to fix. What costs one sprint to fix today may cost a quarter to fix in two years.

The cost of not addressing this grows with every incident on that chart."

---

### Section 2: Why Our Current Approach Isn't Working

**Slide 4 — What We Do Today**

"Let me be clear about something before I go further. Our incident management process is not broken. When something goes wrong, we respond. We hold postmortems. We document what happened, what the impact was, how we recovered. We cut tickets. We fix things. Business is in the room. That discipline exists and it matters.

What I want to talk about is not what we're doing wrong. It's what our current approach is structurally incapable of doing — no matter how well we execute it."

---

**Slide 5 — The Limits of RCA**

"Root cause analysis is the foundation of how we investigate incidents today. And for what it is, it works. But it has three structural limitations that no amount of rigor or effort can overcome.

First, RCA finds the proximate cause — the immediate trigger. It stops at the first plausible answer. 'The service crashed because of a race condition.' That's true. But why does the system allow that race condition to cause a crash in the first place? RCA rarely gets there.

Second, the scope of an RCA depends entirely on the people in the room. That variability is not a people problem — it's a method problem. Our current method has no systematic way to ensure we're asking the right questions.

Third, and most importantly — RCA only triggers after something fails. It cannot tell you about the race condition that hasn't caused a crash yet. Those hazards are invisible to RCA until they become incidents.

RCA is a rear-view mirror. It tells you where you've been. It cannot tell you where the road is about to end."

---

**Slide 6 — The Time Bomb Problem**

"That third limitation has a name in our systems. We call them time bombs — and most of us in this room know exactly what I'm talking about.

These are the race conditions, the data synchronization issues, the edge cases that surface under unexpected load or unusual sequences of events. We know they exist. In many cases, our developers know precisely where they are. And they remain unaddressed — not because anyone is negligent, but because they happen infrequently enough that the business case for fixing them never clears the bar.

There's always a feature to ship. There's always a business ask that is more visible, more measurable, and more immediate than fixing something that hasn't broken yet this quarter.

I want to name this directly: the pressure to deliver is not a character flaw in our managers or our teams. It is a structural feature of how our organizations are measured and rewarded. It is, in systems terms, a control problem — and it is baked into our governance. Our current process has no mechanism to surface these hazards clearly enough, or early enough, to compete with delivery pressure.

So they wait. And occasionally, under the right conditions, they stop waiting."

---

**Slide 7 — The Result**

"The result is what you see in this diagram — and what you saw in the chart on slide two.

We respond to an incident. We find the immediate cause. We fix it. We cut tickets for the follow-up work. Some of it gets done. Delivery pressure returns. The systemic issues remain. The next incident happens — often a variation of the same underlying problem. And each cycle, the impact grows.

This is whack-a-mole at scale. And the moles are multiplying.

I am not here to tell you that we can make incidents go away entirely. No methodology can promise that. What I am here to tell you is that there is a fundamentally different way to approach this — one that addresses system causes, not just symptoms. And we have already started using it."

*[pause before advancing]*

---

### Section 3: A Different Way to Look at the System

**Slide 8 — A Shift in Mental Model**

"The traditional way we think about software failures goes something like this: something broke, therefore something failed. Find the broken thing, fix it, done.

That mental model works well for simple systems. It works less well as systems grow in complexity — more services, more teams, more interdependencies, more ways for components to interact in ways no one individually designed or anticipated.

STAMP — the Systems Theoretic Accident Model and Processes — proposes a different mental model. It says: failures don't just happen because components break. They happen because the control over how components interact breaks down. The system behaves in a way that no one intended, because the constraints that were supposed to prevent that behavior weren't there, weren't enforced, or weren't adequate for the conditions.

This is a subtle but important shift. It moves the question from 'what broke?' to 'where does our system lack adequate control?' And it turns out that question is answerable — systematically, before anything breaks."

---

**Slide 9 — The Poison Pill Example**

"Let me make this concrete with something we actually built.

We have a message processing system. Messages come in, get processed, results go out. Occasionally a message is corrupted in some way — a poison pill. When the processor encounters it, it crashes.

The naive fix is to try to enumerate every possible way a message can be corrupted and handle each one. That's an arms race you cannot win. There will always be a corruption type you didn't anticipate.

What we built instead is a controller. The controller doesn't need to know how the message is corrupted. It just watches for a specific condition: has this process crashed on the same message offset more than once? If yes, it applies a control action — move the offset past that message and let the process recover.

Unknown failure modes, handled by design. Not because we anticipated every possible corruption. Because we designed the control structure to detect and respond to the condition.

Your teams are already doing this in places where the pain was bad enough to force it. The knowledge to build this exists in your organizations. It was just earned at the cost of outages.

STPA is how you find every other place in your system that needs this kind of thinking. Systematically. Before the next outage forces it."

---

**Slide 10 — Introducing STPA**

"So what is STPA, practically?

It is a hazard analysis technique with three properties that matter for us.

First, it is systematic. It follows a defined process — identify the system's control structure, identify what unsafe control actions are possible, identify the conditions that lead to them. The output doesn't depend on the analyst knowing in advance what to look for. The method surfaces it.

Second, it is scoped by you. This is where STPA is fundamentally different from older techniques like FMEA, fault trees, or HAZ-OP. Those techniques require you to analyze every component in the system — what some call boiling the ocean. With a system of our scale and complexity, that's not practical. STPA lets you define the boundary. You choose the system, the hazards you care about, the control relationships you want to analyze. You are in control of the scope.

Third, it is proactive. You do not need an incident to trigger an STPA analysis. You run it on a system and find the control gaps before they cause loss. That is the fundamental difference from everything we currently do."

---

**Slide 11 — What STPA Produces**

"Let me be specific about what comes out of an STPA analysis.

You get a documented control structure for the system — a clear picture of who and what controls what, what feedback they act on, and what control actions they can take. For most of our systems, this picture does not exist anywhere today. It lives in the heads of your most experienced engineers. When they leave, it leaves with them.

You get a catalog of unsafe control actions — the specific ways the control structure can fail to prevent harm. Each one is a concrete, actionable finding. Not 'we should improve reliability.' Specific: 'this controller receives insufficient feedback to detect this condition, and when that happens, this is what can go wrong.'

And you get a clear target for your developers. Instead of relying on tribal knowledge and hoping that whoever wrote the code thought of the edge cases, your developers have an explicit specification of what the system needs to handle.

Your developers stop guessing what might break. They have a map."

---

**Slide 11a — The Control Loop You Already Have**

"Before I show you what we found in our own system, I want to point out something that reframes this entire conversation.

Every single system we run already has a control loop. Every one. You may not have thought of it this way, but it's there.

A client sees something wrong on their screen. They call our support line. Support contacts engineering. Engineering investigates, makes corrections, brings the system back to expected behavior. Support confirms with the client that the issue is resolved.

That is a textbook control loop. Observe a condition, take a corrective action, verify the outcome.

The problem is not that the loop doesn't exist. The problem is where the loop starts. It starts with the client. The client is the sensor. The client is the one detecting that something has gone wrong in our system.

Everything we are talking about today — STAMP, STPA, the analysis technique, the pilot — has one goal: pull that control loop inside our systems, so that the client never has to be the one who tells us something is broken.

When we get there, incidents don't disappear. But they stop reaching clients. And that is what the trend on slide two is really measuring — how often our clients are detecting failures before we do."

---

### Section 4: What We Found in Our Own System

**Slide 12 — The Case Study**

"Everything I've described so far is grounded in established systems safety theory. But theory only gets you so far in this room. So let me show you what happened when we applied this to one of our own systems.

[System name] is [brief description — what it does, who depends on it, why it matters]. We chose this system for our analysis because [scope rationale].

We applied STPA rigorously. This analysis has been written up to publication standard — it will be submitted as a research paper. I mention that not to impress you with academic credentials, but because it means the findings have been subjected to the kind of scrutiny that internal reports rarely receive. What I'm about to show you is not an opinion. It is a documented, defensible analysis."

---

**Slide 13 — The Control Structure**

"This is what [system name] looks like as a control structure.

What you're seeing here is not a system architecture diagram. It's not a data flow diagram. It's a map of control — who and what issues commands to whom, what feedback they receive in return, and what constraints are supposed to keep the system behaving safely.

Take a moment to look at it. [brief walk through major controllers, controlled processes, and feedback loops]

Most of you have not seen your systems drawn this way before. That's not an accident — this representation doesn't exist in our documentation today. It had to be constructed through analysis. And the act of constructing it is itself revealing — because when you draw this picture, gaps become visible that are invisible in every other representation of the system."

---

**Slide 14 — What We Found**

"Here is what the analysis surfaced.

The finding I want to highlight first is this: human operators and the automated system are working off different feedback. They are observing different signals, making decisions based on different information, and taking actions that are each locally rational — but that can interact in ways that produce outcomes neither intended.

RCA would never find this. There is no incident to trigger an investigation. There is no broken component to point to. There is a structural gap in the control design that exists right now, in production, waiting for the conditions that make it matter.

[Present additional findings with concrete examples where available]

Each of these findings shares the same characteristic: they exist today. They are not hypothetical. An incident has not yet forced us to discover them. STPA found them first."

---

**Slide 15 — The Cost of Not Knowing**

"Look at this finding. Now look back at slide two.

[Connect specific finding to a past incident category or trend in the data]

This is not a coincidence. The categories of failure we are seeing in our incident trend are not random. They are symptoms of specific, identifiable gaps in how our systems are controlled. We have been treating the symptoms. We now have a method for finding the gaps.

I want to be direct with you: we found these things because we looked. Systematically. With a method designed to find them.

The question is not whether gaps like these exist in your other systems. They do. The question is whether we find them through analysis — or whether we wait for clients to find them for us."

*[let that land before advancing]*

---

### Section 5: The Virtuous Cycle

**Slide 16 — The Cycle We're Building Toward**

"Let me show you what this looks like when it works.

We run an STPA analysis on a system. The control gaps become visible — documented, concrete, assigned. Teams have clear targets. Fixes are prioritized not by who complained loudest or what incident just happened, but by where the control structure is weakest. Over time, incidents in that system decrease. Engineering time that was being consumed by incident response becomes available. That capacity goes back into analysis, into better controls, into proactive work rather than reactive work.

That is the virtuous cycle. And it is the opposite of what you saw on slide seven.

The difference between the two cycles is not effort. Your teams are already working hard. The difference is where the effort is directed. Right now effort is directed at symptoms. This cycle directs it at causes."

---

**Slide 17 — What Makes It Stick**

"A virtuous cycle doesn't sustain itself. It requires three things to keep turning.

First, visibility. STPA makes hazards concrete and documented. A named, recorded control gap is fundamentally different from a vague sense that something might be risky. It changes the conversation from 'we should probably look at that' to 'we know this exists, we know what it could cause, and we have a plan for it.' That visibility is what allows safety investment to compete with delivery pressure — because it stops being abstract.

Second, measurement. We will track findings against incident trends in the pilot org. When the data shows that STPA-informed fixes are reducing incident categories over time, the case for continued investment makes itself. We are not asking you to commit indefinitely on faith. We are asking you to run the experiment and let the results speak.

Third, organizational commitment. The head of engineering has set the direction. But the people who make that direction real are the managers closest to the teams — the ones who control how time is allocated, where priorities land, and what gets protected when pressure arrives. What we are asking today is for one or two of you to partner with us on the pilot — to be the organizations where we prove this out together, and whose results become the model for how this grows across the company."

---

### Section 6: The Ask

**Slide 18 — The Entry Point**

"Now let me address the question that I know is in the room: where does this fit in an environment where every team is already stretched?

The answer is that the entry point we are proposing does not require new time. It requires using time you are already spending — differently.

When an incident happens, a postmortem is already scheduled. That time is already allocated. What we are proposing is to apply STPA framing to that postmortem — same meeting, better output.

This is not a replacement for what you do today. Your postmortem process stays intact. What changes is the depth and structure of what comes out of it — findings that are systemic and actionable, not just proximate and symptomatic.

And to make this as accessible as possible, we are developing LLM-assisted tooling that guides practitioners through the STPA steps. You do not need a team of trained safety engineers to start."

---

**Slide 19 — The Pilot**

"Here is what the pilot looks like concretely.

Over six to twelve months, a participating org applies STPA framing to its postmortems. A small training cohort learns the technique — and the investment in that training is not a one-time sunk cost. These practitioners become your internal capability. They train others. The methodology spreads at near-zero marginal cost from that point forward.

On the effort question — the data shows that analysis time decreases significantly as practitioners build experience. The learning curve is real but it is short. The first analysis takes the longest. By the fifth or sixth, practitioners are moving through the process in a fraction of the time. We have seen this in our own work, and it is consistent with what the research shows.

LLM tooling accelerates that curve further. We are building it specifically to reduce the barrier to entry for teams who are new to the technique.

At the end of each quarter we review findings against the incident trend. We are not asking you to take this on faith for years. We are asking for one quarter at a time, with data at every checkpoint.

The cost of this investment front-loads. The benefit compounds."

---

**Slide 20 — What Sponsorship Means**

"I want to be specific about what we are asking from a sponsor, because I think the word 'sponsorship' can sound larger than it is.

We are asking for four things.

A named point of contact in your organization — someone who owns the relationship with our team on the pilot.

Protected time for a small training cohort. We will define the exact hours together, but we are talking about a modest, bounded investment — not a redeployment of your team.

A quarterly thirty-minute check-in to review findings and incident data. That is the entire ongoing time commitment at your level.

And a signal to your teams that this is a priority. That signal costs nothing and is worth everything. When teams know their management is invested, they invest too.

That is the full ask."

---

**Slide 21 — The Beachhead Effect**

"We are not asking everyone in this room to say yes today. We are asking for two.

Here is why that is enough.

Results in one organization are visible to everyone else. When incident categories start declining in the pilot org — when the postmortems start producing systemic findings instead of proximate ones — that is not an abstract argument anymore. That is data from inside this company, from a team that looks like your team, running systems that look like your systems.

The practitioners trained in the pilot become your evangelists. They present at internal tech talks. They help other teams get started. The methodology spreads organically, through people your colleagues already trust, rather than through mandates from above.

And the organizations that lead this pilot will have shaped how STPA gets adopted across the company. The practices, the tooling, the training — all of it will be built on what you help us learn.

The head of engineering has set the direction. Two sponsors in this room make it real."

---

**Slide 22 — Close**

"I want to bring this back to where we started.

[Return to incident trend chart]

This trend is not inevitable. It is a symptom of a system that is growing in complexity faster than our ability to control it. We have a method for changing that. We have already used it on our own systems and found things that would otherwise have waited for an incident to surface them.

We are not asking you to solve this today. We are asking two of you to run the experiment with us.

The clients on this chart — the ones whose experience is getting worse with every point on that line — they are currently our control loop. Every call to our support line is a signal that our systems failed to catch something before it reached them.

Let's pull that loop inside. Let's be the ones who find it first.

Who's in?"

---

## Open Items

- [ ] Confirm whether immediate management chain will co-present or formally endorse
- [ ] Complete internal case study paper before scheduling presentation
- [ ] Finalize additional case study findings for slide 14 (quantified, with concrete examples)
- [ ] Define concrete training hour estimate for slide 20
- [ ] Investigate LLM-assisted STPA tooling development timeline
- [ ] Check if recurring failure category analysis from internal LLM work will be ready in time
