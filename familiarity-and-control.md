# Familiarity and control

I was idly scrolling through the comments of a YouTube video taken from a conference presentation given by the [indie game developer Jonathan Blow](https://www.youtube.com/watch?v=uZgbKrDEzAs), when I saw this comment.

> Interestingly, the presentation software he uses is written in Jai and he's done it because "PowerPoint wasn't addressing his needs".

Jai is the programming language that Blow is working on, and Jai was also the subject of the talk. The replies to that comment quickly became a flame war after this response by
a guy named Chris.

> Worst case of NIH I’ve ever seen. This is quite unfortunate, as we need both languages and paradigm shifts for game/simulation programming, however he thoroughly misunderstands (or deliberately misrepresents) several basic computer science principles that are still needed and used. He may be bright, but there are plenty of bright people out there that can skillfully deduce when to apply a paradigm and when not to. This binary thinking he employs (not just on computer science) is getting in his way.

So I had to look up NIH on Wikipedia...

In computer programming, "NIH syndrome" refers to the erroneous belief that in-house developments are inherently better suited, more secure, more controlled,
quicker to develop, and incur lower overall cost (including maintenance cost) than using existing implementations.

Whenever I hear discussions about the wrongness or rightness of "reinventing the wheel" with a particular piece of software or an ecosystem of software, I think there are a
couple of "Elephants In The Room" that both sides are ignoring in the debate.

## The Familiarity Elephant

Those arguing for the use of pre-existing external tools massively underestimate how difficult it can be to understand vast and monolithic software ecosystems that you had no hand in creating yourself.

Obtuse and impenetrable documentation is the norm, rather than the exeption, for both proprietary and open source tools.

The question "why don't you write better docs then?" ignores the fact that in order to write good docs, you first need a good understanding of the system. Or at least a portion of it.

Egg, meet chicken. Chicken, meet egg.

Want to become intimately familiar with the tools that you are using?

Write those tools yourself.

Want to become the world's leading expert on software X?

Write software X yourself.

Sadly, the people who do this work, generally rationalise not using existing tools in terms of those tools being hopelessly inadequate or downright bad.

That might not be an ego-driven rationalisation in all cases.

But in most cases, it probably is.

## The Control Elephant

On the 6th September 2018, GitHub proudly announced that they had removed all the JQuery code from their website.

Sure, JQuery was sort of legacy at the time. So what popular JavaScript framework or library did they replace it with?

React?

Angular?

Vue?

Svelte?

Nope!

They went with "none of the above".

So its pretty safe to assume that GitHub has their own specific in-house tools for their own specific use cases.

This is not so astounding when you realise that React was created by Facebook for their use case, Angular was created by Google for their use case, Vue was created for Evan You's use case, Svelte was created for Rich Harris' use case...

...are you noticing a pattern here?

## The Double Standard

When big companies "duplicate the effort" involved in making their own tools for tasks that are very similar to those already accomplished by other firms, no one seems to
complain about that.

The commercial sense of "driving your own bus" is immediately obvious. 

But as the size of the operation gets smaller, a scornful attitude creeps in.

Who the hell do you think you are, by making your own tools?

Oh the audacity! The folly! The hubris!

My attitude is completely different.

When I see a small commercial operator or an open source contributor making their own tools, I know that there is a good reason for it.

That "extra effort" is likely to bear fruit in some form.
