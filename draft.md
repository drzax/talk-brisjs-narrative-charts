# [XKCD](https://xkcd.com/657/large/)
Ever since I first saw them the XKCD movie narrative charts have fascinated me.

I've been interested in different approaches to telling complex stories on the web for quite a long time.

One approach you can take to telling complex narratives is to simplify the complexity in a way which 'distills' the essence of a story into something which is more digestible or exposes a new angle.

The XKCD movie narrative charts did this in a novel, and I think, very effective way.

On one hand, they provide the ability to see the 'shape' of the story in one easily digested image. While at the same time they allow you to drill deeper. Dig into the structure of the story in more detail.

# [ICAC v1](http://www.abc.net.au/news/2014-04-29/icac-relationships-graph/5391038)
So while I had these charts bobbing around in the back of my head, we began looking to do a story about the ongoing saga about political corruption in NSW being revealed week-by-week, month-by-month by the Independent Commission Against Corruption, or ICAC.

One of the problems with this story from a news-telling perspective is that it was so vast. There were many characters and many events which all combined to create an incredibly complex story.

# [ICAC v2](http://www.abc.net.au/news/2014-08-21/untangling-the-web-how-the-icac-scandal-unfolded/5686346)
During a planning session, it came to me that this would be the perfect opportunity to re-invent the movie narrative charts for a different purpose.

But rather than hand drawing them, we wanted the ability to generate them from different data sets--or, more accurately, the same dataset, with different filters in place. So the challenge was set to re-create the XKCD charts for the web.

# [Prior art](https://csclub.uwaterloo.ca/~n2iskand/?page_id=13)
So, like all good developers, rather than attempt to build it myself, I had a good look around to find someone else's implementation.

And I found one! It's even pretty good--maybe better than what I ended up with, however:
- It's not open source, and
- A quick Chrome Dev Tools inspection revealed that the data structures weren't quite what I wanted.

# [Star Wars: XKCD vs. Me](http://www.abc.net.au/news/2015-12-16/star-wars-every-scene/7013826)
So I decided to roll my own, and eventually the whole thing came full circle and late last year I got to roll out a Star Wars version, just like the original XKCD version (only not quite as good--but interactive!)

# [The challenge](https://cloudup.com/cuGKTIXORC8)
So what's the challenge here? Basically, it's taking something which is incredibly complex and chaotic, adding the further dimension of time, and producing a visual representation which minimises as much as possible the chaos.

More specific to a programming context, it's an optimisation problem at heart.

# [Star Wars](http://localhost:8000/)
In this case that means optimising the vertical order of character lines and the y-axis position of each scene to minimise the criss-crossing of lines.

# [Specific goal](https://github.com/abcnews/d3-layout-narrative)
Specifically, my goal is to be able to give the layout engine a list of characters and scenes in which those characters are involved and have it give me back everything I need to draw the chart to screen.

# [Dig in](https://abcnews.github.io/d3-layout-narrative/#section-39)
So, lets dig in a little.

This is the broad strokes of the layout algorithm. And this is also the part of the talk which starts getting a little source-codey.

I'm going to run through each of these, some very quickly because they're super boring, but others I'll dig in a little and explain what and why.

Fair warning, this is going to get quite complex. So complex in fact, that there's a good chance I'll get confused while explaining it.

If you have any questions--or even better, suggestions for how to do it better--please pipe up, or at least come and see me at the end.

# [jLouvian](file:///Users/elverys7d/Projects/jLouvain/example/example.html)
One core technique that this layout algorithm relies on is community detection.

Just incase you're not familiar with the idea, it's basically a method of taking a whole bunch of nodes (or in this case characters), looking at the connections between them and the strength of those connections (in this case, the scenes they share) and finding smaller groups with in the whole.

Back to the [algorithm](https://abcnews.github.io/d3-layout-narrative/#section-64).

# [Another attempt](https://www.wikiwand.com/en/Stochastic_optimization)
If I had to do it again, I'd be more trial and error about it.

I'd probably create some kind of optimisation cost calculation function which I could use to calculate a good layout based on a bunch of simulations.

A good d3 example of this is [d3 labeler](https://github.com/tinker10/D3-Labeler)

# [Me](https://twitter.com/drzax)
