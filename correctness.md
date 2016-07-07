# Correctness is Security, Correctness is Speed

Shortcuts are for tools - literally. Don't make it easier to specify something by using a shared, simpler syntax that overrides another meaning that is less likely but still technically possible (especially if it would make that less-likely meaning impossible). In specs, as in implementation, [the key to performance is elegance, not battalions of special cases][Conversations: Jon Bentley].

[Conversations: Jon Bentley]: http://www.drdobbs.com/architecture-and-design/conversations-jon-bentley/207000707

Correctness must be enforced unless it woud not be pragmatic to do so.

Importantly, you must not let the use cases drive you *away* from correctness, when correctness would solve the use cases *just as easily* (or nearly so, possibly with a bit more work by tools) - using "we don't strictly need it" as a "justification" for incorrectness is a slippery trap we let ourselves fall into when we want an excuse to avoid doing more work, as a way of offloading our problems onto others (either other developers, or other users).

The same goes for code that trades "correctness" for "performance". Unless you are truly maturely optimizing - wise, learned man optimizing - most likely there's a pathological case that will break the "incorrect" but "optimized" version several times worse than the losses in the "correct" approach would have ever amounted to.
