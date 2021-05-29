# awesome-tech-content

This is my personally curated list of books, blog posts, essays, papers, articles,
keynotes, talks and any kind of tech-related content that I find awesome.

Since this is a personal list of things that I find interesting I'm not really actively
looking for contributions but, I don't know, if you have found something awesome on the
internet and want to share with me and I like it, yeah, I might add it here I guess 😬

---

## Software Engineering

- [Are We Really
  Engineers?](https://www.hillelwayne.com/post/crossover-project/are-we-really-engineers/)
  · _Hillel Wayne_ · Essay.

    Part 1 of Hillel's "Crossover Project". A thoughtful look into the old-age question
    of "is Software Engineering _really_ Engineering" (which is unfortunately often
    expressed in bad faith with the intention to to gatekeep). Followed by Part 2 ["We
    Are Not
    Special"](https://www.hillelwayne.com/post/crossover-project/we-are-not-special/)
    and Part 3 ["What Engineering Can Teach (and Learn from)
    Us"](https://www.hillelwayne.com/post/crossover-project/what-we-can-learn/).

- [Serverless Computing: One Step Forward, Two Steps
  Back](https://arxiv.org/pdf/1812.03651.pdf) · _Hellerstein et al_ · Paper.

    I've read it a long time ago and, being from 2018, some things might be outdated.
    Some of the things I remember is while AWS Lambda has its strenghts (pay-as-you-go,
    autoscale), a full serverless architecture presents several I/O performance
    constraints compare to a more traditional EC2 architecure. Cindy Sridharan has some
    good highlights on [her
    Twitter](https://twitter.com/copyconstruct/status/1075086886610169857?s=20). Highly
    recommend viewing Table 1 (but, again, I can't guarantee it hasn't been somewhat
    deprecated given the timeframe).

- Understanding Clojure's Persistent Vectors ([pt.
  1](https://hypirion.com/musings/understanding-persistent-vector-pt-1) / [pt.
  2](https://hypirion.com/musings/understanding-persistent-vector-pt-2))  · _Jean Niklas
  L'orange_ · Article.

    Interesting articles on Clojure's Persistent Vectors, a data structure invented by
    Rich Hickey _which gives practically O(1) runtime for appends, updates, lookups and
    subvec_. When I first heard about it I thought it sounded weird; what's up with the
    constant speed (hint: the word _pratically_ is doing a lot of heavy lifting here)?
    And why the heck so-called [Lazy Sequences](https://clojure.org/reference/sequences)
    always return a [chunk of exactly 32
    values](http://blog.fogus.me/2010/01/22/de-chunkifying-sequences-in-clojure/) when
    realizing its value? Well, these misteries are explained in the articles linked
    above. Also, if you are that kind of person, you can read the paper that inspired
    Persistent Vectors: [Ideal Hash
    Trees](http://lampwww.epfl.ch/papers/idealhashtrees.pdf) · _Phil Bagwell_

- [Command-line Tools can be 235x Faster than your Hadoop
  Cluster](https://adamdrake.com/command-line-tools-can-be-235x-faster-than-your-hadoop-cluster.html)
  · _Adam Drake_ · Article.

  Well, exactly what the title says! Fun examples of how an intelligent use of basic
  unix commands such as `cat` or `awk` in a modern laptop can yield better results than
  a much more powerful Hadoop cluster for certain tasks, such as text processing. I
  mean, check out this quote: _for the same amount of data I was able to use my laptop
  to get the results in about 12 seconds (processing speed of about 270MB/sec), while
  the Hadoop processing took about 26 minutes (processing speed of about 1.14MB/sec)._

- [Mailinator Architecture](http://highscalability.com/mailinator-architecture) · _Todd
  Hoff_ · Article.

  A short article on [mailinator.com](https://www.mailinator.com/) architecture.
  Warning, it is from 2008 so highly dated. Yet, it is an interesting story about how a
  Java App running on a box that's worse than a current-gen `t2.micro` was still
  processing `75 reqps`, handling DDOS and supposedly had `99.99%` availability. Surely
  the application is relatively simple and most modern business have very different
  constraints - if nothing else, the right HA architecture can make mantaining your
  service as a team much easier. At the same time, while it is very hard to compare
  workloads, I'm used seeing microsservices being provisioned with 10 times as much
  resources to serve a tiny fraction of the load, so I feel there's still something to
  learn from this piece.

## Resilience Engineering

- [The Problem with the 5 Whys](https://qualitysafety.bmj.com/content/26/8/671) · _Alan
  J Card_ · Paper.

    Best critique of the "5 Whys" technique that I have ever read. Essentially, it
    _"insists on a single root cause as the target for solutions and assumes that the
    most distal link on the causal pathway [...] is inherently the most effective and
    efficient place to intervene"_. If nothing else, you ought to check out this
    outstanding representation of the "causal and contributing factors tree diagram"
    that different teams might arrive by each applying the "5 Whys" technique
    independently at the same incident.

- [The Infinite Hows](https://www.oreilly.com/radar/the-infinite-hows/) · _John Allspaw_
  · Article.

    If you have enjoyed the previous paper about the 5 Whys and want more, this is a
    good read. John explains why the 5 Whys also isn't that much of a good idea for
    Software Engineers working with complex distributed systems, gives you an
    alternative technique and drops a lot of links so you can spend a whole afternoon
    reading about the topic.

## Negotiation

- [Salary Negotiation: Make More Money, Be More
  Valued](https://www.kalzumeus.com/2012/01/23/salary-negotiation/) · _Patrick McKenzie_
  · Essay.

    Very good article on Salary Negotiation for Software Engineers. If you read _one_
    piece on the topic, make it this one!

- [Sonia Gupta and Corey Quinn - Embarrassingly Large Numbers: Salary Negotiation for
  Humans](https://www.youtube.com/watch?v=jK6yrvsSaFs) · _Corey Quinn & Sonia Gupta_ ·
  Video.

    Fun video on the topic.

## Historical

The references here are mostly kept as historical curiosity.

- [Debunking the 'Expensive Procedure Call' Myth, or, Procedure Call Implementations
  Considered Harmful, or, Lambda: The Ultimate
  GOTO](https://dspace.mit.edu/bitstream/handle/1721.1/5753/AIM-443.pdf) · _Steele, Guy
  Lewis, Jr._ · Paper

    Keeping this in my pocket mostly in case I ever hear someone arguing that an extra
    function call would impact performance and I need something to smack the doofus back
    to the 70's with.

- [Structured Programming with go to
  Statements](http://www.kohala.com/start/papers.others/knuth.dec74.html) · _Donald E.
  Knuth_ · Paper

    The paper that popularized _"pre mature optimization is the root of all evil"_,
    although there's an earlier source from
    [November](https://dl.acm.org/doi/pdf/10.1145/361604.361612). The paper is a
    discussion about `Structured Programming` and the pros and cons of `go to`
    statements so it is very dated. I list it here because of one interesting curiosity:
    although oft-quoted as a warning against any kind of optimization effort, Knuth's
    words are very specifically a comment on sacrifing legibility to optimize
    **non-critical** parts of the program. In fact, he writes it just after using
    _multiple_ `go-to` statement to increase the performance of a program by 12% and
    complaining about how most software engineers wouldn't consider such improvement
    worthy of their attention. He still concludes that _"premature emphasis on
    efficiency is a big mistake which may well be the source of most programming
    complexity and grief"_ and that _"we should strive most of all for a program that is
    easy to understand and almost sure to work"_ but I nevertheless think the original
    context gives the quote a new meaning.
