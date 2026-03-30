# Building Real Software With Claude Code — A Guide for Non-Engineers

**You don't need to know how to code. You need to know what you want.**

This guide documents a repeatable process for building fully functional, custom software using Claude — Claude Chat as your design partner and Claude Code as your implementation team. It was developed over months of building a complex personal dashboard from scratch, by someone who isn't a software engineer.

If you have deep knowledge in any field — finance, medicine, logistics, education, auditing, whatever — you already have what it takes. The bottleneck was never your ideas. It was the gap between knowing exactly what you need and being able to build it. That gap is gone now.

---

## The Mindset Shift

Before any steps or tools, something has to change in how you think about computers.

The old mental model goes something like: *"It's a computer. I can't code. It probably can't do all that much. I can't trust AI to build real things."* Every one of those assumptions is outdated. But there's a second, subtler trap that catches people who've already gotten past the first one: *"I've used some software before, I know how a couple changes to our existing systems could fix a small problem."* That's still thinking too small. You're starting from what currently exists and imagining minor improvements. Instead, think about what *needs* to happen — what the ideal workflow actually looks like if you designed it from scratch with no constraints. Existing software was built by companies that cut corners, because for most of history good developers were a scarce and expensive resource. Features got generalized. Workflows got averaged. What you got was "good enough for most people," which really means "not quite right for anyone."

There's also a fear of over-personalizing — a sense that building something just for you is wasteful or impractical. That instinct comes from the old world. We're entering an era of hyper-personal software: systems built for exactly one person, tailored to exactly how they think and work. Not a one-size-fits-all product that you adapt to, but something that adapts to you from the ground up. That's what this process lets you build.

Here's the reframe: **don't think about computers at all.** Instead, imagine you're hiring a perfect team. You walk into an office. There's a lead engineer who's smarter than anyone you've met, works instantly, never gets tired, and genuinely wants to understand your vision. Behind them is an entire implementation team that can build whatever the lead engineer designs. Your job isn't to tell them *how* to build — it's to tell them *what* and *why*.

You're the customer who knows the domain. You're also the manager who approves everything before it ships. That's it. Those are your two jobs.

When you imagine what you want to build, **imagine it as perfect.** Don't pre-compromise based on what you think computers can do. Don't scope down because "that sounds too complicated." Describe the system the way you'd describe it to a brilliant colleague who happens to be able to build anything. The tool will tell you if something genuinely isn't possible — but you'd be shocked how rarely that happens.

This isn't about making a basic app. You can build a fluid, personalized system that operates exactly the way your brain works — tailored to your specific workflows, your specific domain, your specific life. Nobody else will ever build this for you because nobody else fully understands what you need. Now you don't need them to.

**A note on software independence.** When you start imagining what to build, your first instinct might be "there's an existing service I can connect to" or "there's already a subscription product that does something similar." Stop and ask: why? If you build it locally, it's free — no subscriptions, no monthly fees. It has only exactly what you need, nothing you don't. Expansion is easy when you spot areas of improvement. And it's completely private — your data stays on your machine. There are exceptions; sometimes your life is already embedded in a platform and bridging to it makes sense (like pulling in a Google Calendar you've used for years). But defaulting to "I'll just build it myself" instead of "I'll find a product that sort of does this" is a genuine shift in how you can operate now.

---

## The Two Claudes

This process uses two tools, and understanding the difference between them is essential.

**Claude Chat** (claude.ai, the browser conversation) is your **design partner**. This is where you think out loud, explore ideas, refine your vision, and produce detailed plans. Claude Chat is the lead engineer in the metaphor — it asks clarifying questions, pushes back on weak ideas, suggests things you hadn't considered, and ultimately produces a blueprint that's ready to build.

