---
layout: page
authors: ["Zhian N. Kamvar"]
teaser: "Ensuring our redesign is friendly and usable for maintainers at all skill levels."
title: "Alpha Testing the Lesson Infrastructure Redesign"
date: 2021-07-06
time: "00:00:00"
tags: 
- "Carpentries Lessons"
- "Community"
- "Maintainer"
- "Infrastructure"
- "Lesson Infrastructure"
- "Carpentries Incubator"
- "Carpentries Lab"
---

## Introduction

> This is an ongoing series of blog posts about the next iteration of the Lesson Infrastructure.
> Find more about our [Design Principles][depr] and our [Path to the Design for the Lesson Website][ux-path]

<!-- Our lesson infrastructure was built on top of the Jekyll static site generator with the idea that we not only provide a way for people to quickly go from markdown documents to a website, but also show how all of the tools we teach work on a live project. -->
<!-- [The current infrastructure](https://github.com/carpentries/styles/) comes as an all-in-one repository that contains the styling elements (CSS, HTML, and JavaScript), tools for validation (Python scripts), and tools for building the lessons (R scripts and a Makefile). -->
<!-- Over time, we have developed materials for getting started with developing a lesson such as the [Lesson Example Website](https://carpentries.github.io/lesson-example/) and the [Curriculum Development Handbook](https://carpentries.org/blog/2021/05/lesson-template-design-process/) to aid the contributor to developing their own lessons. -->
<!-- Despite the documentation, we have been finding many ways in which contributors were uncomfortable or felt intimidated by the infrastructure so that they would end up spending a half hour debugging an out-of-date makefile or avoiding installing it alltogether and hoping for the best via GitHub's editor. --> 

As our community has grown, it became evident that our infrastructure would not easily scale as lessons would rapidly fall out-of-date with the current toolchains and styling. 
We proposed [design principles of the next iteration of the lesson template][depr] to guide us in making lesson contribution a better experience for all involved.
Of course, [as we have learned from previous iterations of the lesson template][previous-iteration], if we create something that does not work for the community, it is useless.
This is why, when we had a stable (but not necessarily pretty) framework, we needed to test it with the community.

After investigating several options from our lesson infrastructure, we realized that the [R publishing ecosystem][rmd] aligned best with our values because it has friendly communities, is available as a binary application on all operating systems, and allows us to integrate with all the features we currently offer. 
From this idea, we created three R packages to host the engine, validator, and styling, called [{sandpaper}], [{pegboard}], and [{varnish}], respectively.
We have not yet officially released these packages, but you are free to try them out for yourself! You can get started by visiting https://carpentries.github.io/sandpaper-docs/.
This post describes our efforts to test changes coming to [callout blocks][bq] and the overall infrastructure.

## Alpha Testing

The alpha testing is a 'bare bones' testing that is designed to identify common stumbling blocks and any unforseen difficulties that arise from real user experiences.
We wanted to assess three major aspects of lesson development: infrastructure installation, lesson creation, and lesson contribution.

### Challenge Syntax

Our first challenge was to assess alternatives to the [callout block quote syntax][bq], which was difficult to construct if you were creating a challenge/solution pair of nested block quotes:

```markdown
> ## Challenge Example
>
> This is challenge text
>
> > ## Solution example
> >
> > This is the solution
> >
> {: .solution}
{: .challenge}
```

We recurited maintainers for anonymous testing and proposed three potential solutions for this syntax using one of three alternatives:

1. HTML `<div>` tags, ([example HTML syntax](https://zkamvar.github.io/glowing-chainsaw/03-div-challenge-blocks.html))
2. custom [code block syntax based on Oxygen (codename: dovetail)][dovetail], ([example dovetail syntax](https://zkamvar.github.io/glowing-chainsaw/04-dovetail-challenge-blocks.html))
3. pandoc [section fences (aka fenced-divs)][en-garde] ([example section fence syntax](https://zkamvar.github.io/glowing-chainsaw/05-fenced-div-challenge-blocks.html))

In the end, the [pandoc section fence syntax][en-garde] won the challenge because it was the easiest to use (6/11) and [participants made the fewest syntax errors][results][^1] when they were asked to [reproduce a challenge/solution block in that syntax without rendering the result to HTML][challenge]. 
HTML was the winner in terms of initial clarity (8/11) and near equally easy to use with fenced divs (5/11).
There were several issues around mixing HTML and markdown because particpants either forgot to [pad the HTML with whitespace][nows] or because [indented HTML code is interpreted as a code block][indent].

Below are some comments from our testers regarding the pandoc section fence syntax:

> ...the pandoc looked more confusing, but when I read about what it requires it's less specific and so the eaisest.

> The fact that pandoc fenced div tags don't have any specific length and don't need to match in length at start and end tags confused me.

> It is easier to parse the pandoc version visually to see the nested structure.

>  For html and pandoc, I like that the text inside the blocks is no different than the usual markdown syntax (I think) and the tag style (open/close) of indicating the blocks makes sense to me. 
> It's really a toss up between which is "better" -- html is less typing and I've seen it before, hence the edge, but I'd be happy to use either in a lesson.

> Pandoc fenced divs are super easy to type, copy paste and move around.

> ...easier to see where the divs close in the pandoc fenced syntax. keeps everything in markdown so it's consistent.

Once we identified the appropriate syntax, we could further refine our design for the lesson infrastructure, which brings us to the infrastructure testing. 

### Infrastructure Testing

Our new infrastructure consists of R and pandoc with our three in-house packages to coordinate, validate, and style our lessons.

We tested the alpha version of our infrastructure between May and June 2021.
For this testing phase, we recruited people from all across our community including maintainers, instructors, core team members, and even people who were brand new to The Carpentries. 
Another aspect was understanding how comfortable the participants were with using our current infrastructure AND how comfortable they were with R.
Our goal was to assess three salient aspects:

1. Is the infrastructure installable?
2. Can participants create a lesson?
3. Can participants contribute to a lesson?

Beyond that, we conducted 20 minute post-feedback interviews to assess how comfortable they were with the new infrastructure and how it compared with the previous iterations.

#### Results

We recurited a total of 19 volunteers to test the infrastructure. 
Every single participant was able to install the infrastructure successfully.

![Scatter plot showing no correlation between infrastructure installation success and Jekyll comfort level (y axis) or R comfort level (x axis).]({{ site.filesurl }}/images/blog/2021/07/infra-alpha-results.svg)




[depr]: https://carpentries.org/blog/2020/08/lesson-template-design/
[ux-path]: https://carpentries.org/blog/2021/05/lesson-template-design-process/
[previous-iteration]: https://software-carpentry.org/blog/2015/07/pushing-back.html
[rmd]: https://bookdown.org/yihui/rmarkdown/
[{sandpaper}]: https://carpentries.github.io/sandpaper
[{pegboard}]: https://carpentries.github.io/pegboard
[{varnish}]: https://github.com/carpentries/varnish
[bq]: https://carpentries.github.io/lesson-example/04-formatting/index.html#special-blockquotes 
[dovetail]: https://github.com/carpentries/dovetail#example
[en-garde]: https://pandoc.org/MANUAL.html#extension-fenced_divs
[challenge]: https://zkamvar.github.io/glowing-chainsaw/07-complex-nested.html
[results]: https://zkamvar.github.io/glowing-chainsaw/08-survey-results.html
[nows]: https://github.com/zkamvar/glowing-chainsaw/commit/c45c1022376e2d756b9b921cd1a60160c9a27cdd#r43706766
[indent]: https://github.com/zkamvar/glowing-chainsaw/commit/43c8eaa5e5db0f4b99393d02598485fc8b837325#r43115050
[^1]: The only syntax error occurred when [one participant typed an upper-case `Challenge` instead of a lower-case `challenge`](https://github.com/zkamvar/glowing-chainsaw/commit/d659cc501a655a08b7625e9258ef0dcce60416ac#r43122398).
