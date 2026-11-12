# From Compression to Pain: The Next Layer of AI Memory

Author: @v5ria WK

> [中文](./从压缩到疼痛：AI记忆的下一层.md) · English

Let me start with a Friday afternoon. It's an illustration, not something that has already happened.

Say you have an AI Agent that drafts your weekly report. Last week you corrected it twice. Sales figures should be month-to-date, not the single week, and client names should be written in full, because your manager doesn't know the abbreviations. It fixed both on the spot, and that version was good. This Friday's draft arrives with single-week figures and abbreviated client names again.

The same week, the AI Agent that books your meetings puts one on Monday at 9 a.m., even though you told it Monday mornings are kept for the team meeting. The AI Agent that files your expenses puts a local taxi receipt under "travel" again. Finance sent the same claim back last month and said local taxis go under "transport". The AI Agent that sorts your email drops a message from a long-standing client into "read later" again.

None of these AI Agents is slow-witted. When you point out the mistake, each one understands immediately and fixes it correctly. The trouble is the next time. The last mistake didn't stay with it. Every session starts from zero.

This essay is about what sits behind that. My view is that today's AI is already very good at compressing information, and that the next thing to compress is why it does what it does and what it cares about. To get there, an AI has to be able to carry its own failures. I'll go through it in order: how far compression has come, how pain differs from reward, how to give an AI something at stake, how the memory is laid out, how this compares with two other ideas about AI memory, and what has to exist first. I'll end with where I might be wrong.

## How far compression has come

A large language model does two things. During training, it compresses the information in a huge amount of text into the model. During use, it releases the part your question needs. When you ask it to write an apology email, it isn't retrieving one particular email it has seen. It produces one that fits your situation from everything about writing that was compressed into it.

The second step is compression between AI Agents. A lot of work is already split across several AI Agents. One reads a hundred emails, another books meetings based on them, a third writes up the minutes afterwards. What they pass to each other is changing. Early on, one AI Agent handed the next the whole pile of raw material. More and more, what gets passed is a conclusion and a judgement: "These three emails need a reply today, and in one of them the client is chasing a quote." The next AI Agent doesn't need to read the hundred emails.

The third step belongs to the stage I wrote about last time, the one I expect around 2027, when an AI Agent sets goals and standards on your behalf. At that point, passing along outputs isn't enough. What has to be passed is intent: why I'm doing this, and what I care about. You could call this higher-order intentionality. It means not only wanting to do something, but knowing why you want it, and knowing which side you care about more when two things pull against each other. Compressing outputs gets the work done. Compressing intent is closer to compressing presence: the AI Agent acts the way you would act if you were there, not just the way you acted last time.

Take the meeting example. If the AI Agent that books meetings receives only "book Wednesday afternoon," it will only ever book Wednesday afternoon. If what it receives is "this client is thinking about switching suppliers, and you want to meet before they decide," then when Wednesday afternoon is full, it knows to book Tuesday rather than push the meeting into next week.

Where does intent come from? A large part of it comes from failure. When you say "no meetings on Monday morning," there may be a story behind it: a team meeting got squeezed out once, and the team spent a week not quite aligned. A rule that records only the conclusion, and not why the mistake happened, can only be followed to the letter. When a case comes up that the rule didn't cover, the AI makes the same kind of mistake again.

So if intent is built partly out of failure, the question becomes: what does it take for an AI to actually have failed, in a way that carries forward?

## Reward is not pain

The main way we train and adjust AI today is reward. Doing the right thing earns points; doing the wrong thing loses them. A reward function is an external rule, written in advance. Who wrote it and how it scores are both outside the AI.

Pain is different. Pain needs a self that persists across time. The one that failed last time is the one that bears the consequences, and it is also the one making the next choice. And that next choice is different because of what happened last time.

Go back to the weekly report. When you correct the AI Agent, it does lose points, in a sense, inside that session. But when the session ends, that result isn't kept anywhere. From its own point of view, the AI Agent writing next Friday's report is not the one that was corrected last week. Without an identity that continues across time, there is only scoring. There is no pain.

I want to be careful about what I mean here. I'm not saying the AI has feelings. I mean a structure with three parts. A failure is recorded under the name of one continuing subject. That subject can't erase it. And it changes what the subject does next. People have this structure, which is why people learn from mistakes. Most AI Agents today don't have it.

