---
layout: page
authors: ["Zhian N. Kamvar"]
teaser: "We announce the first draft of our accessible lesson infrastructure and call for beta testers"
title: "First Draft of The Carpentries Workbench"
date: 2022-01-31
time: "09:00:00"
tags: ["Lesson Infrastructure", "Community"]
---

## What is The Carpentries Workbench?

[The Carpentries Workbench][workbench] is a fresh redesign of our lesson
template from the ground up that clearly separates the tools from the content.
We hope it will better serve the needs of our community members and create
paths forward for improving access, portability, stability, and reliability of
our lesson infrastructure as the repoirtoir of our lesson developers continues
to grow.

Following the guidelines we set out in [our post on design principles][design-principles],
The Carpentries Workbench is built with R and Pandoc in three custom packages
called [{sandpaper}], [{varnish}], and [{pegboard}] for deployment, styling,
and validation, respectively. To find out more about the process we used for
validating that the infrastructure, you can read our [blog post about the alpha
testing][alpha-test] and our [blog post about the UX testing and design][ux-test],
or if you have 20 minutes to spare, you can [watch a video of Zhian's UseR!2021
talk: "Using R as Community Workbench for The Carpentries Lesson
Infrastructure][yt-vid] (with [slides available here](https://zkamvar.github.io/user2021/#1)).

## Show me!

### For Maintainers: Getting the Latest Features!

Our [current lesson template][styles] can be thought of as an all-in-one box of
tools that you can add markdown files to and get a lesson out of at the end. One
of the biggest pain points of this setup is that [as the template improves, 
older lessons rapidly become outdated and miss out on new features][slide-19].
The official way to update a lesson with the new features is to manually create
a pull request from the [styles repository][styles], but this can lead to a 
backlog of github notifications:

![List of notifications requesting an update of lessons with the styles template]({{ site.urlimg }}/blog/2022/01/2022-01-31-gh-notifications.png)

With the new lesson infrastructure, changes, even major changes are applied
immediately. Take for example this [chapter on editing (captured on 
2022-01-26)][new-editing] and compare it with [the same content, but using the 
previous version of the lesson infrastructure][old-editing]. This change
happened with the click of a button (or had I been patient, I could have just
waited a week for the change to implement itself). 

### Demonstration

## Transition Plan

## Future Plans

### Beta Testing (April 2022)

### Improvements/Integrations

 - bring current infrastructure to feature pairity with old infrastructure
   - Image Page
   - all in one (aio) page
   - integrated search bar
   - non-menu resources
 - Integration with [glosario](https://glosario.carpentries.org/)
 - Localisation (l10n) for lessons written in different languages
 - Simplification of build processes
 - Accessibility alerts
 - Standardized authorship and metadata generation
 - Interactive dashboards for monitoring lesson contents, accessibility (a11y), and contributions

[design-principles]: https://carpentries.org/blog/2020/08/lesson-template-design/ 
[{sandpaper}]: https://carpentries.github.io/sandpaper/
[{pegboard}]: https://carpentries.github.io/pegboard/
[{varnish}]: https://github.com/carpentries/varnish#readme
[alpha-test]: https://carpentries.org/blog/2021/07/infrastructure-testing/
[ux-test]: https://carpentries.org/blog/2021/05/lesson-template-design-process/
[yt-vid]: https://www.youtube.com/watch?v=vd8XZSuY_Rs&list=PLSFzyC3wp8-csb8rtreOUoW8C_1J87QD5&index=1&t=1271s
[workbench]: https://carpentries.github.io/sandpaper-docs
[styles]: https://github.com/carpentries/styles/
[slide-19]: https://zkamvar.github.io/user2021/#19
[old-episodes]: https://web.archive.org/web/20220125163344/https://carpentries.github.io/sandpaper-docs/episodes.html
[new-episodes]: https://web.archive.org/web/20220127011238/https://carpentries.github.io/sandpaper-docs/episodes.html
