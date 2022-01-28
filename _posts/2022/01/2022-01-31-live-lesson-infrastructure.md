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

Following the guidelines we set out in [our post on design
principles][design-principles], The Carpentries Workbench is built with R and
Pandoc in three custom packages called [{sandpaper}], [{varnish}], and
[{pegboard}] for deployment, styling, and validation, respectively. To find out
more about the process we used for validating that the infrastructure, you can
read our [blog post about the alpha testing][alpha-test] and our [blog post
about the UX testing and design][ux-test], or if you have 20 minutes to spare,
you can [watch a video of Zhian's UseR!2021 talk: "Using R as Community
Workbench for The Carpentries Lesson Infrastructure][yt-vid] (with [slides
available here](https://zkamvar.github.io/user2021/#1)).

Because we deeply understand the implications of changing things too rapidly,
we are going to make this transition as smooth as possible, starting with **a
soft beta release April 2022** with interested maintainers, lesson authors, and
instructors. **Are you interested in helping out with testing the new
infrastructure in how you work (either teaching, authoring, or maintianing)**


## Show me!

You can see The Carpentries Workbench in action at [the documentation 
site][workbench]. Of course, pictures are worth a thousand words. I have
converted the "Programming With Python" Software Carpentry Lesson and hosted it
in a sandbox github organisation[^note that this conversion was automated, so
there may be a few rendering errors]. This is what the 'Making Choices' episode
of the "Programming with Python" lesson looks like right now using the [Styles
template][styles]:

<figure>
  <img src="{{site.urlimg }}/blog/2022/01/2022-01-31-python-choice-old.png" 
   alt="Screen capture of the 'Making Choices' episode in the Programming With Python lesson using The Carpentries Styles. It has a toolbar at the top with the episode title and a yellow box containing timings, questions, and objectives."/>
  <figcaption>
Screencapture of <a href="https://swcarpentry.github.io/python-novice-inflammation/07-cond/">Programming With Python built with the Styles template</a> on 2022-01-27
  </figcaption>
</figure>

In this example repository, I show what it will look like when we implement [The
Carpentries Workbench][workbench]:

<figure>
  <img src="{{site.urlimg }}/blog/2022/01/2022-01-31-python-choice.png" 
   alt="Screen capture of the 'Making Choices' episode in the Programming With Python lesson using The Carpentries Workbench. It has a toolbar at the top followed by a progress bar that indicates this episode is 55% through the lesson, and a sidebar with navigation that says CHAPTERS. The main content shows the episode title and a grey and blue overview box showing questions and objectives "/>
  <figcaption>
Screencapture of <a href="https://fishtree-attempt.github.io/python-novice-inflammation/07-cond">Programming With Python built with the Carpentries Workbench</a> on 2022-01-27
  </figcaption>
</figure>

Callout blocks are getting a makeover as well. Compare two callout blocks from 
the introductory episode of the lesson:

<figure>
  <img src="{{site.urlimg }}/blog/2022/01/2022-01-31-python-callout-old.png" 
   alt="Screen Capture of the first callout block from the introductory episode in the Programming with Python lesson using The Carpentries Styles. It shows a yellow box with a pushpin icon at the top and a title that says 'Variables as Sticky Notes'. The text is small and it has three images and two code blocks inside."/>
  <figcaption>
Callout block from <a href="https://swcarpentry.github.io/python-novice-inflammation/01-intro/">Programming With Python built with the Styles template</a> on 2022-01-27
  </figcaption>
</figure>

<figure>
  <img src="{{site.urlimg }}/blog/2022/01/2022-01-31-python-callout.png" 
   alt="Screen Capture of the first callout block from the introductory episode in the Programming with Python lesson using The Carpentries Workbench. It shows a grey box with a  dark grey border on the left and bell icon in a dark grey box and a title that says 'Variables as Sticky Notes'. The text is larger and there are three images and two codeblocks inside. The code blocks have thick lines running across the top that clearly separate them from the content."/>
  <figcaption>
Callout block from <a href="https://fishtree-attempt.github.io/python-novice-inflammation/01-intro">Programming With Python built with the Carpentries Workbench</a> on 2022-01-27
  </figcaption>
</figure>

For a full list of features in the episodes, you can visit the [Episode 
Structure](https://carpentries.github.io/sandpaper-docs/episodes.html) episode 
in the Carpentries Workbench documentation. 

### For Instructors: Instructor Notes

One resource that is useful for instructors teaching new-to-them lessons is the
instructor notes, but this page is often buried in the "extras" dropdown menu
and while it is useful to have the overview, the new infrastructure offers a way
to include these _in context_ in the lesson with the new _instructor view_.

First, visit <https://carpentries.github.io/sandpaper-docs/episodes#instructor-notes> and you will see a section that contains a heading, paragraph, and a discussion block (in yellow).

Now, visit <https://carpentries.github.io/sandpaper-docs/instructor/episodes#instructor-notes> and you will find an instructor note revealed:

<figure>
  <img src="{{site.urlimg }}/blog/2022/01/2022-01-31-instructor-note.png" 
   alt="Screen capture of a section showing an embedded instructor note which appears as a light grey rectangle spanning the page with a magenta box containing a white pencil icon on the left and a downward-pointing chevron on the right indicating that it contains content."/>
  <figcaption>
Screencapture of an instructor note from <a href="https://carpentries.github.io/sandpaper-docs/episodes#instructor-notes">The Carpentries Workbench Documentation</a> on 2022-01-27
  </figcaption>
</figure>

Once we have the infrastructure established, we hope to organise instructor
note sprints for our instructors to share their knowledge and contribute to the
lesson development and maintenance.

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

### And More!!!

There are many more features that should make authoring, contributing, and
maintaining lessons easier for everyone including automated checks for 
missing alt text, abnormal heading structure, and invalid internal links.

We are now piloting the inclusion of BioSchemas metadata in our
lessons so that they can be indexed at [ELIXER's Training Portal, 
TeSS](https://tess.elixir-europe.org/), which will give more exposure to the
work of our lesson authors and maintainers.

One of the things I'm really excited about with the lesson infrastructure is a
[less invasive and faster build process for our R-based
lessons][sandpaper-cache] that freezes the package versions and provides [pull
request previews][pr-preview] that will avoid lessons suddenly breaking when
new package versions being released.

### Demonstration

Zhian is going to implement and fill this in on Friday :weary:

## Transition Plan

As I mentioned earlier, we will not make this transition all at once. There are
over a hundred lessons across The Carpentries (including Lab and Incubator),
each with their own unique setup. Before any transition will happen, we will do
one final lesson release and then slowly migrate the lessons based on an opt-in
process by the maintainers and the instructors will be notified at least two
weeks in advance of the migration. 

For the maintainers, I have set up [a workflow for automated conversion with
customisation](https://github.com/data-lessons/lesson-transition/), and once
the maintainers/authors of the lesson are ready and they consent, I will
transition the lesson, preserving the commit history (stripping the styles-
specific commits). 

## Future Plans

The Carpentries Workbench is the first step towards making our lesson
infrastructure more equitable and accessible, but we are far from finished. In
the future, we can envision a lesson infrastructure that drives lesson
developers towards the pit of success in terms of creating accessible and
up-to-date lessons in any lanuguge (both human and computer).

OMAR PLEASE HELP THING OF A GOOD ENDING


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
[sandpaper-cache]: https://carpentries.github.io/sandpaper/articles/building-with-renv.html
[pr-preview]: https://carpentries.github.io/sandpaper-docs/instructor/pull-request.html
