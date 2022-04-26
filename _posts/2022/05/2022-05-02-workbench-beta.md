---
layout: page
authors: ["Zhian N. Kamvar"]
teaser: "Initial outline and plan for the Beta Phase of The Carpentries Workbench"
title: "The Carpentries Workbench: Beta Phase and Beyond"
date: 2022-05-02
time: "09:00:00"
tags: ["Lesson Infrastructure", "Community", "Carpentries Workbench", "Beta"]
---

## TL;DR

We will be transitioning some of the lessons to The Carpentries Workbench in the
next few months as a beta test. The beta test will live in parallel to the
current lessons for at least two months before fully transitioning. If you are a
maintainer, and would like to have your lesson enter the beta test, please [sign
up and tell us about your lesson and when is the earliest time for you to start 
the beta testing][beta-test-signup-maintainer].

We expect to transition all lessons (including incubator and lab) to use [The
Carpentries Workbench][sandpaper-docs] by January 2023.

## Things are going to get beta

We are pleased to announce that we are officially opening applications for
maitnainers to volunteer for beta testing The Carpentries Workbench on their own
lessons. This post will be relatively short, but details can be found in [the
presentation I gave during the April Maintainer Meeting][beta-test-slides]. 

While we have lessons such as [The Workbench Documentation][sandpaper-docs] and
[Collaborative Lesson Development Training][ldt] that currently use the
workbench, understanding the advantages and limitations of the workbench can
only be achieved if we use it on a variety of lessons and maintainers. **The
purpose of the beta phase is to test out the workbench in conditions that I have
no control over.** Thus, we would like to get a breadth of lessons using The
Workbench.

Before I go on, because I will be referring to two versions of any given lesson,
I want to introduce some helpful terminology:

"styles"
: The Jekyll-based engine and styling that has been the basis of Carpentries
  lessons from 2015--Present: https://carpentries.github.io/lesson-example/. 
  *Example: the styles version of the git lesson is at 
  https://swcarpentry.github.io/git-novice*

"workbench"
: The Pandoc + R-based engine and styling that will replace styles:
  https://carpentries.github.io/sandpaper-docs
  *Example: the beta (workbench) version of the git lesson is 
  https://lessons.sofware-carpentry.org/git-novice*

### Why have a beta phase at all?

Our lesson have a _wide_ audience including, instructors, learners, maintainers,
and others who use the CC-BY content in their own work. In the past, [changes to
the way we build lessons happened at a fairly rapid pace][blog-pushing-back],

### What will change?

 - Lesson URLs will change during the beta phase to use an official program
   URL.  For example, The Programming with R lesson,
   `https://swcarpentry.github.io/r-novice-inflammation/` will become
   `https://lessons.software-carpentry.org/r-novice-inflammation`.
 - Lesson folder structure will be rearranged, and the folders containing
   styling will be removed.
 - Syntax will be more aligned with GitHub-flavored Markdown
 - Templating language will be removed

### How long will this take?

The beta test will be gradual in three phases per lesson:

1. **pre-beta** (~4 weeks): A snapshot of a lesson using the workbench is available
   at the new lesson URL, while the styles version of the lesson will remain at
   the original URL with a banner announcing the beta phase with a link for
   feedback. This will be a sandbox for maintainers and instructors to get used
   to the website before migration.
2. **beta** (~6-8 weeks): The lesson will be given a banner announcing that the 
   final transition will occur 8 weeks from that date. The styles version of
   the lesson is given a lesson release on Zenodo. The lesson will be
   transitioned from styles to workbench via [the lesson-transition
   script](https://github.com/data-lessons/lesson-transition/), using `main` as
   the default branch. The styles version of the lesson will be frozen in an
   orphan branch called "legacy", continuing to serve the default URL. **Any 
   changes from this point onwards will update the workbench version of the 
   lesson.**
3. **pre-release** (~6 months): The styles version of the lesson is removed from
   the repository and the default URL will redirect to the lessons URL. We run
   this for six months to allow maintainers to fix any minor bugs in the lessons.


<figure style="text-align: center">
  <img src="{{ site.urlimg }}/blog/2022/05/workbench-beta-flow.png" 
   alt="Diagram of three phases of the beta release. At the top is box labelled 'current' that contains a github logo, a cartoon of a lesson page. Below is a box labelled 'Pre Beta' with the same contents as the box above plus an additional github logo in blue with a camera above it (to indicate a snapshot) and a new cartoon of a lesson page with a padlock over it. There is a clock indicating a timeframe of four weeks. The next box below is labelled 'Beta'. The GitHub logo has become blue and there is a lightning bolt and a line connecting it to the previous logo, indicating that a transformation happened. A smaller, grey github logo is adjacent with a lock over it, indicating that it is archived. The  old lesson page now has a lock and information symbol above it. The new lesson page does not have any symbols above it. The timreframe is 6 to 8 weeks. The final box is titled 'Release Candidate' and has a single blue github logo, a faded old lesson page, and a new lesson page with a timeframe of 6 months"/>
  <figcaption>
An overview of the beta phase, separated into three steps. The entire process will take about 8-9 months until lesson release with The Carpentries Workbench.
  </figcaption>
</figure>

## Challenges

Of course, this transition will not be without any number of challenges.

### Cognitive load

Teaching a workshop is hard and learning coding skills is hard. Testing out a
new format of a website on top of that is added cognitive load, especially if
only ONE lesson is different from the others. We mitigate this by having two
versions of the lesson for three months. This way, even if one out of three
lessons is currently in Beta, the default lesson website is still available so
the transition is not so jarring. 


[beta-test-signup-maintainer]: https://example.com/#TODO
[beta-test-slides]: https://docs.google.com/presentation/d/1qA9U4BkLKW_kOn696jKkDbUgv910_i-sGbHTZ9tyURQ/edit?usp=sharing
[sandpaper-docs]: https://carpentries.github.io/sandpaper-docs
[ldt]: https://carpentries.github.io/lesson-development-training/
[blog-pushing-back]: https://software-carpentry.org/blog/2015/07/pushing-back.html
[design-principles]: https://carpentries.org/blog/2020/08/lesson-template-design/
[{sandpaper}]: https://carpentries.github.io/sandpaper/
[{pegboard}]: https://carpentries.github.io/pegboard/
[{varnish}]: https://carpentries.github.io/varnish/
[alpha-test]: https://carpentries.org/blog/2021/07/infrastructure-testing/
[ux-test]: https://carpentries.org/blog/2021/05/lesson-template-design-process/
[yt-vid]: https://www.youtube.com/watch?v=vd8XZSuY_Rs&list=PLSFzyC3wp8-csb8rtreOUoW8C_1J87QD5&index=1&t=1271s
[workbench]: https://carpentries.github.io/sandpaper-docs
[styles]: https://github.com/carpentries/styles/
[slide-19]: https://zkamvar.github.io/user2021/#19
[old-episodes]: https://web.archive.org/web/20220125163344/https://carpentries.github.io/sandpaper-docs/episodes.html
[new-episodes]: https://web.archive.org/web/20220128171242/https://carpentries.github.io/sandpaper-docs/episodes.html
[sandpaper-cache]: https://carpentries.github.io/sandpaper/articles/building-with-renv.html
[pr-preview]: https://carpentries.github.io/sandpaper-docs/instructor/pull-request.html

[^1]: We are moving away from the 'template' terminology to describe our lesson infrastructure because it has caused some confusion in the past.
[^2]: Note that this conversion was automated, so there may be a few rendering errors---please open an issue on the repository if you find any.

