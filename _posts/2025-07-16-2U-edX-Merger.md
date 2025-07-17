---
title: "The 2U/edX Acquisition: A Retrospective"
date: 2025-07-21
categories: [Writing, Blogs]
tags: [writing, business, blogs, open_source]
description: "A retrospective on the 2U/edX Acquisition from a developer's perspective."
image:
  path: /assets/img/posts/2u-edx.png
  alt: The 2U logo, a plus sign, and the edX logo, showing the merger/acquisition.
  caption:
---

Back in 2021, I had the opportunity to write [a blog post][Original] about the upcoming acquisition of 2U from OpenCraft's perspective. It's been about four years on, and I wanted to revisit the topic. Unfortunately, our SEO strategy has changed and the fears of the acquisition are no longer salient, so there's been no impetus for me to write a follow-up.

However, some stories need to be told. Events like these are rare and heated in the Open Source community. So, I've decided to write this on my own blog. Of course, it comes with a standard disclaimer: These are the views of me personally. They are not the views of [OpenCraft], [2U], [Axim Collaborative][Axim], or anyone else in the Open edX™[^1] Community.

My viewpoint is one of a contractor and member of the Open edX community who has been making his living selling contracts for Open edX Development and also developing extensions for the platform. My role at [OpenCraft] has historically been a blend of sales and software development, giving me a unique perspective. I'll primarily focus on the impact to the open source projects that comprise the Open edX platform and the surrounding community, but some review of business impact will bring context here as well.

## Predictions at the Time

Back when the acquisition was starting, there was a lot of concern. People worried about the Open edX platform-- that it would either be hollowed out, neglected, or otherwise rail-roaded into 2U's specific use cases.

This went hand-in-hand with the fear that Open edX development would not be able to effectively transition from being lead by edX to a community-driven model. Historically, development had been greatly centralized around edX, which did not always prioritize community contributions. You can read more about this in [the first article][Original].

These fears were not unfounded-- edX was going from a non-profit entity to a for-profit enterprise, and some of the best developer, product, and marketing talent in the community along with it. They weren't my predictions, however. I thought that the Open edX platform would improve tremendously. The founding of [Axim] meant there'd be a dedicated organization that would be focusing on the platform itself, not just its utility as part of a single organization's business strategy.

I predicted that the acquisition would result in better collaboration around the platform, more product focus, and overall positive results.

