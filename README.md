# specs-laws

The Three (or more) Laws of Schematics

## The Pragmatic Prime Directive: Serve the Use Cases

The ultimate point of any spec is Taking Care of Business.

Know your use cases, know your scope, know your prior art.

### Know What "Unopinionated" Means

At some level, *anything* is an opinion. Know what opinions and beliefs your spec targets follow (hint: they're part of the use cases), and don't implement things that assume *more* than these beliefs.

### Be Liberal In What You Accept

Implementers will make mistakes, implementers will need to break compliance. You can't just say "it's invalid, throw everything away" when things don't work exactly the way you want (unless you're a serialization format, in which case that signals data corruption). Be Pragmatic. State what should happen when the spec has to degrade. Explain your reasoning. Show your work, and *do* let other students copy off your paper (as long as they don't put your name on it).

## Correctness is Security, Correctness is Speed

Shortcuts are for tools - literally. Don't make it easier to specify something by using a shared, simpler syntax that overrides another meaning that is less likely but still technically possible (especially if it would make that less-likely meaning impossible).

Correctness must be enforced unless it woud not be pragmatic to do so.

## Explicit Is Better Than Implicit, Though The Implicit Case Must Make Sense

Making implicit cases insecure is a mistake, unless it would be more insecure to force security.

## Footer

Questions? Comments? Requests for clarification?
[Raise an issue on this repo][issues].

[issues]: https://github.com/stuartpb/specs-laws/issues
