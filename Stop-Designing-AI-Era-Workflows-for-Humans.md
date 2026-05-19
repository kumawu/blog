# Stop Designing AI-Era Workflows for Humans — Seven New Principles

Author: @v5ria WK

Lately I've been repeating one claim: **the problem with most workflows today isn't that they're "not AI enough" — it's that they're still shaped like humans.**

Every product-development pipeline we run — requirements gathering, product design, engineering, testing, release — was designed for humans. Fair enough; for the last thirty years humans were doing all of it. But now every one of those stages can be taken over, or at least led, by AI. If at this point you keep "adding AI" inside the existing pipeline, you're just patching AI onto a human-shaped skeleton. When you're done, the bottleneck is still in the same place.

Here are seven things I've been turning over in my head.

## 1. Burn the human-shaped pipeline

The most common mistake looks like this: there's a pipeline with five roles strung together, and we give one of those roles an AI assistant and hope the whole thing speeds up.

That's low-leverage.

The high-leverage move is the opposite: **assume every stage is done by AI, redesign the pipeline from scratch, and then add humans back — only at the points where AI genuinely can't do the job yet.**

These two starting points produce completely different pipelines. A pipeline that starts from humans keeps optimizing for clearer docs, better-run meetings, more thoroughly aligned PRDs — all so that another human can understand what's going on. AI doesn't need any of that. AI passes information between stages as structured, machine-readable artifacts. Every stage you optimized for humans is overhead from AI's point of view.

I call this shift **AI-first, humans embedded**. We used to be humans-first with AI assisting one stage; now AI runs the line and humans plug the gaps. It sounds like a word swap, but in practice the whole shape of the pipeline has to change.

## 2. Outcome-driven, stop reasoning by causation

Humans love causal chains: this person is an expert, therefore their work is good; this process is rigorous, therefore the quality is high; this came from a big-name company, therefore it's trustworthy.

In the AI era you have to actively drop this kind of reasoning.

It's not that causation has stopped existing — it's that verifying it has become cheap. A product decision used to be expensive to actually try, so you had to lean on experience, analogy, and "people who know this industry." Trying it for real is no longer expensive: let AI build the full thing, ship it, auto-collect data, auto-analyze, auto-iterate — let the closed loop run for a week and you'll have the answer.

So stop debating "is this person professional enough" or "is this design reasonable." **Run it end-to-end and let the result speak.** Your job isn't to judge professionalism; your job is to design a closed loop that can actually run.

The biggest resistance to this comes from humans themselves. For many people, admitting that their "expert judgment" isn't that important is harder than admitting they're wrong.

## 3. Harness: stringing capabilities into automation

People are throwing around a lot of words right now: Claude Code, Codex, Cursor, Hermes, Opencode, Superpowers. These are all different implementations of the same idea — I lump them together under the term **Harness**.

A Harness is not a product. It's a framework for taking scattered AI capabilities and assembling them into something that can run long-horizon tasks.

The problem it solves: you have foundation models, MCP tools, subagents, skills, sandboxes — these are all parts. How do you get the parts to cooperate well enough that a multi-day, multi-week task like "build this product" actually runs to completion on its own?

The specific brand name doesn't matter. Today it's Hermes; tomorrow it'll be something else. What matters is that you understand the idea and can design your own working pipeline on top of it.

The way to think about it in practice: **what am I trying to do → where is it stuck → turn the stuck point into a new tool or new skill → next time it won't be stuck.** Repeat this loop, and your Harness gets thicker over time, and the size of the thing you can hand off to AI grows.

## 4. Twenty-four hours is the floor, not the ceiling

The most intense individual developer I've seen burns $1.5M a month on AI. The number is uncomfortable at first, but flip it around: what they're buying is 24×7 uninterrupted execution.

Humans have a fundamental ceiling: there's an upper limit on how many hours a day you can work. Ten is already the edge; beyond that, output goes backwards. AI has no such ceiling. While you're asleep, it can keep running for another fourteen hours.

