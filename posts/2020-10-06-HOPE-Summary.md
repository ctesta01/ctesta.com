---
title: "HOPE 2020"
author: "Christian Testa"
date: "2018-11-23"
filters:
   - lightbox
lightbox: auto
categories: [technology, conferences]
---

[HOPE 2020](https://www.hope.net/) took place July 25th through August 2nd and for the 
first time ever was all-online due to the COVID-19 pandemic. I've written up 
this summary of my seven favorite talks with some links to read more about their 
content matter. 

<!--more-->

Table of Contents: 
- <a href="#foia">75,000 FOIA Requests Can’t be Wrong</a>
- <a href="#dirt">Free As In Dirt: In Pursuit of Truly Open Source Physical Objects</a>
- <a href="#libraries">Librarians and Crisis Response: The Case of COVID-19 Maker Response</a>
- <a href="#elections">The Election System - Can We Fix It? Yes, We Can!</a>
- <a href="#ring">One Ring to Rule Them All</a>
- <a href="#solarpunk">Solarpunk, Cyberpunk, and Popculture</a>
- <a href="#lanier">Keynote by Jaron Lanier</a>

<div id='foia'>
<h2>75,000 FOIA Requests Can’t be Wrong</h2>
</div>


Michael Morisy founded MuckRock to help requesters file FOIA requests.  He said
he described their service as “like TurboTax for FOIA requests, until we
realized everyone hates TurboTax.”

[![Screenshot of MuckRock website](/assets/img/2020-10-6/muckrock-screenshot.png)](https://www.muckrock.com/)


What started out as an attempt to get public records out of the Somerville,
Massachusetts local government turned into the realization that with enough
sustained effort through FOIA requests, the public could pressure the
government into being more transparent, often even proactively so. After over a
decade of automating the process for submitting FOIA requests, they've
unearthed some pretty interesting stuff.

Check out some of their most interesting work:

- [Unearthing CREST: CIA's Declassified Archives](https://www.muckrock.com/project/unearthing-crest-cias-declassified-archives-100/)
- [Police Surveillance: Facial Recognition Use in Your Backyard](https://www.muckrock.com/project/police-surveillance-facial-recognition-use-in-your-backyard-452/)

Along the way, MuckRock and FOIA Machine have created the online open-source
DocumentCloud service which is now one of the industry standard online  document
hosting services with analysis, annotation, and publishing  capabilities.
DocumentCloud is used at places like the NY Times, ProPublica, PBS, The
Guardian, and others.  DocumentCloud runs every document you upload through
Thomson Reuters OpenCalais, giving you access to extensive information about the
people, places and organizations mentioned in each.

Links:
- <https://www.muckrock.com/>
- <https://www.foiamachine.org/>
- <https://www.documentcloud.org/>
- [Atlas of Surveillance: Documenting Police Tech in Our Communities](https://atlasofsurveillance.org/)

[Link to Talk](https://archive.org/details/hopeconf2020/20200725_1400_75%2C000_FOIA_Requests_Can't_Be_Wrong.mp4)

<div id='dirt'>
<h2>Free As In Dirt: In Pursuit of Truly Open Source Physical Objects</h2>
</div>

![Title slide for Free As In Dirt by Dominic Muren](/assets/img/2020-10-6/free-as-in-dirt-title.png)

3D printers and CNC machines have revolutionized who has access to the ability
to custom part making capabilities, but it still requires financial investment
and access to global supply chains for parts and materials. Further, even
since the advent of these technologies, globalized supply chains are, if anything,
stronger than ever.  

One key reason for this is that though these machines print with digital
instructions which can be easily copied and sent, the materials they use is
specialized, and therefore usually centrally produced. Another is that many of
these materials are mined, or harvested in a mining-like way, so centralized
production is most cost-effective.

This talk presented an alternative technological development path: one where
materials are sourced entirely from constituents of living ecologies - plants,
animals, microbes, and the materials they produce. Starting with historical
examples of ecology-derived material production, Dominic presented a
catalogue of possible materials for experimentation. Then, using examples drawn
from the maker community and from his own work, he showed how this method of
production has the potential to make objects with functional properties across
the entire spectrum of complexity - even including simple electronics. The talk
emphasized the importance of pursuing manufacturing systems with societal and
ecological advantages as well as resilience.

![the challenge, how to reimagine manufacturing so that every object
made reinforces healthy ecologies where humans co-habitate](/assets/img/2020-10-6/free-as-in-dirt-challenge.png)

Motivating principle:  While vegetarians and vegans are well known for arguing
that we should prioritize eating foods which are closer to the bottom of the
food chain to be more sustainable, where is the physical materials analogue  of
this philosophy?  Such a philosophy could emphasize consuming materials  which
have low atomic numbers.

Unfortunately the materials which humanity is  so hungry for (gold, rare earth
minerals, [coltan](https://en.wikipedia.org/wiki/Coltan), etc.) are high in
atomic number and are primarily extracted from the environment via
environmentally devastating mining projects.  Moreover, our hunger for metals
like coltan which is used in transistors has had disastrous impacts on humanity
including financing conflict in the Democratic Republic of Congo.

With coltan and other rare earth minerals being principle ingredients in
silicon chip based electronics, it seems unlikely that even with recycling and
a reduction in humanity's rapacious desire for these minerals that  we could
ever get to 0 consumption soon.  However, a hypothetical alternative to mining
does exist that deserves investigation:
[phytoremediation](https://en.wikipedia.org/wiki/Phytoremediation).

Shocking as it may seem, there exist plants that are still being discovered
which naturally accumulate metals from the soil in which they grow.  The
New Caledonian tree Pycnandra acuminata accumulates 20-25% nickel in the
latex it produces, and as a result the tree even appears to bleed blue-green.

<center>
<img alt="The famous blue‐green latex of Pycnandra acuminata that instigated the global search for hyperaccumulator plants over the past four decades." src="/assets/img/2020-10-6/free-as-in-dirt-phytoaccumulator.jpg" style="align: center; height:500px;" >
</center>

<span class="image-credit"> Photo Credit: <a href="https://nph.onlinelibrary.wiley.com/doi/10.1111/nph.15105">The discovery of nickel hyperaccumulation in the New Caledonian tree Pycnandra acuminata 40 years on: an introduction to a Virtual Issue</a></span>

Perhaps combined with the advancement of a global environmentalist agenda, these
phytoaccumulators could provide an alternative to the mining which has been
both negatively impacting political stability and the environment.

It's not just phytoremediation that offers a glimpse into an alternative,
ecologically friendly reality that we could create: there are technologies such
as those used at WholeTrees.com which are already being implemented in practice
that dramatically reduce the need for lumber in construction projects.
WholeTrees.com provides mechanical and structural engineers with an interface
to specify their exact dimensional and structural needs and their software
matches them with trees whose structure already matches their needs.  

[![Pavillions constructed from trees supplied through WholeTrees.com, showing off how 
purpose-chosen trees can suit the architectural and structural needs of a given situation 
exactly](/assets/img/2020-10-6/free-as-in-dirt-whole-trees.png)](http://wholetrees.com)

Trees aren't the only green construction material that poses great potential
for upending our wasteful, toxic modern practices: [This Is
Grown](https://www.jenkeane.com/this-is-grown) is a project started by designer
and researcher Jen Keane to develop fabrication techniques that make use of *k.
rhaeticus* bacteria to perform 'microbial weaving' with cellulose. The bacteria
produce a material that is both strong and lightweight with little to no
wastage.

[![a show grown from cellulose](/assets/img/2020-10-6/free-as-in-dirt-this-is-grown-cellulose-shoe.webp)](https://www.jenkeane.com/this-is-grown)
<span class="image-credit"><a href="https://www.jenkeane.com/this-is-grown">
Photo Credit: Jen Keane – This is Grown</a></span>

Other environmentally friendly efforts are even more custom-fit:  [Row7
Seeds](https://www.row7seeds.com/) is a company breeding fruits and vegetables
exactly suited to consumer needs, whether it's growing single-serving size
vegetables to reduce restaurant waste or creating crops which are catered specifically to
the growing environments in a single farm.  They were recently featured in
a New York Times op-ed, [Save Our Food. Free The Seed.](https://www.nytimes.com/interactive/2019/06/07/opinion/sunday/dan-barber-seed-companies.html) 
I'm happy that Row7 Seeds exists as an alternative model for agriculture that
someday could pull us away from the grip of Monsanto.

[![screenshot of the row7 website](/assets/img/2020-10-6/free-as-in-dirt-row7.png)](https://www.row7seeds.com/)

Newly developed environmentally friendly business practices don't just stop at
purpose-bred seeds and purpose-fit trees: an entire community has cropped up
around the idea of [Open Source Ecology](https://www.opensourceecology.org/).
They even have a [Wiki](https://wiki.opensourceecology.org/wiki/Main_Page). 
Open Source Ecology provides all of the information and schematics one needs to
start building and promoting high-performance, modular, do-it-yourself,
low-cost, sustainable civilization and the machinery necessary for it.

See also:

- [The Land Institute](https://landinstitute.org/) who are working to disrupt
  our currently monoculture-based agriculture with polycultures and perennial
  crop based  agricultures.
- [The Block Research Group at ETH Zürich](https://block.arch.ethz.ch/) who are
  working to develop new construction techniques which  are more efficient,
  economical, and expressive with the aim to draw inspiration from our
  architectural heritage and reduce greenhouse gas emissions. Read their
  paper ["Redefining Structural Art: strategies, necessities and opportunities"](https://block.arch.ethz.ch/brg/files/BLOCK_2020_Structural-Engineer_Redefining-structural-art_1578310555.pdf) for an introduction to their working philosophy.
- [Teachable Sorter](https://coral.ai/projects/teachable-sorter) - a cheap,
  Raspberry Pi powered teachable sorter that enables low-budget projects
  to make use of machine-learning and computer-vision powered sorting.
- [Dominic Murien's homepage](http://www.dominicmuren.com/p/home.html)
- [Dominic Murien's TED Fellows feature: Break it down and make it](https://blog.ted.com/break-it-down-and-make-it-fellows-friday-with-dominic-muren/)

[Link to Talk](https://archive.org/details/hopeconf2020/20200725_2100_Free_as_in_Dirt.mp4)

<div id="libraries">
<h2>Librarians and Crisis Response: The Case of COVID-19 Maker Response</h2>
</div>

From the talk description directly:

> On Thursday, March 19, 2020, Dr. Pierre Elias, a Columbia University cardiology
> fellow, reached out to Research and Learning Technologies librarian Madiha
> Choksi to utilize the Columbia University Libraries' 3D printers to produce
> supplemental face shields. Within a few days, she had optimized an existing
> design for face shields, taken two 3D printers from Butler Library to her
> apartment, and was printing parts and assembling shields. A few days later, she
> was joined by her fellow librarians, Alex Gil and Moacir P. de Sá Pereira. Two
> months later this team of librarians had organized one of the largest PPE
> grassroots efforts in the city, COVID Maker Response, which effectively produced
> and distributed more than 25,000 face shields to New York City hospitals and
> other front line institutions during the height of the city's pandemic crisis.

[![Columbia Studio Libraries website screenshot](/assets/img/2020-10-6/columbia-studio-libraries.png)](https://studio.cul.columbia.edu/)

The [Columbia University Libraries Studio](https://studio.cul.columbia.edu/)
has been engaged in disaster response efforts for years now, not only
with their most recent COVID-19 response efforts, but also through their
[Nimble Tents Toolkit](https://nimbletents.github.io/) which provides
research and documentation to help teams organize and address urgent challenges.

The work Columbia University Libraries Studio has been doing in response to 
COVID-19 has undoubtedly made a great impact, but I think I'd like to focus here
on what I learned about how they've been able to translate their learned knowledge
into guidance and resources for others working in urgent crisis response situations
through the Nimble Tents Toolkit.

[![Nimble Tents Toolkit website screenshot](/assets/img/2020-10-6/nimble-tents-toolkit.png)](https://nimbletents.github.io/)

The Nimble Tents Toolkit coordinated a mapathon immediately after Hurricane
Maria in 2018 to document the damage experienced during Hurricane Maria enabling
crisis responders to target their response efforts efficiently and effectively.
Such mapathons are now more commonplace and facilitated by [MissingMaps.org](https://www.missingmaps.org/), an organization that uses OpenStreetMaps to document
the most vulnerable places in the world, so that international and local
organizations can use the maps and data to better respond to crises.

The Nimble Tents Toolkit also provides direction on how to conduct
[Rapid Response Research (RRR)](https://nimbletents.github.io/rapidresponse/).
Their guidelines not only discuss the practicalities of how to conduct
RRR but also how to promote the findings through open access web-based
communications, how to use [Nimble Data Management](https://nimbletents.github.io/rapidresponse/datamanagement/) practices to make data and models most
effective once publicly released, how to prepare for media and publication
releases, and how to deal with some of the hidden costs of RRR.

The Nimble Tents Toolkit also pays special attention to [how to develop
Flash Subject Guides](https://nimbletents.github.io/libguide/) that can serve to
quickly bring researchers and  activists onboard when a crisis requires urgent
response.  Their guide not only discusses what content should be included,
but also how its maintenance can be best organized depending on your team,
best practices, how to ensure accessibility, and a
[catalogue of Flash Subject Guides](https://docs.google.com/spreadsheets/d/1SugkOYJDjMCQQN_GQ0wIce-2ab_9MLUKNTU1c_LtsT8/edit#gid=0).

Lastly, the Nimble Tents Project hosts a description of how the
Maryland Institute for Technology in the Humanities hosted a
[Night Against Hate](https://mith.umd.edu/research/night-against-hate/) social media event on October 13th, 2016 to
gather and learn how to investigate and work to resist hate speech
on social media. They partnered with the Southern Poverty Law
Center and made use of their [Extremist Files](https://www.splcenter.org/fighting-hate/extremist-files) which is a database documenting the profiles of prominent
extremists and extremist organizations. The [description on the Nimble Tents
Project website](https://nimbletents.github.io/nights/) describes the motivation,
foundations, methods, and post-event analysis that was conducted. One of the
primary products of the Night Against Hate is a CSV-formatted block list that
allows users to easily block known extremists and extremist organizations from
appearing on users' Twitter feeds.

See Also: [Online To Online, or O2O](https://o2ostrategy.org/trainings/),
provides online accessible training for anybody interested in learning
more about how to organize community action.

[Link to Talk](https://archive.org/details/hopeconf2020/20200726_1500_Librarians_and_Crisis_Response.mp4)

<div id='elections'>
<h2>The Election System - Can We Fix It? Yes, We Can!</h2>
</div>

[![screenshot of bia-sci-lab title slide](/assets/img/2020-10-6/bia-sci-lab.png)](https://biascilab.com/)

13 year old founder and CEO of [Girls Who Hack](https://girlswhohack.com/),
Bianca Lewis, or Bia, of [BiaSciLab](https://biascilab.com/) presented on the security
inadequacies  in our election system and how we can fix them.

Offering solutions which not only address current inadequacies (such as the
rampant potential for SQL injection and other forms of tampering in our
election reporting system), Bia promotes solutions which will prevent future
insecurity such as bug bounty programs, open source software and hardware, hand
marked paper ballots, encryption, and risk-limiting audits.

Bia is working on [Secure Open Vote](https://secureopenvote.com/), and
end-to-end election system built on modern, open source software and hardware.

[![screenshot of secure-open-vote website](/assets/img/2020-10-6/secure-open-vote.png)](https://secureopenvote.com/)

Shown below, Bia has recently presented her work at the U.S. Congressional Hearing on Election Security and at security conferences all over the world.

![bia standing with the election security commission](/assets/img/2020-10-6/bia-at-election-security-commission.png)

See also: [the Securing America's Federal Elections or S.A.F.E. Act](https://www.congress.gov/bill/116th-congress/house-bill/2722)

[Link to Talk](https://archive.org/details/hopeconf2020/20200726_1700_The_Election_System.mp4)

<div id="ring">
<h2>One Ring to Rule Them All</h2>
</div>

[![Figure 1 from Calacci's extended abstract: county density map of 
ring cameras per capita in the 48 states](/assets/img/2020-10-6/county-density-map-of-ring-cameras.png)](https://www.dcalacci.net/images/extended-abstract.pdf)

<span class='image-credit'>Dan Calacci, Figure 1: County density map of Ring
cameras that posted to the Ring Neighbors app since 2017</span>


Dan Calacci from the MIT Media Lab is turning Amazon Ring's surveillance
in on itself. Using the Ring Neighbors app, Calacci has aggregated data not
only on where Ring has the strongest presence and what kind of video footage it
has been collecting, but also how users interact with that footage, annotating
it and reporting it as containing "suspicious activity."

In one particular appalling example, Calacci showed us footage posted to a  forum
for Jamaica Plain residents (Jamaica Plain being just south of Boston,
Massachusetts) of what appear to be children roller-blading and playing in the
street. This video was shared on social media and posted by the owner of the
recording Ring device as an example of suspicious activity,  with the poster
exclaiming that it documented potential car-jacking activity (not at all
supported by the video).

Calacci went on to interrogate this idea of whether or not Amazon Ring's system is
actually documenting crime, and even if it is, to question the effect that
residents policing their neighbors could have.

In an [extended abstract submitted to the 6th International Conference on Computational Social Science](https://www.dcalacci.net/images/extended-abstract.pdf), Calacci documented the results of a spatial autoregressive lag model of the data he collected.
In this paper he finds that less expensive, middle-income neighborhoods
with comparatively low home values are more likely to use the Ring platform.
Surprisingly, theft was not significantly correlated with the number of Ring
cameras per county, but other crimes including robbery and motor vehicle
theft were.

[![figure 2 from calacci's paper: coefficients from the sarlm regression model](/assets/img/2020-10-6/ring-sarlm-coefficients.png)](https://www.dcalacci.net/images/extended-abstract.pdf)

<span class='image-credit'>Dan Calacci, Figure 2: Total
(direct + indirect) impact of county-level variables on number of active Ring
cameras,corrected for spatial autocorrelation and estimated using a spatial
simultaneous autoregressive model</span>

His work is featured in this recent Gizmodo article:
[Ring's hidden data let us map amazon's sprawling home surveillance network](https://gizmodo.com/ring-s-hidden-data-let-us-map-amazons-sprawling-home-su-1840312279).

In recent work, Calacci has been examining measures of how much more complicated
traveling through a given city like Boston would get if one wanted to completely
avoid potentially being recorded on a Ring camera.

[Link to Talk](https://archive.org/details/hopeconf2020/20200726_1900_One_Ring_to_Surveil_Them_All.mp4)

<div id='solarpunk'>
<h2>Solarpunk, Cyberpunk, and Popculture</h2>
</div>

![Solarpunk: A Promise, Not a Warning](/assets/img/2020-10-6/solarpunk-a-promise-not-a-warning.png)

<span class="image-credit"><a href="https://www.artstation.com/flagflagflagflag">
Art Credit: 白色风车 by Liuying J.P</a></span>


This talk explored the problematic themes and biases of modern popular
narratives around technology. As technology becomes more complex and sophisticated,
people more and more on stories about technology to understand the tech-world.
Unfortunately these stories are often produced by multi-national, well-marketed
corporations that have an incentive in furnishing their stories with
hidden product ads, lone genius-inventor legends, and cyberpunk visions of a
world with no privacy (but so much convenience)!

Sadly, cyberpunk is the default story when it comes to modern science fiction.
Our popular movies focus on technology as a means to create greater weapons,
and the characters cast as the heroes are all too often heroes simply because
they take the situation into their own hands.  Instead, it is possible to
imagine a version of sci-fi where democratizing technology allows the
public to prevent the consolidation and weaponization of technology. This is
part of what solarpunk is.

[Solarpunk](https://en.wikipedia.org/wiki/Solarpunk) emphasizes an optimistic
vision of the future where humankind works together with technology to address
environmental concerns such as climate change and pollution.

Solarpunk promotes the [Repair Manifesto](https://www.ifixit.com/Manifesto) as
a rejection of over-consumption.

[![the repair manifesto](/assets/img/2020-10-6/repair-manifesto.png)](https://www.ifixit.com/Manifesto)

Here's my favorite quote from the talk, referring to the Iron Man movies and how these
portrayals of technology contribute to the loss of our ability to ask about how
technology can be used for the whole of society:

> Hey Mr. Stark, why don't you create small energy generators for every hospital
> worldwide? In Syria they could really use it right now.

See Also: [solarpunks.net](https://solarpunks.net/) a neat blog about solarpunk
progress.

[Link to Talk](https://archive.org/details/hopeconf2020/20200727_1100_Solarpunk_Cyberpunk_and_Popculture+.mp4)


<div id="lanier">
<h2>Keynote by Jaron Lanier</h2>
</div>

This talk was primarily rhetorically and didactically driven,
so for brevity I've included an outline for anybody in a rush.

Outline:

- An increasingly common theme of current media is that people are afraid of
  being replaced:
  - This is because of the often perpetuated narrative that human laborers are
    like widgets or parts of a machine in the modern economy. 
    - This philosophy hasn't worked out very well for productivity and quality.
    - This kind of thinking has been successfully upended where human laborers have
      been given more agency in their roles as manufacturers.
      - See Deming and statistics' in role quality control.
  - So looking at more contemporary problems, shouldn't humans be given more agency in
    regards to AI and how their personal data is used?
    - This could be achieved through collective bargaining and responsibility.
      - This might help empower content producers as well as put a stop to
        the promotion of inflammatory media that engages our fight-or-flight
        response.
        - See unionization, Gareem Bank and solidarity lending.
  - What about addressing the fact that the AI as a black box continues to scare people?
    - Looking at it from its roots, the narrative that computer intelligence is
      separate from human intelligence is driven by our instincts to fear that
      which we don't understand as well as narcissism in viewing
      computer-scientists as some kind of god-like creators of new intelligence.
    - We should emphasize that the alternative is to view computer intelligence not as
      artificial intelligence, but as augmented/associative/aggregate
      intelligence.
      - Maybe if more people understood this perspective, they would be less
        scared of an AI-driven economic collapse.
      - See possible alternative data collection methods, like the Microsoft
        Trove which wants to pay people to license their data for use by
        researchers training computer models.

Lanier spoke about the increasingly common subtext in popular media that
humanity is being threatened by being replaced by technology.

Lanier argues that this narrative is fed to us constantly through social and
traditional media -- including examples of ostensibly optimistic news articles
describing how machine-learning algorithms can now outperform skilled experts,
such as doctors in identifying particular diseases like cancers.

First, to put this idea in context, let's trace its cultural origins. Much of
this notion of humanity being replaced by technology first took root with the
industrial revolution. The prevailing viewpoint was that human laborers on the 
factory lines were replaceable and they worked as if they were pre-specified
parts of a machine with no agency or autonomy.  However, this system had a
problem: it didn't work very well, because workers weren't invested in the
outcome of their work.

A new practice and philosophy in manufacturing soon disrupted this mentality,
and this came from [William Edwards
Deming](https://en.wikipedia.org/wiki/W._Edwards_Deming), who was among other
things an engineer and statistician.  Deming was one of the first to introduce
statistics into manufacturing practices, and in particular an early advocate
for real-time feedback loops.  The theory goes that as a result of sharing
quality assessments with workers, workers become more invested in the quality
of their product.

Deming's teachings were first widely adopted in Japan during the post-war
period.  Ford Motor Company was simultaneously manufacturing transmissions for
a new  car in both Japan and the United States. After the car made it to
market, consumers quickly started requesting the model with Japanese
transmissions  over the US-made transmissions. When Ford engineers decided to
inspect for differences between the transmissions made in the US vs. Japan,
they found that while those made in the US were within the specified  tolerance
ranges, the Japanese were virtually identical to each other and  closer to the
nominal values for each part. As a result, the Japanese transmissions ran
smoother.

What does this tell us about the relationship we should strive for between 
people and technology in the modern world?  In fact, many of the same problems
of poor quality control and lack of investment are happening with machine
learning and data aggregation. People don't know how their data are being used
and lack any reason to be invested in the results of machine learning 
projects based on data collected from sources such as social media.

There are many ways that data are aggregated, but one of the most common is a
barter relationship where people are told "give us your data, and in return
we'll provide you some service. (e.g. social media)." 

Unfortunately, this sends the message that the intelligence is in the algorithm
and not in the data and it removes the role of human intelligence in data
collection.

So what can we do about it? Is it conceivable to imagine a world where
people have awareness of what data they're producing, the ability to influence
what happens with it, and some ability to improve it if it's to a purpose?

One source of inspiration is how workers not only gained agency through
not only manufacturing practices but also through unionization.

Lanier proposes the notion of Mediators of Individual Data, or MIDs. A MID
would represent a cohort of individuals who band together and collectively
advocate for controlled usage of their data.

As an example of how free-association based groups can effectively advocate
for their interests together, look at the track record of 
[Gareem Bank](https://www.grameen-bank.net/) in Bangladesh.

Muhammad Yunus, founder of Gareem Bank, won the Nobel Peace Prize in 2016 for
his research and work on solidarity lending as a means to provide banking
services to the rural poor without collateral. 

[Solidarity lending](https://en.wikipedia.org/wiki/Solidarity_lending) has been
around for a while, and it's not without valid criticism, but the fundamental
idea of using group cohesion to reduce risk and establish trust seems to hold
water.

In any large-scale learning environment, Lanier argues, there has to be some
coarse-grained mechanisms.  In evolution, we call it a species: we don't just
have one evolutionary lineage that tries to solve everything. In a neural
network, it's individual layers.

Currently, social media exists without that coarse-grainedness -- it's just the
provider vs. individuals. Without the distributed mechanisms of group-level trust,
and group-level attention to decency and quality, we have created a world
where inflammatory media that ignites our fight-or-flight response prevails.

Even if we were to successfully give people collective bargaining and
responsibility in the context of social media, there's still this pervasive
view of compuer intelligence as a threat to human laborers.

This comes down to a question of how computer intelligence is viewed: is it
separate from our own intelligence, as if a mind of its own, or is it an
extension of humanity, like a tool?

Lanier argues gives two reasons why the "AI" side of this divide, where
computers are viewed as intelligent independent and separately from human
intelligence, may have won the star role in popular culture narratives. 1). It
plays into the fear of the other, and that can be used to yield funding.  That
is to say, when one approaches a military agency and tells them Skynet is going
to come alive, and whoever controls it is going to control the world, they're
pretty fast to hand over their money.  2). The other side of this is that it's
flattering to think of humans as giving birth to some kind of new life-form, as
if we can play god.

Instead, if we were to recast AI from meaning "artificial intelligence", to
denoting aggregate, associative, and augmented intelligence – a form of
intelligence which people work together to create with the understanding of
technology as a human activity, rather than as a threat to humanity – perhaps
people would feel more optimistic about their ability to contribute in shaping
the future. 

One possible model of how a future where people are given more respect and
agency in the aggregation of data used for machine learning projects is
[Microsoft Trove](https://www.microsoft.com/en-us/ai/trove). Trove provides
users the ability to license their images and data to machine learning projects
in exchange for a small payment while still getting to own their data. By
providing an opportunity for researchers in need of data and those producing
the data to interact, the Trove project aims to ethically and respectfully
produce high quality machine learning datasets.

[Link to Talk](https://archive.org/details/hopeconf2020/20200727_1400_Keynote_-_Jaron_Lanier.mp4)
