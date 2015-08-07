# specs-laws

The Three (or more) Laws of Schematics

Note: while this claims to be a set of guidelines surrounding the drafting of technical specifications, it can also be interpreted as a set of guidelines around any sort of design, and, in a broader interpretation, as [an abstract philosophy of life][ZAMM] (with shout-outs to the driving philosophies of others). All opinions expressed are my own, except the Robustness Principle was Jon Postel's. Also this document cribs heavily from [The Design of Everyday Things][] and [The Pragmatic Programmer][]. Subject to interpretation. Follow at your own risk or benefit. [Party Hard][].

[ZAMM]: http://amzn.to/1GS6rXX
[The Design of Everyday Things]: http://amzn.to/1dAbip2
[The Pragmatic Programmer]: http://amzn.to/1JABxdu
[Party Hard]: https://www.youtube.com/watch?v=WccfbPQNMbg

## The Pragmatic Prime Directive: Serve the Use Cases

The ultimate point of any spec is [Taking Care of Business][]. Your spec needs to make **real people**'s *real lives* **really easier**. Nobody wants a spec that tells them how to do something they already do, but more painfully and less effectively.

Know your use cases, know your scope, know your prior art. Realize that [you're not the first one to notice these problems][SPACEWAR] (and that there's [still lots of yet-untapped potential for better solutions][cluetrain]).

[Taking Care of Business]: http://www.elvisblog.net/2012/03/31/elvis-captain-marvel-jr-and-the-tcb-lightning-bolt/
[SPACEWAR]: http://stuartpb.github.io/spacewar-article/spacewar.html
[cluetrain]: http://www.cluetrain.com/

### Know What "Unopinionated" Means

At some level, *anything* is an opinion. Know what opinions and beliefs your spec targets follow (hint: they're part of the use cases), and don't implement things that assume *more* than these beliefs. [Recognize that you are asserting a worldview][worldviews], and [when choosing chaos over order, understand how the chaos spawned that order][Dark Leviathan].

[worldviews]: http://www.shirky.com/writings/herecomeseverybody/semantic_syllogism.html#worldviews_differ_for_good_reasons
[Dark Leviathan]: http://aeon.co/magazine/technology/on-the-high-seas-of-the-hidden-internet/

### Know When To Say "Don't Do That"

There's an old [vaudeville][] bit, popularized by the duo [Smith & Dale][], where a patient (played by Smith) goes to see a doctor (Dr. Kronkheit, played by Dale), which goes:

- **PATIENT**: Doctor, it hurts when I do this *(raises arm)*.
- **DOCTOR**: Well, don't do that.

[vaudeville]: https://en.wikipedia.org/wiki/Vaudeville
[Smith & Dale]: https://en.wikipedia.org/wiki/Smith_%26_Dale

However, there's a similar, less-known follow-up to that bit, after the doctor has been chastised for his attitude and sees his next patient, which goes like this:

- **PATIENT**: Doctor, it hurts when I do this *(stabs self in the neck with a fork)*.
- **DOCTOR**: Interesting, we'll have to saw it off.

You can't offload all of your problems onto the user, but you can't let the potential for any user to have any self-inflicted problem stop you from giving them the tools to do so. And, of course, not all problems are self-inflicted. (When a problem can *be* inflicted *onto others*, that's what's known as a "security hole", and should be evaluated as such.)

You need to understand *why* the user is motivated to do this painful behavior. Sometimes, it's just lifting their arm - they need to reach higher heights. Maybe they're stabbing their neck with a fork because that's how they lanced a boil before and they've come to think that's normally how they can relieve their pain. Sometimes, they just *aren't* - you'll find that the hypothetical user hurt by this behavior doesn't exist. Whatever it is, the solution here starts with **asking them**. Trying to solve it with a brute-force attack on possibilities is intractible, and the answer is almost always (*by definition*) going to be outside your search space.

And, of course, sometimes human motivations are too murky and complex to truly comprehend, and diagnosing it directly is likely to introduce more problems, as illustrated by *another* exchange, from the same vaudeville act:

- **PATIENT**: Doctor, my neck hurts.
- **DOCTOR**: Well, sit down and open your neck.

Such is life. When you have gotten to that point, and **only** when you have gotten to that point, should you say "don't do that", and just live with the fact that you made that call. (Be open to others if they later come to you to explain their motivation further, and consider what might otherwise satisfy/address those motivations.)

### Be Liberal In What You Accept

Implementers will make mistakes, implementers will need to break compliance. You can't just say "it's invalid, throw everything away" when things don't work exactly the way you want (unless you're a serialization format, in which case that signals data corruption). Be Pragmatic. State what should happen when the spec has to degrade. Explain your reasoning. Show your work, and *do* let other students copy off your paper (as long as they don't put your name on it).

### Work With The Implementation

A spec without an implementation is just a pipe dream - just saying "everybody will agree on everything forever" doesn't fix anything. Start working on an implementation, even just a polyfill, as early as possible (making sure to keep that implementation in sync with your proposed spec - a divergent implementation at this stage is going to make things so much worse).

## Correctness is Security, Correctness is Speed

Shortcuts are for tools - literally. Don't make it easier to specify something by using a shared, simpler syntax that overrides another meaning that is less likely but still technically possible (especially if it would make that less-likely meaning impossible). In specs, as in implementation, [the key to performance is elegance, not battalions of special cases][Conversations: Jon Bentley].

[Conversations: Jon Bentley]: http://www.drdobbs.com/architecture-and-design/conversations-jon-bentley/207000707

Correctness must be enforced unless it woud not be pragmatic to do so.

Importantly, you must not let the use cases drive you *away* from correctness, when correctness would solve the use cases *just as easily* (or nearly so, possibly with a bit more work by tools) - using "we don't strictly need it" as a "justification" for incorrectness is a slippery trap we let ourselves fall into when we want an excuse to avoid doing more work, as a way of offloading our problems onto others (either other developers, or other users).

## Explicit Is Better Than Implicit, Though The Implicit Case Must Make Sense

Making implicit cases insecure is a mistake, unless it would be more insecure to force security.

## Footer

Questions? Comments? Requests for clarification?
[Raise an issue on this repo][issues].

[issues]: https://github.com/stuartpb/specs-laws/issues
