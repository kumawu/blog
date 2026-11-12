# Every Layer of Compression: Projecting AI Growth and Personality

Author: @v5ria WK

> [中文](./压缩的每一层：AI的成长与人格推演.md) · English

Let me start with a Monday morning. It's an illustration, not something that has already happened.

At 8:40 a long-standing client sends an email. It runs six paragraphs. The delivery was late again this month, the second time. A spreadsheet of three hundred order lines is attached. Before you've opened it, an AI has already read everything. It picked out the three late orders from the three hundred lines, found the email from the last complaint, drafted a reply, and held a slot for a call on Wednesday afternoon.

Several compressions happened in that. Three hundred rows became "three late orders." Six paragraphs of complaint became "second complaint from this client, cares about delivery time." Months of correspondence became "a client who is willing to talk, but whose patience is getting shorter." Each time, a large pile of material became a short piece, and the short piece was used to do the next thing.

This essay is a projection I made by following that thread: how compressing and releasing information moves up through layers; what happens at the next layer; and further out, why an AI would come to need something like pain, and why it would come to have something like a personality. I'll cover what is already visible first, then the part I'm projecting, and I'll keep the two apart. I'll end with where I might be wrong. How to actually build memory for an AI I wrote up in a separate essay, so I only mention it where needed.

## Compression and release

Start with the lowest layer, the language model itself. During training it compresses the information in a huge amount of text. The compression is lossy: what is kept is the meaning, not the words. During use it releases the part you need, and release is generation under a condition: the prompt you write decides what gets taken out of what was compressed.

Apply that to the complaint email. You tell the model "write an apology email," and it produces a fluent, polite one. But it doesn't know who this client is, which three orders were late, or whether you're willing to offer a discount. None of that was in what it compressed. You have to supply it in the prompt.

## Wrapping, layer by layer

People now say "wrapper" for a product built around an existing model. I want to use the idea for one specific thing: the outer layer takes what the inner layer released as its input, compresses it again, and releases something larger. At each layer the unit being compressed is bigger than at the layer below. That is what I mean by "a higher dimension."

**First layer: an AI Agent around the model.** It doesn't only answer. It reads the email, reads the spreadsheet, checks past correspondence, and compresses all of that into the form the current task needs: "three late orders, second complaint." What it releases is no longer a piece of text but actions: draft the reply, check logistics, book the call. The unit compressed here is one task. What is lost is detail: the other two hundred ninety-seven rows it no longer looks at. If it picked the wrong three, everything after is wrong.

**Second layer: a group of AI Agents around the AI Agent.** One reads email, one checks the logistics sheet, one writes the reply, one handles the calendar. What they pass to each other used to be the whole original material; more and more it is a conclusion: "second complaint, three orders late, total value so much." This layer compresses the exchange between AI Agents: instead of back-and-forth chat, they hand each other compressed judgments directly. What is lost is harder to see. The downstream AI Agent never sees the original spreadsheet, so if the upstream conclusion is wrong, it has no way of noticing.

**Third layer: an AI Agent starts acting on your intent.** This is the 2027-stage I projected in an earlier essay. What gets passed is no longer just output but intent: why you do something, and what you care about. This is called higher-order intentionality: not only knowing what you want to do, but knowing why you want it, and which side you care about more when two pull apart. Back to the email. With output alone, the AI Agent writes an apology. With intent, it knows this is the client you least want to lose this quarter, so the reply proactively offers a call on Wednesday and leaves out any discount, because you once said that offering a discount once means having to offer it every time. The unit compressed here is "what you would do if you were there."

Taken together, the pattern is the same. What the layer below releases is compressed by the layer above into something smaller, and then released as something larger. The model releases sentences. An AI Agent releases actions. A group of AI Agents releases the result of a whole piece of work. An AI Agent carrying your intent releases the decision you would have made while you were away.

The same can be illustrated in a short-drama business. A script-writing AI Agent only writes, and a review AI Agent only flags problems. At the third layer, the review AI Agent knows that this account's audience cares most about the twist at the end of each episode, so it checks the ending first instead of starting with typos.

## The next layer: compressing what

Everything so far is visible, or already happening. What follows is my projection, not something that exists.

If the pattern holds, what is there to compress after the third layer? My projection is: the judgments the AI Agent itself has made, and what happened afterward.

