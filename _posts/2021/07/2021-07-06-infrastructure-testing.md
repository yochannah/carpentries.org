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

Our lesson infrastructure was built on top of the Jekyll static site generator with the idea that we not only provide a way for people to quickly go from markdown documents to a website, but also show how all of the tools we teach work on a live project.
[The current infrastructure](https://github.com/carpentries/styles/) comes as an all-in-one repository that contains the styling elements (CSS, HTML, and JavaScript), tools for validation (Python scripts), and tools for building the lessons (R scripts and a Makefile).
Over time, we have developed materials for getting started with developing a lesson such as the [Lesson Example Website ](https://carpentries.github.io/lesson-example/) and the [Curriculum Development Handbook](https://carpentries.org/blog/2021/05/lesson-template-design-process/) to aid the contributor to developing their own lessons.
Despite the documentation, we have been finding many ways in which contributors were uncomfortable or felt intimidated by the infrastructure so that they would end up spending a half hour debugging an out-of-date makefile or avoiding installing it alltogether and hoping for the best via GitHub's editor. 

As our community has grown, it became evident that our infrastructure would not easily scale as lessons would rapidly fall out-of-date with the current toolchains and styling. 
We proposed [design principles of the next iteration of the lesson template][depr] to guide us in making lesson contribution a better experience for all involved.
Of course, [as we have learned from previous iterations of the lesson template][previous-iteration], if we create something that does not work for the community, it is useless.
This is why, when we had a stable (but not necessarily pretty) framework, we needed to test it with the community.

## Alpha Testing



[depr]: https://carpentries.org/blog/2020/08/lesson-template-design/
[ux-path]: https://carpentries.org/blog/2021/05/lesson-template-design-process/
[previous-iteration]: https://software-carpentry.org/blog/2015/07/pushing-back.html
