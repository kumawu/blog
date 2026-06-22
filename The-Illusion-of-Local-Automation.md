# The Illusion of Local Automation — From a Cup of Milk Tea to How Companies Use AI

Author: @v5ria WK

The other day I waited a long time for a cup of milk tea.

It was a shop of maybe 200 square meters. At its busiest it had six staff; that day there weren't many customers, and the crew thinned out until only one person was left. Few people were ordering, so this one person had to make each cup from start to finish — which is why I waited so long.

While waiting, I looked around and took a photo.

![One lone staff member behind the milk tea counter][cover]

> Photo: only one staff member left behind the counter, holding the whole line together by himself — from shaking the tea to dispensing measured pours to sealing the cup.

And I noticed something interesting: **almost every single step on this counter was already automated.**

A digital auto-sealing machine that closes a cup at one press; a thermostatic dosing water dispenser, with temperature and volume controlled to the digit; automatic measured pours, automatic tea shaking… Next to every machine was a spec sheet, each one announcing, in its own way, "this step of mine is high-tech."

And yet the cup in my hand still took forever.

## Every step is advanced, the whole cup is still slow

So where's the problem?

Not in any single machine. The sealer seals in a flash, the dispenser pours in a second; step by step, each one is faster and more precise than a human hand.

The problem is **in between those steps.**

Each machine only handles its own segment of "processing": the sealer only seals, the dispenser only dispenses. But scooping the tea base into the cup, carrying the cup under the sealer, pressing the button, pulling out a straw, sticking on the label, calling the number — all these **connecting actions** still rely on that one staff member's two hands to string together.

So when the crew dropped from six to one, every machine was still just as fast, but the time to produce a whole cup multiplied. Because what determines how long a cup takes was never how fast any one machine is — it's **how busy the person stringing all the steps together is.**

This is the classic **local-optimum trap**: you've stuffed the most advanced equipment into every workstation, every segment got faster, but the tempo of the whole line is set by the one connecting step that wasn't automated. How much water a bucket holds depends on its shortest stave; how fast this counter serves depends on those hands still shuttling back and forth between two machines.

Gains in single-point efficiency never became gains in overall efficiency. That middle layer — the "human integration layer" — ate all the gains back up.

## This is exactly how most companies use AI today

Standing there waiting for my tea, it suddenly struck me that this scene is almost identical to how most companies view and use AI right now.

Over the past year or two, nearly every company has been "adopting AI." How, exactly? Usually like this:

- Marketing uses an AI to write copy and generate images;
- Customer service plugs in an AI chatbot;
- Engineering uses AI to autocomplete code;
- Operations uses AI to write weekly reports and summaries;
- Legal uses AI to review contracts.

Every step gets a powerful model bolted on, and every team can write in its report, "we've introduced AI, efficiency up X%." It sounds like the whole company has been armed with high tech.

But if you step back and look at the entire business pipeline, you'll find it eerily resembles that milk tea shop:

**Every workstation has been fitted with an AI, but between the workstations, it's still humans doing the hauling.**

Marketing's AI generates a draft of copy, a human copies it, pastes it into the chat app, @-mentions the designer; the designer's AI produces an image, a human downloads it, renames it, uploads it to another system; engineering's AI writes the code, a human manually runs the tests, opens the PR, waits for approval; the question the customer-service AI can't answer gets handed off to a human, who then digs through three other backends.

Every segment of "processing" has been sped up by AI, but all the **routing, connecting, judging, handing-off** still presses down on humans. The human is still that staff member shuttling between machines, pressing buttons, calling out numbers.

The result is the very thing we saw in that milk tea shop: **it looks like high tech has been introduced at every step, but overall efficiency hasn't actually improved.** Or worse — because now humans not only do the connecting work they used to, they also have to learn how to deal with each AI, how to digest its output, how to judge whether it's right.

## Why it gets stuck here

I wrote earlier in [*I Am the Biggest Bottleneck in the AI System*](./我是AI系统里最大的瓶颈.md) about a judgment: as AI gets stronger, the human slowly becomes the bottleneck itself. This milk tea scene is a specimen of that judgment in the physical world.

The root of the jam is that we've **only automated the "processing," not the "routing."**