**So even if AI gave you zero per-hour speedup, just running 24 hours a day already crushes any human by a multiple.** Speedup is the bonus; continuous operation is the floor.

This judgment changed how I evaluate "investing in AI." I used to think: how much time will this tool save me? Now I think: when I'm not around, can it keep working? If it can't, the tool is worthless — when I clock out, it clocks out, and I've thrown the money away.

So the thing I think about most these days is: **how do I keep the running agents busy at all times** — so that when I eat, sleep, or step out, they don't sit idle.

## 5. The ability to evaluate is the real scarce good

Getting AI to run isn't hard. The hard part is: is what it produced any good?

Most people can't answer that. The reason isn't laziness — it's that they lack the ability to evaluate.

The traditional standard for a PRD-writing product manager is "the doc is done." They aren't on the hook for whether the product makes money; that's the commercialization team's job. So they don't evaluate the product — they only evaluate their own artifact: is the doc complete, is the flowchart clear.

This role logic becomes awkward in the AI era, because AI can write the doc ten times faster than they can. If they can't evaluate "is the product good," all they can do is keep evaluating "is the doc good" — and that's exactly the work AI has already absorbed.

**The real scarcity going forward is people who can evaluate.** Evaluate what? Whether this iteration moved closer to the final goal, whether AI's output can be fed straight into the next stage, which metric inside the loop is sliding and why.

A person who can evaluate can manage ten agents in parallel. A person who can't evaluate can't even manage one — because they don't know when to let it keep going and when to stop it.

## 6. How many agents can one person run in parallel

I usually have 5 to 8 tasks running on my desktop at once: one writing code, one generating video, one doing product analysis, one running tests. Every few minutes I switch, check status, give a new instruction, move to the next.

There's a number from research: humans can switch between roughly 5 to 6 tasks at the same time. That's the cognitive ceiling. But you can push it higher if you solve one core problem — **rebuilding context on switch.**

Most of the switching cost goes into "where was I just now." If it takes 30 seconds to recall, then 8 tasks burn 4 minutes per round of switching and the math works against you. But if every agent proactively tells you, the moment you come back, "this is what I did, this is where I'm stuck," the switching cost drops to seconds.

The improvement I most want to build right now is exactly this: have every agent proactively surface its current context on the right side of the screen. **Make switching back not depend on human memory.**

Once that capability exists, the number of agents you can run in parallel has no ceiling. You're no longer doing a single job — you're directing a squad that runs forever.

## 7. FDE is the most valuable role in the AI era

One specific role to close with: **FDE, the Forward Deployed Engineer.**

Palantir was the first place this role really worked. It was never mainstream in classic Silicon Valley, but in the AI era it's becoming one of the most sought-after roles.

The defining trait of an FDE: **they go into the customer's environment like a consultant, taking on the dirtiest real requirements; and they abstract each engagement's lessons back into reusable platform capability, like a platform engineer.**

Why does this role matter so much in the AI era? Because every one of the six points above needs someone on the customer side who can translate fuzzy needs into machine-executable tasks. AI can write code, evaluate, run 24 hours — but it needs a human at the front telling it: **what is the real problem to solve this time.**

A traditional product manager can't do this. A traditional consultant can't either. The former is too far from the customer; the latter is too far from the implementation. The FDE sits at both ends at once.

If you're thinking about your own career direction, I'd point you toward FDE: **stick close to one real business scenario, untangle the mess inside it, and be able to use AI to actually solve it.** People who can do all three of those things will be the most valuable hires for the next several years.

## Ending

All seven points are saying one thing:

**Stop designing AI-era workflows for humans.**

Pipelines designed for humans leave a slot for a human at every stage — even when the slot is no longer necessary. Add up those slots and you get the ceiling on the next generation of productivity.

The right move is the opposite: **first assume there are no humans and get the pipeline running; then add humans back, only at the few points where they truly can't be replaced.**

On that path, three kinds of people will be the most valuable for the next few years: those who can evaluate, those who can switch between agents, and the FDEs who stay glued to the business.

Everything else, the machines can do.
