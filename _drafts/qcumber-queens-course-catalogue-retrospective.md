---	
layout: post
title: "Qcumber (Queen's course catalogue): A Retrospective"
description155: "Qcumber is an unofficial course catalogue for Queen's University, created to fill the severe absence of course-finding tools. It was launched in 2012."
search_title70: "The Qcumber Course Catalogue: A Retrospective"
tags:
    - reflections
    - programming
    - qcumber
type: post
published: true
main_square_image_url: /static/images/posts/qcumber/logo.png
main_square_image_alt: "Qcumber logo"
---

Qcumber is a simple, accessible course catalog for Queen’s University students. Creating its original incarnation and sharing was a wonderful experience, but since I've been out of Queen’s for 18 months, this post will help me relinquish it to future students (especially those who are continuing to maintain and improve it).

The impact and progress made with the site has been exciting to witness; it has grown to involve eight direct contributors, and recently surpassed the 1,000,000 pageview mark! Qcumber was the first complete website I ever developed, and I regard it as a great success in utility and personal learning. Its current state is the result of many people's work, so I encourage you to read the acknowledgements section. :)

{% include captioned_image.html src="/static/images/posts/qcumber/home.png" caption="Qcumber's homepage at the time of this post" cls="inline-padded" %}

Vision
------

The vision for Qcumber is extremely simple: we strongly believe that:

- a catalogue should support "modern" (non-broken) ways of sharing and browsing, like linking to pages, opening tabs, and using the browser's back button
- course descriptions, prerequisites and timeslots should be accessible to anyone, not just signed-in current students

Surprisingly, neither of these were available in fall of 2012, when the university bought a new registration system and stopped updating the traditional catalogue website. The features offered by Qcumber are not revolutionary! Nevertheless, they set Qcumber apart from the current offerings to this day.

Thanks to Qcumber, there exists a single page with description, prerequisite, and timeslot information for each course at the university. Here is a screenshot illustrating a typical course page.

{% include captioned_image.html src="/static/images/posts/qcumber/course-page.png" caption="A typical course page" cls="inline-padded" %}

Since launch, the team (please see acknowledgemnts at the bottom) have added some extra features to make things even better. These include:

- instant term filters
- links to textbooks and past exams
- inserting links in prerequisite texts
- a university department contacts page

In development, there is also a [new version](http://new.qcumber.ca) of the site (which has better search capabilities), and an awesome [prerequisite chart](/static/images/posts/qcumber/prerequisite-graph.png) generator.

Traffic
-------
As mentioned before, we've hit the 1,000,000 pageview mark, with our peak day reaching over 26,000 pageviews! It is evident that Queen's students sorely miss the regular browsing experience when trying to organize their schedule each semester.

Here is the summary of traffic to the site:

{% include captioned_image.html src="/static/images/posts/qcumber/stats-summary.png" caption="The summary of Qcumber traffic since launch" %}

Some interesting patterns are very apparent!

{% include captioned_image.html src="/static/images/posts/qcumber/graph-annotated.png" caption="A timeline showing the history of Qcumber" %}


Acknowledgments
---------------

The significant contributions of my friends in both updating the site and adding new features means I cannot nearly claim the site as my own anymore. In fact, I have barely touched it in the past year. The following people are to thank for many of Qcumber's features, fixing the web scraper when it breaks, experimenting with new ideas, and generally being excellent people.

- **[Nissi](https://twitter.com/xxbanner)** (The whole site was driven by her experiences advising students! She also guided the user experience along the way and made the resources page.)
- **[Carey Metcalfe](https://github.com/pR0Ps)** (Many chats along the way, numerous internal improvements, tabbed homepage, scraper optimizations, textbook and exam links)
- **[Phil Schleihauf](https://github.com/uniphil)** (Cool term filters, documentation, code quality)
- **Christine P’ng** (Logo design and personal support!)
- **[Michael Layzell](https://github.com/mystor)** (Scraper updates, [new.qcumber.ca](http://new.qcumber.ca), really cool [prerequisite charts](/static/images/posts/qcumber/prerequisite-graph.png))
- **[Graham McGregor](https://github.com/Graham42)** (Continuing updates to data and scraper)
- **[Jamie Macdonald](https://github.com/jameh)** (SSL fix)

Thanks also go to everyone at the [Queen's Hack Nights](https://github.com/Queens-Hacks) group, for the great collaborative environment and fun work sessions.

Appendix - History
------------------

The site itself launched in December of 2012, but it had a long journey to get there. The idea of making a simple, friendly course catalogue to help students create their timetables actually came to a good friend Nissi during 2010, in the summer. This was during the time of [QCARD](/static/images/posts/qcumber/qcard.jpg) (and the Arts and Sciences [calendar website](/static/images/posts/qcumber/arts-science-calendar.png)).

While QCARD was a very... idiosyncratic application ("sleeping" from evening to morning to process requests was an endearing but inconvenient feature), the Arts and Science calendar provided easy and open access to course descriptions and prerequisites (no timeslots, however).

On March 4th, 2011, SOLUS became the official online registration system for Queen’s, as well as the only way to access up-to-date course information. I won't list out every deficiency of the system, but I *will* say that I regard it as a frustrating, tedious, and inconsistemt system, closed to anyone without a current Queen’s student number. (It also arrived for the price of [$35 million](http://queensjournal.ca/story/2012-01-20/news/quasr-gets-boost/), along with HR and financial software.)

At this point, I was more eager to build my own site than to use SOLUS to pick even 10 courses for the coming year. Finally I went back to developing the idea Nissi and I had spoken about the previous summer.

After a month or more of learning about hosting, Twitter Bootstrap, the box model, sass, less, Django, webmaster tools, and analytics, I finally made switched the site live on December 14th, 2012. The minutes and hours after launch were astonishingly exhilarating, and I could barely tear my eyes from the real-time analytics page.

After the launch frenzy had settled a bit, Phil joined in and began creating documentation to make the project more accessible to newcomers. Carey also began making modifications to the layout and other aspects. This continued for a number of months, and as I have stepped back from such an active role in the project, others have jumped in and started contributing and, in the last few months, even managing the live site.

I'm uncertain what the future will hold for Qcumber. There are a number of efforts under way to stabilize the project and make updates more regular, and also to add features to the site, but since it is primarily driven by spurts of inspiration on the part of the developers, these are 

Reflections
-----------

-being more strict with deployment
-focusing more on automation of scraping (memory restrictions were an issue early on, but not later)

I wish I had been more strict with the mechanics of deployment. Since this was the first time I've run a site, I j