Every machine, every AI, solves one finely sliced, isolated task: seal one cup, write one paragraph, complete one line of code. These tasks share a trait — they are all **fed in by someone (a human) and taken away by someone.** The machine doesn't know what the previous step was, nor is it responsible for where the next step goes. It's just a passive part on the line that a human has to wire up.

So the human is forced into being the **integration layer**:

- the human moves data from one system to another;
- the human judges whether this step's output can enter the next step;
- the human rolls back, corrects, and redoes when something goes wrong.

And what actually consumes the time is precisely these hand-off actions, not the processing itself. Of a cup of tea's time, far more is spent carrying it around than on the one second of sealing. Of a business process's time, far more is spent "waiting for a human to carry the previous step's result to the next" than on the few dozen seconds of model inference.

**We keep optimizing the steps that were never slow, while leaving the slowest connecting step to humans.**

## The way out isn't more machines, it's redesigning the process

If that milk tea shop wanted to truly get faster, the answer obviously isn't to buy ten more advanced sealing machines. No matter how fast the sealer, it can't eliminate the act of "a human carrying the cup over."

The real fix is to **redesign the line itself**: let the tea base, the pour, the seal, and the label flow automatically along one continuous track, with the human only loading at the very start and picking up at the very end. In other words, what needs automating isn't any one workstation, but **the conveyor belt between the workstations.**

It's the same with companies using AI. The thing I say over and over in [*Stop Designing AI-Era Workflows for Humans — Seven New Principles*](./Stop-Designing-AI-Era-Workflows-for-Humans.md) is exactly this: **don't stuff AI into a human-designed legacy process one workstation at a time.** Do that, and you've merely swapped pricier parts onto a manual line — the conveyor belt is still those hands.

The right direction is the reverse:

**1. Automate the hand-offs, not just the processing.**
Real efficiency comes from connecting the conveyor belt between steps — letting the previous AI's output become the next AI's input directly, without landing in a human's hands in between. An Agent finishes writing code, then runs the tests itself, opens the PR itself, iterates on the CI results itself, instead of stopping at every step to wait for a human to do one round of hauling.

**2. Let AI run end-to-end through a process, instead of occupying one workstation as a dot.**
To judge whether a company has truly adopted AI, or merely bought a pile of "high-tech sealing machines," look at one thing: **is there a complete business process that can run from start to finish on its own, with the human only giving direction at the start and accepting the result at the end?** If the answer is no, then no matter how many models you've plugged in, you're still stuck in that milk tea scene.

**3. Free the human from the "integration layer" and move them to the "design layer."**
A human's value should not be hauling data between systems, pressing buttons, doing the wiring. Those are exactly what should be handed to machines. The human should do what machines still can't: define which processes are worth doing, design the acceptance criteria, pull the whole line back when it drifts. From the person laying bricks to the one drawing the blueprint and running the line.

## A simple self-check

If you want to know which layer your company (or your own work) is actually at right now, ask one question:

> **If you pulled all the staff down to just one person, could your business still run at roughly the same speed?**

That milk tea shop's answer is "no" — down to one person, the serving speed instantly multiplied in time. Because its automation is local; the tempo of the whole line is still set by the number of people.

If a process that has "introduced AI" still has throughput strongly correlated with "how many people are hauling in the middle," then it's no different in essence from that milk tea shop: **it bought a lot of high tech, but it didn't change the fact that efficiency is decided by people.**

A process that has truly been AI-ified should be the opposite: adding people won't make it much faster, and removing people won't make it much slower, because the people were never on the conveyor belt to begin with. The people are at the two ends of the belt — loading and picking up, defining goals and accepting results.

## Ending

That cup of tea did eventually get made, and I got it. But the dozen-odd minutes I spent standing there waiting might be the clearest stretch of thinking about AI I've had all year.

It's easy to be fooled by "every step is advanced" into believing that advanced parts will naturally assemble into an advanced system. But a cup of milk tea reminds me: **what determines the overall speed was never the fastest step, but the connection that hasn't been automated and can only be strung together by a human.**

What most companies are doing now is bolting ever pricier machines onto a manual line. The real opportunity is to build the conveyor belt itself — and then take the human down from that spot between two machines where they've been working as a porter.

[cover]: https://github.com/user-attachments/assets/5da8c8f8-53ff-44df-ab67-34f77ed961f8