**Claude Code** is your **implementation team**. This one is important to understand clearly, because it's easy to get confused about what Claude Code actually *is*. Claude Code is an AI builder that lives on your computer. Its brain runs on Anthropic's servers, and it works in your files — creating folders, writing code, wiring things together. When it's done, it puts its tools down and goes home. It is not embedded in your project. It's not running inside your app. Think of it like hiring a contractor to build a house: they show up, do the construction, and leave. The house stands on its own. If your finished project happens to use AI features (like a chatbot or smart assistant within the app), those are things Claude Code *set up for you* — they're part of the house, not the contractor.

This distinction matters because Claude Code is the bridge between the blueprint and a working product. It's remarkably good at getting things right in one pass — *if* the blueprint is good.

The quality of what Claude Code builds is directly proportional to the quality of what Claude Chat designed. This is why most of this guide focuses on the design conversation, not the implementation step.

---

## The Process

### Phase 1: Explore Your Vision

**Goal:** Get the idea out of your head and into a conversation.

Open Claude Chat and start talking. Describe what you want to build in plain language. Don't worry about structure, technical terms, or whether it "makes sense" as software. Just describe the problem you're trying to solve and what a perfect solution would feel like to use day-to-day.

**What this looks like in practice:**

> *"If I'm going to set up a system that manages different areas of my life — health, finances, investments, maybe a calendar — what are the major topics I'd want? I'm imagining some kind of dashboard where each area has its own section. I want to be able to talk to it in natural language, like through a chat, and have it understand what I mean and update the right thing. How should I think about this?"*

That's it. It's not a spec. It's not even fully formed. It's just the seed of an idea, spoken out loud. Claude Chat will immediately begin asking clarifying questions — *where does this live? how do you imagine feeding it information? what does "done" look like for a first version?* — and those questions are where the real design happens.

**Key principle: spend more time here than feels productive.** The exploration phase isn't a warmup before the real work. It *is* the real work. Make propositions. Suggest alternatives. Imagine the system working in three different ways before you pick one. This is where clarity comes from, and clarity is what makes everything downstream work.

### Phase 2: Let Claude Be the Engineer

**Goal:** Establish the right dynamic for the design conversation.

Once you've described the core idea, explicitly tell Claude Chat to take the lead on technical decisions. Something like:

> *"You're the lead engineer. I'm the client. I know what the end product should feel like, but the technical decisions are yours. If it's something an engineer should decide, don't ask me — just decide. If it's something only I'd know, ask me."*

This framing does two important things. First, it stops Claude from asking you questions you can't answer ("Should we use PostgreSQL or SQLite?" — you don't care, and Claude knows the right answer anyway). Second, it frees you to focus on what you're actually good at: knowing the domain, evaluating whether suggestions match your vision, and catching things that feel wrong.

**Your job in this dynamic:**

- Describe what things should *feel like* to use
- Say yes or no to proposals
- Flag when something doesn't match your mental model
- Provide the *shape* of what you want — not the technical knowledge, but the specific vision

That last point deserves explanation. Claude already knows your domain in the abstract. It knows what calorie tracking is, what a reading log is, what an audit pipeline looks like. What it doesn't know is the *shape* you want — the specific way you imagine interacting with it. For example: Claude knows how to track calories, but it doesn't know you want a dynamic heatmap that shows your activity over 90 days at a glance. It knows what a notes app is, but it doesn't know you want something that looks and feels like Obsidian, stripped down to only the features you use, connected to your other creative tools. The shape is the difference between a generic solution and *your* solution. That's what you bring.

**Not your job:**

- Choosing frameworks or technologies
- Deciding database structures
- Knowing what's technically feasible
- Writing any code or pseudocode

Save your mental energy for vibe-checking. When Claude suggests a system, close your eyes and imagine using it. Does it feel right? Does it match how you actually work? That instinct is worth more than any technical opinion you could form.

**Critical habit: write things down mid-read.** Claude's responses during design conversations will be long, dense, and stimulating — the perfect combination to derail a floating thought. When you're reading a response and something tickles your brain — a detail that's 90% right, a phrase that sparks a better idea, a small disagreement — **stop reading and jot it down in the chat box immediately.** Don't tell yourself you'll mention it when you get to the end. You won't. You'll get absorbed in the next paragraph and the thought will evaporate. Just type your reactions into the message box as you go — short fragments are fine — and clean them up into a coherent response when you're done reading.

