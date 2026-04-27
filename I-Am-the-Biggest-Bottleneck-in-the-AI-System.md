# I Am the Biggest Bottleneck in the AI System

Author: @v5ria WK

> English · [中文](./我是AI系统里最大的瓶颈.md)

I was talking with a friend recently, and said one thing: **I am, without a doubt, the obstacle right now.**

It sounds ironic to say out loud, but the more I think about it, the more I think it's true.

## Where the problem comes from

We're building a system that involves a huge amount of AI interaction. In theory, AI dialogues are supposed to happen tens of thousands of times, with every round being a chance to push things forward. But the reality is that across those tens of thousands of dialogues, most of them are way too inefficient.

It isn't AI's fault. AI is getting smarter, responses are fast, you get a result in seconds. The problem is on the human side.

Once a human enters the loop, most of the time is spent **learning**, not pushing forward. Understanding the AI's output, digesting it, thinking about how to phrase the next instruction, hesitating about whether to accept the result. This process by itself burns through huge amounts of time, and lower-skilled participants will also drag the direction off course and introduce unnecessary confirmation loops.

The result: human participation slowly becomes the bottleneck on the system's iteration speed.

## The wind has shifted

I've noticed a trend: more and more people are talking about **taking the human out of the loop**.

Not that humans don't matter, but that for the act of *iterating the system*, the ideal state is: AI sets its own goals, executes them, checks them, reflects on them, and re-plans for the next round of optimization. A complete self-iteration loop.

Humans only need to give direction at the start and accept the result at the end. All those low-efficiency confirmation, approval, and correction loops in the middle should be cut wherever possible.

Looking back at the evolution of AI-assisted development, it has roughly gone through three stages:

1. **The completion era**: AI does autocomplete, the human types one character at a time, AI guesses the next step.
2. **The synchronous Agent era**: humans direct an Agent through a "prompt → response" loop, the Agent can handle more complex tasks, but every step still requires real-time human participation.
3. **The autonomous Agent era**: Agents run independently, completing larger tasks over longer time horizons, with less human intervention. The human's role shifts from "line-by-line guidance" to "defining the problem + reviewing the result."

The third stage is arriving, and it's arriving faster than most people expected.

**Synchronous interaction is itself the bottleneck.** You sit there staring at the Agent's output, waiting for it to generate, reading it, giving feedback, waiting for it to revise — and most of what your brain is doing during that loop is "confirmation," not "creation." On top of that, while you're sitting there, the number of Agents you can run at the same time is just a handful.

A better mode is to let the Agent run independently in an isolated environment, hand the task off, and go do something else. The Agent works for hours, iterates and tests repeatedly, and when it's done it returns the result in a form that's easy to review quickly — logs, screenshots, live previews — instead of making you read every line of the diff.

This realization made me a little anxious, because it implies that **inside an AI system, the room left for humans to create value is shrinking** — at least at the level of "execution."

## I ran an experiment last week

Last weekend I built an AI exam system as a side project. I designed a task for the AI and let it self-iterate.

It ran for two days.

Two days later, the result came out, and everyone involved was happy with it.

I barely intervened in the middle. What it was doing during those two days, I mostly only looked at after the fact.

That outcome left me both excited and more anxious — if AI can finish this in two days, and my being there might actually interrupt it and slow it down, then where is my value?

The experiment made me realize that the developers running ahead of the curve are already working this way:

- Almost 100% of the code is written by Agents
- Human time is spent on **breaking down problems, reviewing results, and giving feedback**
- Multiple Agents are launched in parallel, instead of holding one Agent's hand all the way to the finish line

You're no longer writing code. You're building a **factory that produces software**. The factory is staffed by a team of Agents, and your job is to set the direction, equip the tooling, and review the output.

## What is the paradigm

What I think about every day now is: how do I design better tasks for the AI, so that it can self-iterate more times, work longer, and produce more value.

Looking back at the exam system experiment, I think the core reason it worked is this: **"exam" itself has objective answers, so the AI can run, score, and tell whether each iteration is better or worse — entirely on its own. The evaluation criteria are baked into the task.**

That's the essential feature of a self-iterable task.

So the question of whether a task is suitable for AI self-iteration really comes down to one question:

> **Can the criteria for success be automatically verified by a machine?**

- Yes → it can self-iterate; humans only need to define the goal at the start and accept the result at the end
- No (it requires human subjective judgment) → humans are still necessary, but their intervention should be compressed to the minimum

Based on this, I've worked out a few concrete practices:

**1. Front-load and quantify the acceptance criteria**

