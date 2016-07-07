# Know When To Say "Don't Do That"

There's an old [vaudeville][] bit, popularized by the duo [Smith & Dale][], where a patient goes to see a doctor and has the exchange:

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