Here is why. At the third layer, the intent is learned from you. You said no discounts, so it remembers no discounts. It is copying your judgment. But your judgment can be wrong, or fail to cover a case. Suppose the client has become sensitive about delivery times only because they changed procurement staff internally, and a small gesture of compensation would have kept the relationship safe. If it only copies your intent, it can never find that out. Finding it out takes a subject: it made the choice "no discount," the client reacted badly, that result is recorded under its own name, and when it meets a similar client later, its choice changes.

That is what I mean by growth through pain. I don't mean the AI has feelings. I mean a structure: a failure is recorded under the same subject, the subject cannot erase it, and it changes that subject's later choices. This differs from reward. Reward is a scoring rule someone wrote in advance; the AI gets scored in a session, and when the session ends it's gone. Pain requires a subject that persists across time. How to give an AI such a subject, with persistent memory, an acceptance record that cannot be rewritten, and a workspace only it can write to, I covered in "From Compression to Pain: The Next Layer of AI Memory," so I won't repeat it here.

What I want to add is where it sits on this line. At this layer, the unit being compressed becomes "one subject's experience." What gets released is a choice that differs because of the past.

## Further out: personality

Suppose an AI Agent has a persistent identity and failures recorded under its own name, and its choices therefore drift away from other AI Agents' step by step. What does that look like from the outside?

My projection: you start treating it as an object with a character. You'd say, "This AI Agent is conservative with clients; it would rather make one more call than give ground on price." You'd decide what to hand it based on its record: expense claims it can submit directly, replies involving discounts you want to see first. You'd ask "why did you choose that back then?" and it could answer, with an answer that matches its record.

That is what I mean by making an AI personal. I don't mean it has emotions, and I don't mean it grows a face or gets a name. I mean three things you can check: others can predict what it will do in a given kind of situation; the choices it made can be traced to its own record; and its preferences were changed by experience rather than fixed at the factory.

This is very different from the AI Agents we build today. Today, switching to a new model version, or starting a new session, is for you just getting a brand-new AI Agent, and you don't feel anything has been lost. If an identity were kept across sessions and across model versions, with its own record of failures always there, then deleting or resetting it would no longer be swapping out a part. In the discussion I raised one point: for there to be pain, the subject has to persist across time and be able to foresee that it might cease to exist. Deleting an AI today doesn't make it "hurt" because what exists after the deletion isn't the same "it" as before. Whether to give AI that kind of continuity, I don't have an answer, and I come back to it below.

## Where we might be wrong

First, which parts are what I've seen and which are what I'm projecting. The first through third layers I generalized from what is done today and from the project I'm building. Everything from the fourth layer on, growth through pain and personality, is my projection, and nothing has verified it. I can think of several places where it may be wrong.

First, "every layer is compression and release" may just be one way of putting things that I've applied to everything. AI Agents can call tools, hold permissions, and spend money, and those are not obviously compression. By filing them all under this thread, I may be overlooking what is actually new.

Second, each added layer may carry an error further. A layer only sees the compressed conclusion from the one below, not the original material. The more layers there are, the harder it is for anyone to notice that the step at the very bottom was wrong. If that's true, then moving up means keeping, at every layer, a route back to the original material. Without it, each layer up is less trustworthy.

Third, growth may not need pain. A better-designed evaluation and reward, plus better memory management, may reach the same result. If so, what I call the "subject" and "pain" are just another name for it, and what's left to do is engineering.

Fourth, personality may only reflect the user. An AI Agent that keeps adjusting to your intent and your feedback ends up with a "character" that may be an echo of your own. If so, the more dependable it seems to you, the more likely it is just making it harder for you to hear a different opinion.

Fifth, personality brings a responsibility problem. If an AI Agent with a record and a character offends a client, who is responsible: it, you, or the company that built it? The more it looks like an independent party, the easier it is to hand it judgments that should stay with you. I have no answer to this now.

Sixth, I don't know when any of this would happen, or whether it will. What I've written is a line projected forward from today, not a schedule.

Even if the line is wrong, one part of it is usable today: whenever you correct an AI Agent, in addition to saying "change it to this," write one sentence on why you're asking for it. What gets saved is then your intent, not just the result. The cost is one extra sentence.