This sounds minor but it's one of the single biggest practical habits that separates productive design sessions from ones where good ideas get lost.

### Phase 3: Refine and Expand

**Goal:** Sharpen the vision and let scope grow intentionally.

After a few rounds of back-and-forth, Claude Chat will have a solid understanding of what you're building. Now push further. Ask it to poke holes. Ask what's missing. Ask what features would be "obvious additions" that you haven't mentioned yet.

Here's a counterintuitive principle: **scope creep is your friend at this stage.** In traditional software development, expanding scope is dangerous because every addition costs engineering time and risks breaking things. But here, the math is different — Claude Code can take a well-designed plan and build it remarkably fast. The real danger isn't building too much. It's building in one direction and then realizing halfway through that you want to go a different direction.

Refactoring — restructuring something that already works to accommodate a new idea — is where even Claude Code gets fuzzy. Building strong in one direction is safe and fast. Tearing something apart and rebuilding it because your vision shifted mid-construction is slow, error-prone, and demoralizing. In the worst case, one bad refactor can leave your codebase in a half-transitioned state that Claude Code can't make heads or tails of. All it takes is one poorly timed interruption and you're spending a full day trying to dig yourself out, redesigning things on the fly, patching broken connections. A real human developer would spend a week in that same hole. It's best to avoid it altogether with a clear shot to the finish line.

Sometimes mid-course corrections are unavoidable — that's reality. When they happen, keep them as small and contained as possible. But the design phase is your best weapon against this: **get the vision zoomed out as far as possible without losing sight of what matters.** See the whole system in your head, on a personal level, before a single line of code exists.

So when Claude suggests a feature and you think "oh, that would actually be really useful" — say yes now, while it's free. If it suggests something that sounds cool but doesn't serve the core vision, say no. The goal isn't to add everything; it's to identify the things that are obvious in hindsight so they can be part of the design from the start, not bolted on after the fact.

### Phase 4: Test the Design With Roleplay

**Goal:** Find problems before any code exists.

Before building anything, have Claude roleplay as both the user and the system. Walk through specific scenarios:

- *"Walk me through what happens when I open the app for the first time."*
- *"I just got a new client. Show me the flow of adding them and setting up their engagement."*
- *"It's Monday morning and I need to know what's urgent this week. What do I see?"*

These are user stories, and they expose edge cases, missing features, and awkward flows that are invisible in the abstract. You'll find things like: "Wait, there's no way to mark something as urgent" or "What happens if a document belongs to two different engagements?"

This is also where disagreements surface — Claude might have interpreted something differently than you intended. That's exactly what you want to discover now, when changing direction costs nothing.

### Phase 5: Adjust and Re-Refine

**Goal:** Incorporate what you learned from roleplay into a tighter vision.

The user story walkthroughs will almost certainly reveal things you want to change. Maybe a feature you planned isn't necessary. Maybe something you dismissed early on turns out to be important. Maybe the overall structure needs to shift.

This is fine. You haven't written a single line of code. Changes at this stage are free.

Go back to Claude Chat and pitch the revised vision. Re-refine it. Get alignment. You'll know you're ready to move forward when the conversation starts to feel repetitive — when Claude's suggestions are all things you've already considered and your responses are mostly "yes, that's right."

### Phase 6: Generate the Spec

**Goal:** Have Claude Chat produce a detailed implementation blueprint.

This is the handoff artifact — the document that bridges your design conversation and the actual build. Tell Claude Chat to write a comprehensive spec for the feature.

**What a good spec includes:**

