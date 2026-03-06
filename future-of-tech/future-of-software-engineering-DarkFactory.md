# The Dark Factory
### AI Coding and the Future of Software Engineering

---

## Table of Contents

**Preface**

**Part One: The Gap Nobody Is Talking About**
- The Contrasting Realities

**Part Two: The Five Levels of AI Coding**
- Level Zero — Spicy Autocomplete
- Level One — The Coding Intern
- Level Two — The Junior Developer
- Level Three — Developer as Manager
- Level Four — Developer as Product Manager
- Level Five — The Dark Factory

**Part Three: What the Dark Factory Actually Looks Like**
- StrongDM's Software Factory
- Scenarios, Not Tests
- Digital Twins and Production Safety
- The Economics of Compute

**Part Four: The Self-Referential Loop**

**Part Five: Why Experienced Developers Get Slower**
- The J-Curve of Workflow Disruption
- The Trust Problem
- Organizational Structures Built for Humans

**Part Six: The Brownfield Reality**
- The Challenge of Legacy Systems
- The Migration Path

**Part Seven: The Collapsing Junior Developer Pipeline**
- The Broken Apprenticeship Model
- The Rising Bar

**Part Eight: The New Shape of Software Organizations**
- The Generalist Advantage
- Radical Flatness
- What Cannot Be Automated

**Part Nine: The Demand That Never Saturates**
- The Shifting Bottleneck

**Conclusion: The Work That Remains**

---

## Preface

Let me tell you something that will mess with your head a little.

Right now, a three-person team is running a software factory where no human writes code and no human reviews code. It just ships. Continuously. On its own.

And at the same time, experienced developers who started using AI coding tools are taking 19% longer to finish their work. Not beginners. Not people who are bad at their jobs. Experienced engineers — getting slower.

Both of these are happening right now. Same tools. Same era. Completely opposite outcomes.

That contradiction is what this book is about. Because the distance between those two realities is not about technology. It is about whether people are willing to actually change — not just adopt a new tool, but rethink how they work from the ground up.

Some teams have done that. Most have not. And the gap between them is getting wider every month.

---

## Part One: The Gap Nobody Is Talking About

### The Contrasting Realities

Here is what the frontier looks like. Anthropic engineers are watching Claude Code write 90% of its own codebase — a number moving steadily toward 100%. A company called StrongDM has been running a fully autonomous coding system since last July. You hand it a written spec. It builds the software. Nobody touches the code. It just works.

These are not research projects. These are live production systems making real money.

Now here is what most of the industry looks like. A study by METR gave experienced open-source developers the best available AI tools and watched what happened. Those developers took **19% longer** to complete tasks — while being convinced they were **24% faster**.

Sit with that for a second. They were slowing down while feeling like they were speeding up. That is not a small error in judgment. That is a fundamental disconnect between perception and reality — and it is happening at scale across the industry.

The difference between the two groups was not the tools. It was everything around the tools. The habits. The workflows. The org structures. The willingness to let go of the old way.

This is the gap nobody in the industry wants to talk about honestly, because admitting it means admitting that most "AI transformation" so far has been mostly theater.

---

## Part Two: The Five Levels of AI Coding

To understand where most teams are actually stuck, you need a map. Dan Shapiro's framework breaks AI coding into five levels — and it is a little uncomfortable, because most people who think they are at Level 4 are quietly sitting at Level 2.

### Level Zero — Spicy Autocomplete

AI finishes your sentences. You type, it suggests the next line, you accept or move on. You are still writing the software. The machine is just a very fast assistant that has read an enormous amount of code.

This is where everyone starts. It saves a little time. It does not change how you think about your work.

### Level One — The Coding Intern

You give the AI a specific task — write this function, build this UI component — and it does it. You review everything it produces. You still own all the decisions that matter.

Think of it like working with someone on their first week. Useful. Needs supervision. You would never hand them something important and walk away.

### Level Two — The Junior Developer

Now the AI can navigate your whole codebase. It can make changes across multiple files, understand the context of what you have built, and handle more complex tasks. You still read everything it produces, but you are relying on it for bigger pieces of work.

Here is the uncomfortable part: **90% of developers who call themselves AI-native are operating right here.** They have faster autocomplete and a more capable assistant. They are nowhere near a dark factory.

### Level Three — Developer as Manager

The AI writes code and submits pull requests. You review at the feature level — does this behave correctly, does it make sense — rather than reading every line.

And this is where things get psychologically messy. Your entire career was built around writing code, understanding it deeply, owning it. Trusting a system you did not build, that you cannot fully inspect, to make decisions — that feels wrong, even when the results are good. Most developers hit this wall and quietly stop climbing.

