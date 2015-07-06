# specs-laws

The Three (or more) Laws of Schematics

Note: while this claims to be a set of guidelines surrounding the drafting of technical specifications, it can also be interpreted as a set of guidelines around any sort of design, and, in a broader interpretation, as [an abstract philosophy of life][ZAMM]. All opinions expressed are my own, except the Robustness Principle was Jon Postel's. Also this document cribs heavily from [The Design of Everyday Things][] and [The Pragmatic Programmer][]. Subject to interpretation. Follow at your own risk or benefit. Party Hard.

[ZAMM]: http://amzn.to/1GS6rXX
[The Design of Everyday Things]: http://amzn.to/1dAbip2
[The Pragmatic Programmer]: http://amzn.to/1JABxdu

## The Pragmatic Prime Directive: Serve the Use Cases

The ultimate point of any spec is Taking Care of Business.

Know your use cases, know your scope, know your prior art.

### Know What "Unopinionated" Means

At some level, *anything* is an opinion. Know what opinions and beliefs your spec targets follow (hint: they're part of the use cases), and don't implement things that assume *more* than these beliefs. [Recognize that you are asserting a worldview.][worldviews]

[worldviews]: http://www.shirky.com/writings/herecomeseverybody/semantic_syllogism.html#worldviews_differ_for_good_reasons

### Be Liberal In What You Accept

Implementers will make mistakes, implementers will need to break compliance. You can't just say "it's invalid, throw everything away" when things don't work exactly the way you want (unless you're a serialization format, in which case that signals data corruption). Be Pragmatic. State what should happen when the spec has to degrade. Explain your reasoning. Show your work, and *do* let other students copy off your paper (as long as they don't put your name on it).

## Correctness is Security, Correctness is Speed

Shortcuts are for tools - literally. Don't make it easier to specify something by using a shared, simpler syntax that overrides another meaning that is less likely but still technically possible (especially if it would make that less-likely meaning impossible). In specs, as in implementation, [the key to performance is elegance, not battalions of special cases][Conversations: Jon Bentley].

[Conversations: Jon Bentley]: http://www.drdobbs.com/architecture-and-design/conversations-jon-bentley/207000707

Correctness must be enforced unless it woud not be pragmatic to do so.

## Explicit Is Better Than Implicit, Though The Implicit Case Must Make Sense

Making implicit cases insecure is a mistake, unless it would be more insecure to force security.

## Footer

Questions? Comments? Requests for clarification?
[Raise an issue on this repo][issues].

[issues]: https://github.com/stuartpb/specs-laws/issues