- A clear overview of what's being built
- The data structure (what information gets stored and how it's organized)
- What the user interface should look like (layout, components, interactions)
- Specific behaviors (what happens when you click this, what updates when that changes)
- What to build now vs. what to save for later
- Edge cases and important notes about things that could go wrong

The spec Claude produces will likely be very technical — full of terms and structures you don't fully understand. **That's fine. You don't need to understand the technical details.** What you need to do is read the *overview sections*, confirm they match what you discussed, and trust that the underlying detail is faithful to the conversation that produced it.

Think of it like working with an architect. You don't need to understand the engineering drawings. You need to look at the floor plan and say "yes, this is the house I described."

If the overview doesn't match your vision, say so. Claude will regenerate it. If it does match, approve it and move on.

### Phase 7: Hand Off to Claude Code

**Goal:** Get the spec implemented as working software.

Take the spec from Claude Chat and give it to Claude Code. A simple lead-in sentence followed by the full spec works well — something like: *"Next feature is going to be a D&D character support page for the creative and writing tab. Here's the details:"* and then paste the whole thing. Claude Code doesn't need you to summarize or restructure what Claude Chat produced. It can handle the full spec as-is.

Unlike Claude Chat, **Claude Code doesn't need a README for context** — it can look around your entire codebase and see the real code, the file structure, and how everything connects. The README is for *Claude Chat*, which can't see your project files. When you start a new Chat session for a new feature, attach or paste your README so Chat understands the current state of the project. Claude Code figures that out on its own.

**What to expect:** Claude Code will think for a while (sometimes several minutes for large features), then produce a batch of files. For well-specified features, it's common for Claude Code to get the implementation right — or very close to right — in a single pass. This is the direct payoff of the thorough design phase.

**A warning about speed:** The first time Claude Code finishes a major feature, you might not be ready for it. It'll work for eight or nine minutes on something that would take a human developer weeks or months. You'll sit there slightly stunned, realizing you need to get to work planning the next thing. This drag is harmless but real — and it's why the parallel workflow matters. When you hand the spec to Claude Code, mentally consider it done and working. Then ask yourself: *what's next?* The way the two Claudes are separated, any planning you do with Chat won't interfere with what Code is building. They're parallel, not linear. **While Claude Code builds**, go back to Claude Chat and start the design conversation for your next feature. Once you get into this rhythm, you're never waiting.

### Phase 8: Test and Batch Your Feedback

**Goal:** Find issues, collect them all, then fix them in one pass.

Once Claude Code finishes, go through the result carefully. Open the interface, click everything, try the flows you roleplayed earlier. You will almost certainly find issues — but they're usually small and cosmetic:

- Spacing or alignment problems
- A button that doesn't look quite right
- A missing option you expected to see
- A color or font that feels off
- An interaction that works but feels clunky

**Critical habit: do not send issues to Claude Code one at a time.** Instead, keep a running list as you test. Write down everything you notice, no matter how small. There are two reasons for this:

1. **Efficiency.** Claude Code thinks deeply about each task. Sending ten tiny fixes individually means ten full thinking cycles. Sending them as one list means one thinking cycle that handles all of them.

2. **Memory.** Once you've found four or five issues, the earlier ones start slipping from your mind. If you're sending them one at a time, you'll forget things. Writing them down as you go ensures nothing gets lost.

Once your list is complete, send the whole batch to Claude Code along with clear expectations for each fix.

### Phase 9: Iterate Until Satisfied

**Goal:** Repeat the test-and-fix cycle until the feature feels right.

After the first round of fixes, test again. You'll likely find a few more things. Collect them, batch them, send them. This cycle typically takes two or three rounds before a feature feels solid.

You'll know a feature is done when you're using it and it just *works* — when you stop noticing the interface and start focusing on the content.

### Phase 10: Loop Back

**Goal:** Start the next feature from the top.

Return to Claude Chat. Start a new conversation (chat sessions get token-heavy over long design discussions and work better fresh for each major feature). Begin the exploration phase for your next feature.

The cycle repeats: explore → refine → roleplay → adjust → spec → build → test → fix → loop.

---

## Summary of the Loop

```
┌─────────────────────────────────────────────────┐
│              CLAUDE CHAT (Design)                │
│                                                  │
│   1. Explore your vision (plain language)        │
│   2. Let Claude lead technical decisions         │
│   3. Refine and expand scope intentionally       │
│   4. Roleplay user stories and edge cases        │
│   5. Adjust the design based on findings         │
│   6. Generate the detailed spec                  │
│                                                  │
├─────────────────────────────────────────────────┤
│              CLAUDE CODE (Build)                 │
│                                                  │
│   7. Hand off the spec                           │
│   8. Test the result, batch your feedback        │
│   9. Iterate fixes until solid                   │
│                                                  │
├─────────────────────────────────────────────────┤
│   10. Loop back to Claude Chat for the next      │
│       feature — start a fresh conversation       │
└─────────────────────────────────────────────────┘
```

---

## Things That Help Along the Way

**Keep a README.** A plain-language document that describes what your project is, what it does, and how it's structured. This is the single most useful piece of context for Claude Chat — it onboards the design partner quickly so you don't have to re-explain your entire project every conversation. Update it as a **cap-off action** when you decide a feature is done: commit your code to GitHub, then tell Claude Code to update the README to reflect what was just built. Think of it like saving your game at a milestone. Claude Code might eventually get in the groove and update it on its own, but until that happens, make it a deliberate step — actually tell it to do the update instead of just moving on to the next thing.

**Start with one thing.** Don't try to build your whole system at once. Pick the single feature that's most concrete in your mind — the one where you can most clearly picture what it looks like and how you'd use it. Build that first. Once it's working, the next feature is easier because you have a foundation to build on and a README to reference.

**The exploration phase protects you from yourself.** This isn't about trusting a system — it's about a well-known reality in software: people describe what they *think* they want, it gets built exactly as they asked, and then they look at it and realize what they *actually* want is something different. This has been the central headache of software engineering for decades. The customer isn't lying or being careless; seeing a working version just clarifies things that were fuzzy in the abstract. The exploration phase — the roleplay, the back-and-forth, the "imagine using it on a Monday morning" exercises — is your best shot at having those realizations *before* anything is built, when course correction is free instead of painful.

**You don't need to understand the spec.** The spec is a communication artifact between Claude Chat and Claude Code. Your job is to verify that the overview and descriptions match what you discussed — not to understand the implementation details. If the summary says "A character sheet with ability scores, combat tracking, and class-specific features" and that matches what you designed together, approve it and move on.

**Imagine the system as perfect.** Don't pre-compromise. Don't assume something is "too complex." Describe what you actually want. The constraint isn't capability anymore — it's clarity of vision. The clearer you are about what you want, the better the result.

**Start new Claude Chat sessions for each major feature.** Long conversations get expensive in terms of tokens per message and context quality. A fresh chat with your README attached gives Claude a clean slate and a solid foundation. Claude Code sessions can run longer since they handle context differently.

---

## Your Flow Devices

Once these four things are connected, you're ready to go:

- **Claude Chat** (claude.ai) — your design partner. A Pro subscription is recommended for the longer conversations that serious design work requires.
- **Claude Code** — your implementation team. It runs through the Claude desktop app on Windows and Mac, so there's no need to deal with a raw terminal if that's intimidating. Follow the setup instructions at [docs.anthropic.com](https://docs.anthropic.com/en/docs/claude-code) to get started.
- **GitHub** — your project's home and backup. Every time you finish a feature, commit and push. This is your version history and your safety net. If you don't have an account, it's free.
- **VS Code** (optional) — a free code editor. You probably won't need it much — it's mostly useful for quick things like checking a config file or copying an API key. Claude Code handles the real editing.

---

## A Final Note

The biggest thing this process taught me wasn't about AI or coding. It was that the barrier between "having an idea" and "having a working system" was never really about technical skill. It was about the assumption that you needed technical skill.

You know your domain better than any engineer you could hire. You know how your work actually flows, where the friction is, what information you need and when you need it. That knowledge is the hard part. The building is the easy part now.

So build the thing. Make it for you. Make it for exactly who wants it.