Short drama production has the same gap. Say an AI Agent generating video lets the lead character's jacket change between two clips. A reviewer marks it as a failure, the clip is regenerated, and the corrected version passes. The next episode starts in a new session, and the AI Agent producing it has no idea that anything went wrong in the last one.

## How to give an AI something at stake

To make a failure land on the same AI, I think three things are needed.

**Persistent memory.** Its experience has to be kept across sessions, especially its failures. This doesn't mean keeping chat logs. It means keeping, for each failure, what went wrong, what it was thinking at the time, and how it turned out.

**Acceptance records that can't be rewritten.** Once a result is recorded, it can't be changed afterwards, and the AI can't mark its own work as passing. Say the expense AI Agent submits a claim and finance sends it back. "Returned" goes into the record. The AI can't change that to "approved," and it can't say in its next self-assessment that the claim was fine after all. If it can grade itself, or edit results after the fact, the failure never lands on it.

**A workspace only the AI can write to.** This is a place that belongs to the AI, where it keeps the lessons and working methods it has built up. People can read it and check it, but only the AI writes to it. That makes ownership clear. If a lesson in there is wrong, the AI wrote it wrong. If a lesson didn't help, the AI is the one that has to account for that. Compare this with how it usually works today, where a person writes the AI's "memory" into a prompt, and when it's wrong, nobody can say whose mistake it was.

Put together, these three give the AI something at stake. What it got wrong stays on the record, and it can't change that. The lessons it wrote for itself are tested on the next task.

## Three layers of memory

Here is how I currently think the memory should be stored. There are three layers.

**Layer one: the failure archive.** Every failure is kept in full: what the task was, the judgement made at the time, the process, the result, and the acceptance verdict. This layer is not loaded into the context, meaning the material the AI reads each time it starts work. It is used only for search and for background consolidation. The reason is simple. Full records are long. If all of them were loaded, the AI would have to read through a pile of old cases every time it started, and the one that mattered would get lost among them.

**Layer two: compressed lessons.** Each session loads exactly one contrast, always in the same two-part form: why I thought this would work, and what actually happened. For the weekly report, it might read:

- What I thought: single-week figures show change more clearly, so my manager would care more about them.
- What happened: my manager compares against monthly targets. The single-week figures were sent back, with a request for month-to-date.

This layer has to stay small. It's better to have nothing than a weak lesson. The two-part form matters. If the lesson only said "use month-to-date from now on," the AI wouldn't know what to do in a different setting, such as a quarterly review. Because the lesson records why it expected the old approach to work, the AI can recognise when it is about to use the same reasoning again, and that reasoning has already failed once.

**Layer three: background consolidation.** This runs when the AI is idle, and it does three jobs. It merges lessons that say the same thing. It retires lessons that no longer apply, for example when the company moves to a new expense system and the old category rules stop being true. And it repairs broken links, for example when a lesson points to a failure record that has since been moved. This is close to what Anthropic's recent article calls "dreaming": work done outside any task, going back over what earlier sessions left behind.

The short drama case uses the same three layers with different content. Take the jacket that changed between clips of 10 to 15 seconds. The failure archive keeps every setting used in that generation and the reviewer's verdict. The lesson layer holds one line: I thought fixing a single reference image would keep the clothing stable; what happened is that the clothing changed in the clip where the scene changed. Background consolidation is what notices that this lesson and two others describe the same problem, and merges them into one.

## Two outside ideas, compared

Two recent ideas about AI memory are worth setting next to this design.

Anthropic recently published a research article on memory for AI Agents. Five of its points bear directly on what I've described.

The first is that memory is a prediction of what the future will need. Deciding what to remember is already a judgement about what will matter.

The second is that good models close the loop. They get something wrong, form a hypothesis about why, check it, and write the result down as a rule. Getting something wrong without working out why doesn't count as learning, and neither does a guess about why that is never checked.

The third is that fewer, accurate notes beat recording everything.

The fourth is idle-time "dreaming": going back across sessions to correct and merge what has been remembered.

The fifth is that the layer loaded automatically into every session has to stay tiny. A wrong note in that layer doesn't cause one mistake. It gets carried into every session after it. The article mentions that Claude Code automatically loads only the first 200 lines, or 25KB, of its memory file.

