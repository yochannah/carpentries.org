---
layout: page
authors: ["Zhian N. Kamvar", "Alycia Crall"]
teaser: "We re-evaluate the historical role of the Lesson Infrastructure Community to understand how we can maintain community advocacy in our infrastructure"
title: "The Lesson Infrastructure Commitee: Past, Present, and Future"
date: 2021-12-17
time: "09:00:00"
tags: ["Lesson Infrastructure", "Community"]
---

Take a moment to browse [Greg Wilson's original HTML lecture for The Unix Shell (2006-11-27)](https://web.archive.org/web/20070225214536/http://www.swc.scipy.org/lec/shell01.html) and then head over to [the most recent snapshot of The Unix Shell (2021-10-23)](https://web.archive.org/web/20210710233318/https://swcarpentry.github.io/shell-novice/02-filedir/index.html). 

Back then:

 - markdown was only 2 years old 
 - git was only 3 years old
 - github did not exist
 - jekyll did not exist
 - smartphones and tablets did not exist

The lesson infrastructure has evolved so much in the past 14 years along with the vastly changing landscape of online publishing where it is now easier than ever to publish a website from a handful of markdown documents.

A large part of my job for the last 20 months has been to learn from the Maintainer community and subsequently understand, analyse, and re-imagine our lesson infrastructure in a centralised way that can serve our Maintainers, Instructors, and Learners equitably and reduce barriers for entry.

None of these achievements could have been possible without the input from the community of Maintainers, Instructors, and Learners who helped with the alpha and UX testing of the new lesson infrastructure. These efforts all built off of the ideas generated from the Lesson Infrastructure Committee and we are not yet through! 

Over the last couple of months, I sent out a call to former Lesson Infrastructure Committee members to sit down and tell me about their experiences with the committee so that I could see what such a committee might look like in light of the next interation of the infrastructure, and if such a committee need exist.

One of our central values in The Carpentries is that we champion community collaboration. Our lesson infrastructure has gone through many iterations and will likely go through many more. Each of these iterations would not have been possible without some form of community input. From 2006 to 2017, the lesson infrastructure was an interesting creature: born in the open and evolved through the efforts, whims, and passions of a small community of voluteers.

## A Brief History of the Lesson Infrastructure Committee

In 2018, the Lesson Infrastructure Committee was created to achieve the following goals: 

1. Manage lesson release process and coordinate lesson releases
2. Group decision-making for any changes that will affect more than one lesson
    - This applies to lessons officially described as “supported” by the Carpentries
3. Maintenance of the following general repositories:
 - [carpentries/styles](https://github.com/carpentries/styles)
 - [lesson-example](https://github.com/carpentries/lesson-example)
 - [workshop-template](https://github.com/carpentries/workshop-template)

Some larger acheivements from the committee were to make the template more accessible. These included updating the infrastructure to be more friendly to Windows users and employing the use of continuous integration to build R Markdown lessons. These acheivements were successful largely because the problems were well-scoped, easy to implement, and the communication of the changes was straightforward. The committee worked well when it considered the question "Will this workflow inhibit contribution?" 

The vast majority of these decisions were made with consensus and implemented by whichever person had time to implement them, but as with all large projects, there were challenges that would leave the members of the committee feeling discouraged. These challenges included ambitious tasks that the community really wanted, but were either not well-scoped or required planning and implementation that were beyond the scope of a volunteer committee (e.g. it would require at least a week of full time developer attention).

Additionally, because of the "exposed-plumbing" nature of the infrastructure and difficulty with which updates were brought into lessons, it became more difficult to communicate more nuanced features to the growing pool of Maintainers, who all had varying levels of expertise. 

In March 2020, a global pandemic descended and the committee was put on indefinite hiatus to respect the time and effort of the committee members. The committee has not been reconvened. 

## What is the Future of the Lesson Infrastructure Committee?

Our Carpentries community comes together for many reasons, and one of those is because we care deeply about lowering the barriers for people to learn basic computational and data skills. Our lessons are entirely written by volunteer effort and our volunteers should not worry about minor details about lesson formatting. 

Our new lesson infrastructure removes much of the temptation for [bikeshedding](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3976103/?report=classic#s7) by completely separating the tools from the lessons themselves. One thing is clear: if we want to ensure that our lesson infrastructure adheres to our core values, we need to have a clear path for community input. At this time, the new infrastructure is not yet in a mature state. It is currently operational and we have determined through testing and feedback that the approach is sound, but the documentaion needs vast improvment and unguided testing from maintainers/lessond developers is still necessary. To have a committee meet to discuss this rapidly-shifting work would be a waste of their valuable time, especially as the pandemic continues to loom and we are still adapting to the ever changing policy landscape and stress it wrought. 

We will make a call for people to join the new committee when we release the first stable version of the lesson infrastructure in 2022 and it is likely that the new committee will take on a different form than the previous committee: I will serve the committee in a similar fashion that the Core Team serves the Executive Council. The committee will serve as a brain trust through which well-scoped challenges with multiple options will be presented and discussed. They will ensure that the lesson infrastructure continues to adhere to our core values.

I would like to thank the former Lesson Infrastructure Committee members for taking the time to sit down with me and tell me about their experiences. Without their input, we would not be where we are today.

