---
title: "No more waterfall word counts! How DevOps can smooth the documentation process "
permalink: /no-more-waterfall-word-counts/
date: 2014-03-05
layout: single
sitemap: false
tags: invisiblethread,residency,devops,word-counts,monitoring,translation
---

*Cross-posted to [The Invisible Thread](https://www.ibm.com/developerworks/community/blogs/invisiblethread/entry/no_more_waterfall_word_counts_how_devops_can_smooth_the_documentation_process?lang=en) as part of the DevOps social media residency*

Here's a thought exercise for anybody who writes computer code. Imagine that you're working on a two-month task, just like the work that you do all the time. But there's a catch: your boss needs to know how many lines of code you are going to add, change or delete. Your goal is to be correct within 10 percent of the final number of changed lines.

Sounds tough, right? Well, I have to do that before each release of the documentation for a software product. Months before my documentation team's work is finished, I've got to give a count of new, changed and deleted words so the translation centers can plan their work. In general, we call that the translation delta estimate, but I call it the *waterfall word count*. In an agile world, when the software is changing all the time, how accurate do you think that word count is? Yep, not very accurate. As a result, we have to allow a long time to get docs translated, which slows down the release cycle.

![Diagram that shows the bottleneck of agile development teams sending work to be deployed by traditional operations teams][bottleneck_diagram]

[bottleneck_diagram]: ../images/TM_bottleneck.jpg "DevOps bottleneck diagram"

#### Why are translators so fast but translation results so slow?

I've noticed that our translation centers (TCs) are very efficient. Thanks to computer tools that compare words and phrases with previously translated materials, one person can translate thousands of words in a day. At that rate, the TCs can finish the documentation for even large releases in a few days. So why do I have to allow four or more weeks of turnaround time for these jobs?

The answer is that our TCs have a typical operations [pipeline bottleneck](http://blogs.atlassian.com/2013/07/devops-release-management-deployments/). They don't have accurate information about how much work is coming down the pipe and thus have trouble planning. I often overestimate my word count because if I estimate too low, we run into budget and deadline problems. But that makes the problem worse because TCs have to budget time for the inflated amount of work that never arrives.

I see three simple ways to fix this problem:

- Remove the bottleneck by making the writers learn 12 new languages and do their own translation.
- Consult a psychic to help us make perfect translation delta estimates months in advance.
- Stop translating our work and sell only to English-speaking countries.

Just kidding! The good news is that DevOps principles point to a better way of handling this problem.

#### This looks like a job for continuous monitoring!

Lots of enterprise-level translation projects use multiple translation drops to smooth out the workload for the TCs (for some background on that strategy, download [Modelling Continuous Translation.ppt](http://www.fredhollowoodconsulting.com/articles/Modelling%20Continuous%20Translation.ppt). However, one or two extra translation drops just don't fix the problem.

Here's the plan I'm working on: we estimate the final waterfall word count as usual, but we also set up an automatic translation delta count that runs as part of our nightly builds. As the release moves ahead, we can project those word counts forward so we can see how we're progressing. The following graph shows how that might look. In this example, the original word count (red dot) was high, but who can tell that it's high without other information? The green line shows that the individual word counts run over nightly builds, and the blue line shows a regression analysis of those word counts — basically a mathematical estimate of where those counts are headed. In this case, the regression line shows that the work is coming in below the word count estimate.

![Diagram of regular translation word count deltas over time, approaching a translation drop date][regression_diagram]

[regression_diagram]: ../images/ContinuousMonitoringTranslation.gif "Continuous translation monitoring diagram"

This scenario above is all [slideware](http://c2.com/cgi/wiki?SlideWare); none of these tools are yet automated and nothing here works the way I'm describing it. In order to get this working even at a basic level we'd need to automate the following tasks:

- Translation packaging to pack up the files into a format that the TCs and their tools can work with
- Translation delta estimation — we've got tools to do this but they need to be automated
- Final word count reports to let the writers know what the final delta was — surprisingly, we don't often get that information, so it needs to be part of the translation process

I'm hoping that if we can get this continuous, accurate information to the TCs (the “Ops” side in this DevOps allegory), they can put that info to good use and pass the benefits on to the writers and developers. Of course, we also run into the problem of changing the culture to support DevOps principles, but I'm going to have to leave that for another blog post.

This is a small step in using DevOps principles to improve our documentation efforts, and I'm just getting started. I'd be thrilled to hear if anyone else is getting into this kind of work or has thoughts about it, so get in touch.