### Level Four — Developer as Product Manager

You write a spec. The AI builds the software. You evaluate whether what came out actually works. You never look at the implementation.

This requires a skill most engineers genuinely do not have yet: writing specifications so clear and unambiguous that a machine can execute them without a single follow-up question. It sounds simple. It is not. It is a completely different kind of hard.

### Level Five — The Dark Factory

Spec goes in. Working software comes out. No human writes code. No human reviews code. The system runs on its own.

Most people in the industry assume this is theoretical, or a decade away. It is neither. There are companies operating here right now. And the interesting question is not whether it is possible — it is why so few are willing to try.

---

## Part Three: What the Dark Factory Actually Looks Like

### StrongDM's Software Factory

StrongDM's team is three people. Their job is not to write code. Their job is to write clear specifications and verify that the software behaves correctly when it comes out.

The system only became truly viable when Claude 3.5 Sonnet arrived. Before that model, AI agents could write code in short spurts but would lose the thread on anything complex. Claude 3.5 Sonnet could hold context across long, multi-step problems without drifting. That was the moment it clicked.

The agent they use is called **Attractor** — open source, built on three markdown files. No secret infrastructure. No proprietary magic. A well-designed specification system and a model capable of following it.

### Scenarios, Not Tests

This idea is worth slowing down for, because it is one of the most important things in this book.

Traditional tests live inside the codebase. If your AI agent writes the code and can also see the tests, you have a problem: it will learn to write code that passes the tests. Not code that genuinely works. Code that passes the tests. It is exactly like a student who memorizes the practice exam without actually understanding the subject — the score looks fine, but the knowledge is not there.

StrongDM uses **scenarios** instead. These are behavioral descriptions of how the software should act, written from the outside — and the agent never sees them during development. It cannot optimize for them. The only way to pass a scenario is to actually build software that works.

The difference in practice: a test says "this function should return this value." A scenario says "a user should be able to log in, find their report, and export it in two clicks." You can game the first. You cannot game the second.

### Digital Twins and Production Safety

The autonomous system needs to test against real services — login providers, project management tools, messaging platforms. But you cannot let an AI agent make live changes while it is still iterating on what to build.

StrongDM's answer is a **Digital Twin Universe** — simulated versions of every external service the software talks to. They behave exactly like the real thing. The agent tests against them without risk. Nothing in production is ever touched during development.

It is a bit like flight simulators for pilots. All the complexity, none of the consequences of getting it wrong.

### The Economics of Compute

StrongDM budgets **$1,000 per human engineer per day** for AI agents. That sounds like a lot until you put it next to what an engineer actually costs — salary, benefits, the meetings they sit in, the context switching, the days when nothing ships because of a dependency or a blocker.

The agents run continuously at that budget. No breaks. No context switching. No waiting on someone else. And often, the total cost is lower than the equivalent human work.

---

## Part Four: The Self-Referential Loop

Here is one of the stranger things happening in tech right now: AI is building itself.

OpenAI's Codex 5.3 analyzed its own training logs, found failing tests, and proposed fixes — improvements made by the model to the very process that trains the model. That loop produced a 25% speed improvement and 93% fewer wasted compute tokens.

Claude Code is writing 90% of its own codebase. Anthropic's goal is 100%.

Boris Churny, the Claude Code project lead, has not written a line of code in months. His job is now to decide what the system should build and describe it precisely enough that it can. He went from engineer to director — same person, same role, completely different work.

This is not a curiosity. It is a compounding advantage. Teams that have crossed into autonomous development are improving faster because their systems can improve themselves. The gap between them and everyone else does not stay constant. It widens.

And the adoption numbers reflect it. **4% of all public GitHub commits are now made by Claude Code.** Projected to pass 20% by year-end. A billion-dollar run rate in six months.

---

## Part Five: Why Experienced Developers Get Slower

So if AI makes coding faster, what is going on with that 19% slowdown?

### The J-Curve of Workflow Disruption

Imagine you have driven on the left side of the road your whole career. Someone hands you a faster car — but it is built for the right side. The car is genuinely better. You are still going to crash a few times before you figure out how to use it.

That is roughly what happens when AI tools get dropped into existing workflows without changing those workflows. Developers now spend time evaluating suggestions before accepting them. They spend time fixing code that looks right but is subtly wrong — the kind of wrong that is harder to catch than obvious errors. They context-switch between their own thinking and the AI's output. They debug problems they did not create.