Don't say "build a good recommendation system." Say "build a recommendation system whose CTR on the test set beats baseline by 5%." The more specific the goal, the more room the AI has to judge for itself, and the fewer times it needs to come back and check with you.

**2. Give the AI a test environment it can run repeatedly**

Code has unit tests, content has a scoring rubric, data has schema validation. This is the infrastructure of self-iteration. Without it, every time the AI makes a change it has to ask you "is this right?" — and you become the bottleneck again.

The ideal is to give the Agent a fully isolated sandbox: it can install dependencies, run tests, and build the project freely, without affecting your local environment. Inside the sandbox, the Agent iterates over and over until all tests pass and the output is reliable enough, and only then does it hand the result back to you.

**3. Move your point of intervention from "process review" to "goal-setting + course correction"**

The old mode: AI shows an intermediate result → I look → I give feedback → AI continues.
The better mode: spend more time at the very beginning getting the goal and the boundaries clear → AI runs on its own → only step in when it gets stuck or goes off course.

Spend twice as long up front defining things clearly, in exchange for not intervening at all in the middle.

**4. Use artifacts instead of live monitoring**

Don't watch the Agent's real-time output. Have it produce, when it's done, an artifact you can review quickly — a log summary, key screenshots, a comparison of results. That's the only way you can run several Agents at once: you can't watch three Agents' live processes simultaneously, but you can spend a few minutes browsing three artifacts after they all finish, and pick the best.

**5. Parallel rather than serial**

Running one Agent at a time, sitting there waiting for it to finish — that's still a human dictating the rhythm. The better way is to launch multiple Agents at once, have them tackle different tasks in parallel, or have multiple of them attempt the same task with different approaches and pick the best result at the end.

This changes what "efficiency" even means: not "each iteration is faster," but **"more iterations run in parallel per unit of time."**

## Where the human's real value is

Once the paradigm becomes clear, my view of "the human's value" also shifts.

The human shouldn't be the reviewer in the middle of the process. The human should be:

- **The one who defines the problem**: what's worth solving, how to prioritize
- **The one who designs the evaluation criteria**: what success looks like, how to measure it
- **The one who spots when things go off course**: is the AI iterating in the right direction, or is it optimizing the wrong metric

These three things are the ones AI can't replace yet, because they require deep understanding of the business and the user.

Concentrate your energy here, and you stop being the bottleneck — you become the lever. Your value isn't in laying every brick by hand. It's in designing the blueprint of the factory and making sure the production line doesn't drift.

## The other thing I figured out today

There's a deeper problem with humans being in the middle of the loop, beyond just being slow.

**Human participation forces the AI's process to be "downsampled" to a level a human can follow.**

When AI iterates autonomously, the intermediate steps it designs don't need to be explained to anyone, don't need to fit human work habits, don't need to follow the linear "do A first, then B" logic that a human can read off a page. It can explore dozens of paths at once, finish the task in an order that looks chaotic to a human, take shortcuts a human would never voluntarily take — not because those shortcuts are wrong, but because a human can't read them, and so a human won't dare walk them.

The moment a human steps in, all of that is interrupted. The human needs to know which step we're on, needs to confirm whether the next step is reasonable, needs the AI to lay out its reasoning. The act of "explaining" itself locks the AI's process inside the range of what's human-comprehensible. The slowdown isn't that explaining is slow — it's that **comprehensibility is itself a constraint**, and it prunes off all the moves that work but can't be explained.

That made me reread why "accepting the result" matters more than "participating in the process."

You don't need to understand how AI got to the result, the same way you don't need to understand the inner workings of a compression algorithm — you just need to know the file restores correctly and no data was lost. What you need is a good acceptance standard that can tell whether the result is right, not a good review process that ensures every step happens within your line of sight.

In other words: **the urge to control the process is another form of being the bottleneck.** Letting go of understanding the process, and focusing on defining the goal and accepting the result, is what actually frees the human from the loop.

## How much time is left

The urgency of this is probably higher than most people think.

From the data I've been seeing, Agent usage is growing extremely fast, and is already starting to overtake the traditional line-by-line writing model. The window we have to adapt to the new paradigm is short — if you don't start thinking about "how to let the Agent work autonomously" now, by the time this mode becomes the industry standard you may not even have the right to be anxious about it anymore, because you'll already be out of the production loop.

## Closing

If I had to compress all of it into one line:

**We used to be anxious about "will AI take my job?" Now I'm anxious about "am I dragging AI's job down?"**

That shift came faster than I expected. This isn't one person's feeling — it's a structural change happening across the whole industry. The only question is: are you building the factory, or are you still laying bricks by hand?