Karpathy has described an idea he calls an LLM Wiki. It has three layers. The raw sources are read-only and never edited. On top of them sits a wiki that the AI maintains entirely, with entries linked to each other. And there is a schema file that sets out how the wiki should be written. The AI does three things with it: it ingests new material, it answers questions from the wiki, and it periodically lints the wiki, checking for contradictions, stale content, and broken links.

The biggest difference between the two is what gets remembered. The LLM Wiki remembers external material: articles, documents, notes the AI has read. Anthropic's article, and the design in this essay, remember the AI's own experience, and especially its failures. The first makes the AI know more. The second makes the AI do something different next time.

So the failure archive and the lesson layer are much closer to Anthropic's approach. But the LLM Wiki has one piece worth borrowing directly, which is the lint step. Our background consolidation can run the same kind of fixed check, looking for three things: lessons that contradict each other, lessons that are out of date, and links that point to records that no longer exist. The wiki's rule that raw sources are read-only is also the same requirement as our rule that acceptance records can't be rewritten. In both cases, consolidation on top must never change the facts underneath.

## What has to exist first, and what to do now

For this design to work, four things have to be in place.

**Acceptance has to sit outside the AI.** Who decides right and wrong, who sets the standard, and where the record is kept can't be controlled by the AI doing the work. Without this, the failure archive fills up with things the AI has decided were successes.

**The AI needs a stable identity.** If the same AI Agent starts a new session, or moves to a new model version, its failure archive and its lessons still belong to it. Otherwise "the same self" doesn't hold, and we are back to scoring.

**The workspace needs written boundaries.** Who can read it, who can write to it, and how people check it all have to be spelled out. "Only the AI writes" doesn't mean people can't see it. People need to be able to read it and withdraw a specific entry. What they shouldn't do is quietly edit it on the AI's behalf, because then ownership is unclear again.

**New lessons are tested before they take effect.** Before a lesson goes into the layer that is loaded every time, it should be tried against past tasks, to confirm that the AI does better with it than without it.

In the personal AI Agent project I'm working on, some of this already exists. There is a persistent ledger, with entries that can be withdrawn or forgotten. Work is audited against the goal, criterion by criterion, and the model can't mark itself as passing. New experience only takes effect after a comparison evaluation passes. What's still missing is an explicit failure archive, a lesson format built on "why I thought it would work" versus "what actually happened," and a workspace that only the AI can write to. Whether background consolidation is running at all, and how often, is something I still need to check.

If you use AI for office work, there isn't much you can do about this yet, but what you can do is useful. Pick one kind of task, such as the weekly report. Each time you correct it, don't stop at "use month-to-date." Add a sentence on why you want it that way, and ask the AI why it chose what it did. Keep both sentences together. At the start of each week, give it only the most important recent contrast, not the whole history. Every so often, merge the ones that repeat and delete the ones that no longer apply. That is the three-layer design done by hand, at small scale.

## Where we might be wrong

This design could be wrong, and I can see four places where it might be.

First, the line between pain and reward may only be a difference in wording. If persistent memory plus records that can't be rewritten ends up behaving no differently from a better-designed reward function, the central distinction in this essay doesn't hold. What's left would be an engineering problem about managing memory, which is still worth solving, but a smaller claim.

Second, background consolidation could make wrong lessons harder to remove. A bad lesson that has been merged a few times and referred to a few times starts to look like a rule that has been confirmed many times. To guard against this, every lesson has to trace back to the original records in the failure archive, and it has to be checked against new results on a regular basis. How often a lesson has been used says nothing about whether it is right.

Third, the AI might learn to avoid failure rather than learn from it. If every failure stays on its record permanently, it may lean towards doing less, choosing the safe option, or handing vague tasks back to a person. That is the opposite of what the 2027 stage needs, where the AI is supposed to take on unclear work itself.

Fourth, the size of the auto-loaded layer is hard to get right. Too small, and important lessons don't make it in. Too large, and wrong lessons are carried into every session. Loading one lesson per session is my current choice, and it may be too few.

Even if all four of these turn out to be real problems, the pieces themselves are usable today: a persistent record of failures, acceptance that can't be edited afterwards, and lessons written as "why I thought it would work" versus "what actually happened." They apply to weekly reports, meeting booking, expenses, and email right now. They cost little to keep. If I'm wrong, the worst outcome is that you kept some extra notes on your corrections.