Productivity drops before it rises. That is the J-curve. The curve does turn upward — but only for teams willing to go through the dip and redesign how they work. Most do not.

### The Trust Problem

**46% of developers do not fully trust AI-generated code.** Which is rational — AI does make mistakes, and some of those mistakes are subtle enough to pass a casual review and blow up in production three weeks later.

But here is the trap. If you distrust the code but have no systematic way to verify it, you end up doing double work: using AI to write and then manually reviewing with the same effort you would spend writing it yourself. The time savings disappear. The frustration does not.

The fix is not to trust blindly. It is to build verification systems — scenarios, behavioral tests — that let you evaluate what the code does without inspecting every line of how it does it. That is a workflow redesign problem. Most teams treat it as a trust problem and stay stuck.

### Organizational Structures Built for Humans

Stand-ups exist because people forget what they were working on. Sprint planning exists because teams need shared context. Code reviews exist because humans make inconsistent calls under pressure.

None of this is bad. These were sensible solutions to real problems.

But when AI writes the code, those specific human problems stop being the bottleneck. The coordination overhead stays. The meetings still happen. The review cycles still run. The structure was designed to manage human complexity — and it turns out, that structure is now the thing slowing you down.

StrongDM just deleted the whole layer. No sprints. No stand-ups. No Jira boards. Three people write specs and check outcomes. The coordination overhead that would normally require ten times the headcount does not exist, because there is nothing left to coordinate.

---

## Part Six: The Brownfield Reality

Here is the thing that most articles about AI coding quietly skip over.

Most software in the world is **brownfield** — systems built over years, stacked on top of older systems, with no real documentation and full of decisions that made sense at the time but were never written down. The engineers who made those decisions may have left years ago.

For these companies — which is most companies — the path to a dark factory is not flipping a switch. It is a long migration through a lot of pain.

### The Challenge of Legacy Systems

A legacy codebase is not just code. It is accumulated knowledge in disguise. Business rules buried in conditional logic. Edge cases handled by workarounds nobody remembers creating. Architecture decisions made for reasons that walked out the door with whoever made them.

Before any of this can be automated, it has to be understood. And that is deeply human work — domain experts, engineers who have lived with the system for years, people who know customers well enough to recognize when a "simplification" would quietly break something that matters.

The system itself becomes the specification. Before you can replace it, you have to read it carefully enough to describe what it actually does — not what you think it does, not what the documentation says it does, but what it actually does, including the weird bits.

### The Migration Path

For most organizations, this happens in stages and there are no shortcuts.

Start by using AI at Level 2 or 3 to move faster on current work while you plan the deeper change. This buys time and builds team familiarity with AI-assisted development before the harder transition begins.

Then use AI to document what exists. Feed the legacy system to an AI and extract behavioral descriptions from it. Build scenario suites that capture what the software currently does — including the edge cases and the quirks. This is the foundation everything else rests on.

Then rebuild your verification pipeline around behavior rather than implementation. The goal is to know whether software works without having to read it.

Then — and only then — shift new development to autonomous agent patterns. New features, new services, new integrations go through the autonomous pipeline. Legacy maintenance stays human-supervised until the specs are solid enough to hand off.

This takes months in most organizations. Years in large ones. There is no shortcut through the documentation work, and no way around the organizational discomfort of changing how teams operate. Anyone who tells you otherwise is selling something.

---

## Part Seven: The Collapsing Junior Developer Pipeline

This part is hard to read if you are early in your career, or if you manage people who are. But it is better to understand it clearly than to be surprised by it.

A Harvard study found junior developer employment dropped **9 to 10 percent** within just six quarters of widespread AI coding tool adoption. UK tech graduate job postings fell 46% in 2024, with projections of another 53% drop by 2026. US junior developer postings declined 67%.

These are not forecasts. They already happened.

### The Broken Apprenticeship Model

The traditional path into software worked like this: you started with the simple stuff. Small features. Bug fixes. Routine tasks. Low stakes, fast feedback, plenty of room to learn by making mistakes. Senior engineers mentored you, reviewed your work, and gradually handed you more responsibility.

AI has taken over the simple stuff. Not perfectly, not always — but well enough that companies are no longer hiring juniors to do it.

The apprenticeship model is not broken because anyone decided to break it. It broke because the entry point was automated. The first rung of the ladder is gone, and nobody has agreed on what to put in its place yet.

Some organizations are experimenting with structured learning programs — more like medical residency than traditional hiring — where junior engineers work alongside AI systems, evaluate outputs, and learn through assessment rather than implementation. These are promising, but still rare.