2U was betting that the acquisition would allow them to unify efforts from a technology perspective, offer more competitive instructional design and marketing support to their clients, and improve their content portfolio tremendously. You can read more about their pitch in [this press release](https://press.edx.org/2u-inc.-and-edx-to-join-together-in-industry-redefining-combination) at the time of the acquisition.

So what actually happened? It turns out most of my predictions were correct, and most of the fears were not-- but how we got there was a roller coaster of a ride with twists and turns I had not expected. First, we need to get an overview of what happened to 2U.

## The Fall and Restructuring of 2U

![Image of stock chart over time of 2U, with markers showing specific dates, described in a table at the end of this section.](/assets/img/posts/2u-stock-chart.png "Source: Yahoo Finance.")

|Number| Date |Event|~Share Price|
|------|------|
|1|March 2020|COVID-19 Pandemic results in social upheaval, lockdowns.|$680|
|2|End of June 2021|2U Announces purchase of edX|$1325|
|3|March 2022|Fed ends zero interest rate policy, beginning rate increases|$350|
|4|August 2023|Apex of interest rate increases. The Fed holds at 5.33%|$100|
|5|January 2024|2U Abdicates maintainership of several repositories|$30|
|6|End of July 2024|2U Declares bankruptcy, undergoes restructuring|$3|
|7|Sept 2024|Restructuring completes, leaving 2U a private entity|last seen at $0.27|

When the COVID-19 pandemic of 2020 hit, 2U was bolstered by sudden opportunity. The lockdowns of the covid pandemic resulted in layoffs so enormous that [COBOL-based government unemployment systems cratered](https://www.theverge.com/2020/4/14/21219561/coronavirus-pandemic-unemployment-systems-cobol-legacy-software-infrastructure) under the crushing demand. In a month's time, [22 million people found themselves unemployed](https://www.bls.gov/opub/mlr/2021/article/covid-19-ends-longest-employment-expansion-in-ces-history.htm).

Stuck at home without a job, a sudden influx of demand arrived to online education platforms and services. Universities who had neglected digitizing were caught with their pants down, making 2U's value proposition as a higher-education digital transformation company glimmer.

Up until this point, 2U had been riding a rocky road downward. Their strategy of spending about [four thousand dollars in marketing](https://www.classcentral.com/report/2u-edx-acquisition-analysis/) for every student enrolled had caused the market to balk, dropping their stock price back in 2019 precipitously. The Online Program Management sector in general had been losing steam as demand for online degrees waned, with criticisms rising[^2]. 2U's offerings, which were as expensive as on-campus degrees, held questionable value propositions.

This sudden change thrust upon society was an opportunity-- now everyone was looking to go back to school, and the only way to do so was online. Riding high on the increased valuation, 2U could acquire the excellent material, contracts, talent, and branding that edX had built, and leverage that to reduce marketing and technological costs in the long run while increasing enrollment. If there was ever an opportunity, it was now. That was the idea.

The market didn't buy it. Immediately after the announcement, shares plummeted. Investors did not see a compelling narrative on how purchasing edX would increase the value of the company-- especially at the price tag of 800 million dollars. It was a tall mountain of debt to climb. But the good news was that with clever financing, they could manage this in a zero interest rate environment.

![Graph of the Federal Funds Effective rate over the last few years, showing its nosebleed rise.](/assets/img/posts/fed-funds-rate.png "Source: Federal Reserve Bank of St. Louis")

But then the Federal Reserve clamped the money hose. [Inflation had raged](https://www.usinflationcalculator.com/inflation/current-inflation-rates/) after the pandemic stimulus spending, up to 9.1% according to the Consumer Price Index. The Fed increased the [Federal Funds Effective Rate](https://fred.stlouisfed.org/series/FEDFUNDS) to a dramatic degree. For more than a decade, the federal reserve had kept interest rates low-- nearly to zero for most of that time, only starting to increase the rate at the beginning of 2015 to a height of about ~2.5 in 2020, when it slashed them right back down in the face of the pandemic.

The market thought that the Fed didn't have the stomach to raise rates significantly. Up until this point, inflation had been under control. The sudden increase in rates was a punch right to the solar plexus of 2U's financial viability when it was already staggering.

2U had to cut expenses. They were throwing talent overboard their sinking ship, hoping to stem the bleeding. It wasn't enough, and the skeleton crews struggled to keep up with the remaining work. Finally, in July of 2024, [2U declared bankruptcy](https://www.insidehighered.com/news/business/2024/07/26/long-embattled-2u-declares-bankruptcy). The acquisition of edX had proven a critical mistake.

After a few months of negotiations, 2U was delisted and was reclaimed as a private company, its creditors taking ownership. However, 2U, and thus edX, survives as a company, even if it is no longer a public one. Those I've spoken to within the company note that they've had to stay scrappy, but that they are finally seeing a light at the end of the tunnel after all the restructuring work. 2U's story is not over, though it remains to be seen if it ever regains the size it once had.

## The View and Impact from the Sidelines

At the time this was all happening, I wasn't paying attention to their stock price, or really focusing on 2U's viability as a company. But I was hearing of the layoffs. At first, I didn't think too much of them-- layoffs are common after acquisitions. Companies start cutting to lean out, consolidate, and improve fundamentals.

But the layoffs kept coming; the talent drops more surprising. Excellence was exiting. Eventually, one of the best engineers I'd ever met was cut-- someone fundamental in guiding the platform's development (and its community) from the early days. Someone who had mentored so many in the community and had always been a pleasure to work with. The news flipped my perspective instantly. Now I **knew** something was wrong. That's when I started looking at the charts and realizing just how bad it had gotten.

![A brick wall, vandalized with stencil lettering which reads, "Until Debt Tear Us Apart"](/assets/img/posts/ehud-neuhaus-debt-unsplash.jpg "Courtesy Ehud Neuhaus via Unsplash")

[OpenCraft] is a contractor providing services around the Open edX platform. Our projects with edX had been halted right before the acquisition and never picked back up. The Open edX community is much larger than edX-- we had other things to keep us busy. I occasionally checked in with my 2U contacts, but I hadn't been focusing on the company's viability until then. Very shortly afterward, we all had to.

In January of 2024, edX announced that they did not have the manpower to continue maintaining several of the repositories in the Open edX project. Suddenly, there was a ravenous need for community members to take stewardship of code that had been managed by edX since its inception, and the number of these new vacancies was enough that no one organization in the community could step up and fill them all.

In a brief instant, the Open edX Platform lost its largest point of centralization. Core Contributors stood up to take on these repositories from organizations across the Open edX landscape. While an incredible challenge, it's one of the moments where I found myself most proud of the community. The Core Contributors are a feather in the cap of the Open edX project.

In June of 2021, there were 14 [Core Contributors](https://docs.openedx.org/en/open-release-quince.master/developers/references/legacy_guide/process/core-contributors.html) inducted by edX to assist in the maintenance of the Open edX Platform and its community. Today there are 79[^3]. This level of distribution of community power and responsibility makes the platform stronger. It continues to grow.

This was not how we wanted it to happen. The team at edX brought skills, leadership, and guidance to the community. However, for years, edX had been reticent to give others commit access to their repositories. The CC program had started just before the acquisition, and it stayed small. In my view, it was more a concession that the project had gotten too large for one company to manage than a forward-thinking move. The hollowing out of the company-- the sudden loss of their ability to hold tight, was not what the community wanted to be the impetus for this change.

Since then, however, the ability for other companies to gain commit access-- to join the program and have real say in how the platform develops, has encouraged companies to focus more on upstreaming. Knowing that their pull requests won't be deprioritized due to the conflicting priorities of a single party has done wonders for flywheel that is open source collaboration.

My impression is that in recent years, especially with the reduction in force, 2U has focused more of their development effort on community solutions. They have been more willing to listen and to participate because they no longer have the luxury of ignoring the community momentum. Features like Discovery and Enterprise, which existed to serve edX's narrow needs and were made with little community consult, are targeted for deprecation[^4][^5] in favor of community designed replacement features.

## The rise of Axim and its Leadership

One of the big questions when the acquisition happened was 'What would happen to the $800 million paid by 2U?' The answer was that a new non-profit would be created with a complementary mission to the old one. This new organization, Axim, was staffed by some of the best and most community-oriented team members and engineers from edX's open source team. These were people who were already leaders in the community-- resulting in a continuity that the community could immediately get behind.

With the massive endowment, this new organization could focus on what it wanted to without having to worry about keeping the lights on-- something edX always had to worry about. Finally, community-oriented leaders could serve that community without worrying about the next quarter's finances. I was quite hopeful. My hopes were not in vain.

A year or so ago, I did a talk on [the differences between the big open source learning management systems](https://youtu.be/LoL9-DHqR24?si=CMQ6bzbRZs3Tr_eN&t=3662). I specifically looked at their evolutionary history and noted that the Open edX platform has not been viewed by its creators as a product. Rather, it had been a tool to accomplish edX's business goals. The team at edX was staffed by team members at MIT and Harvard who had a large staff of technical people to maintain it and so a lot of UX ergonomics were left by the wayside, and functionality that wasn't in service of their business model wasn't prioritized.

![A slide showing key competitive differences between the different Open Source LMS platforms, emphasizing how Canvas and Moodle excell at Blended learning, Open edX has a wide dev community but difficulties with installation, and how you don't want to run a MOOC with Moodle if you can avoid it.](/assets/img/posts/competitive-comparison-slide.png "A slide from my talk.")

Now, however, there was an organization that could rally around improving the platform as a product. And boy, have they. Take a look at the release notes of [Koa](https://docs.openedx.org/en/latest/community/release_notes/koa.html) and [Lilac](https://docs.openedx.org/en/latest/community/release_notes/lilac.html), the last two releases before the acquisition. Now look at the release notes of [Teak](https://docs.openedx.org/en/latest/community/release_notes/teak.html) and [Sumac](https://docs.openedx.org/en/latest/community/release_notes/sumac.html), the last two releases. The differences are stark-- Teak and Sumac are far more exciting improvements to Open edX **as a product**. The new releases push out new features and massive improvements over old ones. The older ones are primarily small incremental improvements.

Axim's courting of *Mission-Aligned Organizations*, such as [Western Governors University](https://openedx.org/blog/the-open-edx-project-and-western-governors-university/), has pumped fresh blood into the veins of the community. Funding, talent, and vision are rushing into Open edX in a way not seen since its early days. It's exciting to be working on the platform today in a way it has not been for a long time.

There are criticisms that can be levied-- some processes introduced, such as the product proposal process, have been overbearing for small changes. The fact that Axim is not directly exposed to market forces means that the discipline of the market doesn't directly influence their decisions. However, Axim has been excellent at taking feedback. The last Open edX conference had focused workshops on resolving process issues, and Axim takes consult from companies which are directly exposed to the market, allowing them to still learn the lessons it reveals.

The Open edX community is privileged to have Axim's team at the helm. I have been continually impressed with their leadership and drive in a world where effective leadership is an ever-scarce resource. Their handling of the maintainership crisis was so smooth that I doubt anyone outside the developer community noticed anything at all.

## Lessons Learned

There are some important lessons to be learned here. A few of these can easily generalize to other projects, and others are a bit harder to generalize but are helpful to keep in mind.

### Product Vision is Critical

We lost a great deal of talent in the community in the wake of the acquisition. Some left at the beginning because they felt it was a good time for a change, some felt the mission of 2U wasn't what they signed up for at edX, and many more were laid off over the next few years. As developers, we look up to the most talented among us. Their talents matter, and they lead us through difficult challenges.

However, talent isn't enough. A strong vision of what the project is and should be is critical to direct that talent towards its productive ends. Excellent engineers keep this in view, but there is no substitute for dedicated product focus. This gives talent its full impact. The UI/UX and product teams in the community have been critical in this new chapter of the project.

![A screenshot from the new 'In-context metrics' feature delivered by OpenCraft and funded by Axim. Here, we can see the sidebar extended in the studio, showing off metrics of how the learners are interacting with content.](/assets/img/posts/in-context-sidebar.png "The ability to see metrics on your content right alongside it in the studio is a major improvement to the authoring experience.")

Even after the exodus, there was plenty of excellence left in the developer community. Top tier developers still believed in the project and had continued employment. Much more got done despite the reduction in force. It really does come down to alignment. Left to our own devices, developers will do things like optimizations and refactors. These are important, but without product vision, what do those refactors buy us? The freedom to do the same thing we were always doing, slightly faster? These improvements should pave the way to building a better product.

### When Contributions are Welcomed and Rewarded, We Get More of Them

This might seem obvious, but like any mindful practice, it's easy to get stuck in our own narrow channel and forget to show gratitude and encouragement to those looking to contribute. The difficulties with edX leading the Open Source project surrounded how they handled contributions not precisely aligned with their goals. That makes perfect sense in the moment-- edX's engineering team had important business priorities and this was time spent that could have been spent on their own goals.

Yet, neglecting contributions discourages future contributions. If you know your pull request will languish for months or years, why make it? The Core Contributor program has been an excellent solution to this problem-- and every open source project should be considering how they induct key personnel from the community with powers and responsibilities. By ensuring there's continued incentive to review pull requests, and that there's privileges and rewards for continued quality contributions, you get more participation and more leverage from your community.

![Several hands laying on the trunk of a tree, symbolizing unified purpose.](/assets/img/posts/hands-on-tree.jpg "Courtesy Shane Rounce via Unsplash")

When the critical need for maintainers arrived, we already had an A-list of Core Contributors ready to start taking charge, and the program was ready and defined-- able to take new inductees to fill the need. I shudder to think how this would have gone if none of the groundwork had already been completed. So if you're putting off creating a Core Contribution program for your project, don't wait any longer!

Sometimes, the best thing you can do is loosen your grip. If you've built an incredible community, give them the power and the incentives to keep improving things. Holding cards close to your chest may make conventional business sense, but when your business is surrounding an open source project, it hobbles your momentum.

### The Members of a Community Ebb and Flow

We lost many people, but we have gained more. It is the natural cycle of an open source project that contributors move on, and new ones arrive. Although we lost some incredible people, no one, no matter how talented and capable, will break a strong community with their departure. If they do, the community was not strong to begin with. The Open edX community has proven resilient.

As a delightful surprise, many who we lost returned. Some started their own consulting companies around the platform, some got rehired through other organizations within the community. Goodbye isn't necessarily goodbye forever.

### Having a Well-Funded Governance Organization Staffed with True Believers is Awesome If You Can Get It.

This one's a bit harder to generalize. It's a rare event that an Open Source project is backed by a post-economic[^6] non-profit organization, let alone one comprised of true believers in the project and its community. Most open source projects would need to find some kind of sponsorship model to continue their work, or sell adjunct services. But if an open source project is to continue to improve, it needs leadership that can tackle it at the product level, and who believes in the open source model.

Axim's overall goals are [larger than the platform][Axim], however they do recognize it as a critical tool: The more they can get it in the hands of people who will deploy it to help their communities, the better their reach can be. That view-- which focuses on how the product fits within a larger narrative, and the know-how to guide it there, are what make this an excellent one-two punch.

## What's Next

The more I learn about the challenges life brings, the more I am convinced that community strength is the deciding factor when adversity arrives. Strong communities bring up strong leaders who are invested in their success. The Open edX community has proved its resilience through trial after trial, and I expect more and continued great things.

I don't know everything the future brings, but I do know that the Open edX Platform will continue to improve, and I believe it's one of the best open source projects any developer could have the privilege to work on. If this is something you'd like to be a part of, please swing by the [forums](https://discuss.openedx.org/), [check out the Slack](https://openedx.org/slack), browse the [issues list](https://github.com/openedx/edx-platform/issues) or comment on the [next product proposal](https://openedx.atlassian.net/wiki/spaces/OEPM/pages/4348968964/Proposed). If you're new to open source contributions, check out the [Open Source Masterclass](https://opensourcemasterclass.org/). The Open edX Community, and Open Source at large, will be better with you in it.

![A fist raised in the air, surrounded by the words "Long Live FLOSS".](/assets/img/posts/long-live-floss.svg "A graphic from the Open Source Master Class, linked above.")

[Original]: https://opencraft.com/the-2u-edx-acquisition-opencrafts-take/
[OpenCraft]: https://opencraft.com/
[Axim]: https://www.axim.org
[2U]: https://2u.com

[^1]: Open edX is a registered trademark of edX LLC. All Rights Reserved.
[^2]: Criticisms mostly surrounded 2U making money off of non-dischargeable student loans, profiting off of students going deep into debt. While this is a legitimate criticism, it is applicable to nearly every higher education institution in the United States, who should not get a pass by virtue of their incumbency. The fact that they were charging as much for a degree despite the fact they had no campus facilities is the better criticism. However, since these degree programs are sponsored and accredited by the universities that brand them, it is not clear to me how much of the price is 2U's doing and how much is those Universities worrying about cannibalizing their on-campus offering. If I remember, 2U would also argue that more intense and personal ancillary guidance/counseling services than are provided via traditional college educations. I cannot comment on the veracity of this.
[^3]: A [listing of all Core Contributors](https://openedx.atlassian.net/wiki/spaces/COMM/pages/3156344833/Core+Contributors+to+the+Open+edX+Project), current and historical, is available. I have not included the Core Contributors listed from 2U in my count here, as this would overstate my point. Of note, however, is that the Core Contributors from 2U are outnumbered by contributors outside of it, 79 to 75, and the gap is widening. CCs from 2U meet the same standards as other CCs as set forth by [OEP-54](https://docs.openedx.org/projects/openedx-proposals/en/latest/processes/oep-0054-core-contributors.html).
[^4]: [Course Discovery Deprecation Ticket](https://github.com/openedx/course-discovery/issues/4449)
[^5]: There is not currently a ticket for Enterprise's deprecation. However, there is momentum to replace its most critical functionalities with well-designed replacement features, such as [this proposal for learning paths](https://openedx.atlassian.net/wiki/spaces/OEPM/pages/5105483785/Proposed+Learning+Paths+by+OpenCraft), and talk of one day removing it has come up at every conference of the last few years.
[^6]: Taken to mean 'does not require continuing business model revenue to operate' rather than 'the rules of economics no longer apply.' I'm sure Axim could overhire and provision a ton of servers in AWS and blow through it all if they really wanted to.