### The Rising Bar

What companies do want is becoming clearer. Engineers who can hold an entire product in their head — user needs, business constraints, technical tradeoffs, all at once. People who can write a specification that leaves nothing important ambiguous. People with real customer intuition, not just technical skill.

The honest version: being a decent engineer who ships solid code at a steady pace used to be enough. It is not enough anymore. The bar moved fast and it is not moving back.

---

## Part Eight: The New Shape of Software Organizations

### The Generalist Advantage

When AI handles implementation, the value shifts to knowing what to build — and that requires understanding a lot more than code.

A database specialist who can tune queries is useful. But the person who understands the database, the users running those queries, the business process generating the data, and the downstream system consuming it — that person is much harder to replace. AI can write the query. Only someone who understands the whole picture can decide what the query should be asking.

Generalists who can hold systems, users, and business constraints together in their head are becoming the most valuable people in the room. That is a real reversal from how the industry thought about hiring for most of the past decade.

### Radical Flatness

Look at the companies already operating at the frontier. Cursor: $500 million in annual recurring revenue, a few dozen employees, roughly $3.5 million in revenue per person. Midjourney. Lovable. These companies produce five to six times the revenue per employee of a typical SaaS business.

Their org charts are nearly flat. A small group of people who deeply understand what users need, translate that into clear specifications, and direct AI systems to build it. The middle layers — team leads, project managers, coordination roles — are mostly absent, not because they were cut in a dramatic restructuring, but because there is genuinely nothing left for them to coordinate.

The hierarchy in traditional software companies exists to manage human complexity. When AI reduces that complexity, the hierarchy becomes expensive overhead.

### What Cannot Be Automated

Look at every role that survives the transition and you will find one common thread: judgment that cannot be written down.

Knowing what to build and for whom. Understanding what a customer actually needs versus what they say they need. Sitting with ambiguity long enough to resolve it into something real. Anticipating second-order effects. Caring enough about the outcome to push back when a spec is wrong.

These are not skills you can put in a prompt. They are the source of the prompts. And the people who have them will find that AI makes them not less relevant, but dramatically more powerful.

---

## Part Nine: The Demand That Never Saturates

Every time computing got dramatically cheaper, the world did not produce the same amount of software more efficiently. It produced explosively more software — for entirely new people, solving entirely new problems.

Mainframes were for large corporations. Then PCs made software accessible to individuals. Then cloud made it possible for tiny startups to build at scale. Each transition did not shrink the market. It opened entirely new ones.

AI will do the same thing, only faster.

Right now, a rural hospital cannot afford a custom patient scheduling system. A mid-sized manufacturer tracks its supply chain in spreadsheets because custom software costs more than it can spend. A small business runs critical operations on tools designed for someone else because nothing better is within reach.

As AI drops software production costs by an order of magnitude, these markets open. The total demand for software is not anywhere close to being saturated. It never was. The only thing that limited supply was cost, not imagination.

### The Shifting Bottleneck

The constraint changes. It used to be: *can we build this?* With AI, that question dissolves faster than anyone expected.

The new constraint is: *what should we build? Who is it for? What does done actually look like?*

The people who thrive in this world are the ones hardest to replace — those with deep customer understanding, systems thinking, and the ability to turn a fuzzy problem into a precise specification. The dark factory does not replace these people. It amplifies them. A sharp product thinker with a small team and access to autonomous engineering capacity can do what previously required a hundred people.

The quality of your thinking becomes the only real limit.

---

## Conclusion: The Work That Remains

The dark factory is real. It works. The teams that built one are accelerating, and the gap between them and everyone else is not staying the same — it is compounding.

And most organizations are still at Level 2. Using AI as fancy autocomplete. Calling it transformation. Getting slower. Wondering why the gains are not showing up.

The technology is not the problem. The technology is ready. It has been ready.

What is not ready is the hard, unglamorous work underneath: documenting systems that have decades of implicit knowledge locked inside them. Writing specifications precise enough that a machine can execute them. Rebuilding verification around behavior instead of implementation. Redesigning organizations around judgment instead of coordination. Figuring out how to bring the next generation of engineers into a world where the entry-level work has been automated.

None of this is comfortable. All of it takes longer than anyone wants. Most organizations will resist it until competitive pressure makes resistance impossible.

But here is the thing — and this is the part worth sitting with.

The bottleneck is no longer what you can build. For the first time in the history of software, almost anyone with a clear enough idea and a good enough specification can build almost anything.

The only question left is: do you know what should exist?

The dark factory is waiting for the specification. What you write for it is entirely up to you.
