%title: MediterraneaJS 2015 - Lessons Learned Building Paz
%author: @lukeb0nd luke@yld.io
%date: 2015-05-19

-> Building <-

\                            \______  \___  \_____
                           / \___  //   |/\__  /
                          / /\__/ // /| |  / / 
                         / \_____// \___ | / /\___
                        /\_/     /\_/  |\_|/\_____/


-> # MediterraneaJS, Barcelona <-
-> ## June 2015 <-


-> Luke Bond <-
-> YLD.io <-
-> @lukeb0nd <-

---

## CONTENTS

- What this talk is/isn't
- What is Paz, historical context and story
- Lessons learned, both personal and technical

---

## WHAT THIS TALK IS/ISN'T

- I'm not here to show off something awesome I built
- I'm not going to live-code something to impress you
- I'm not going to otherwise try to blow your mind or patronise you
- I'm going to share a story in which I learned a lot
- I hope you get something out of it

---

## WHAT THIS TALK IS/ISN'T

This story follows a familiar template:
- I was interested in some stuff
- I built a thing to learn about that stuff
- Overall it went well but there were ups and downs
- I learned a lot about myself and about being a developer
- I'm going to share this with you

- Talk is mostly non-technical
- My intention is to humanise "the developer"
  - There is a lot of non-tech stuff we don't talk about enough
- Warning: at times decends into a rant about what it means
  to be a software engineer

---

## HISTORY

- At the time I was a backend developer
  - Not full-stack, not "DevOps"
- I wanted to learn more about "DevOps" type stuff
  - To have a more well-rounded skillset
- I started learning about Docker
  - Inspired by the Docker episode of NodeUp
- Questions re hosting and deployment led me to CoreOS and Fleet
- I identified two problems that I wanted to solve:
  - "Docker networking is hard"
  - and "Fleet needs a UI"
- I hacked together a POC and "Paz" was born

---

## WHAT IS PAZ AND WHY?

Purely for context of the story:
- Paz is an open-source Docker PaaS built in Node.js
- Leverages CoreOS, Etcd and Fleet for running Docker containers
- If all this is unfamiliar:
  - Imagine an open-source, host-it-yourself Heroku
  - That runs Docker containers
  - And is written in Node.js
- Sound like buzz-word bingo? More on this later...

If this is over your head don't worry;
this talk assumes no previous knowledge!

---

## HISTORY

- I got accepted to speak about it at Container Camp London 09/2014
  - (It was little more than vapourware at this point)
- 4 months of "crunch time" followed:
  - Daytime: day job as a Node.js consultant
  - Evenings & Weekends: Paz
  - I checked out of most other aspects of my life
- I worked hard, I made mistakes, but I achieved a lot
  - I loved what I was doing
  - I completely burned myself out
  - I wouldn't change a thing*

---

## HISTORY

- I built Paz and spoke about it at Container Camp
  - With invaluable help from friends and colleagues
  - /cc @tomgo, @bananaoomerang and @jongold
- After that I couldn't face it any more
- I worked for another two months in my day job then went travelling
- Stuff happened in my personal life
- I had lots of time to work on Paz but I did nothing
- I couldn't discipline myself
- I was suffering "burnout"; an unfamiliar feeling for me
  - Normally I have boundless energy

---

## OPEN-SOURCING PAZ

- I felt I needed a push to get me out of my rut
- I decided to open-source Paz as-is
  - i.e. "unready"
  - Release early vs when polished" <- interesting question
  - I hoped it would kick me into action
- Traction suffered but the project survived
- I spoke about the project and the burnout at LNUG in Feb '15
  - And open-sourced it during the talk
  - Very liberating!
  - It was a cthartic experience for me

---

## PAZ TODAY

- Progress on Paz picked up slowly after that
  - Although never at the "crunch time" pace
  - It's still far from my final vision
  - Because I don't have enough time to work on it
- YLD held a hackathon in Lisbon last month
  - As a YLD team-bonding exercise
  - As an open-source project by a team member, Paz was chosen
- Running the hackathon taught me a few things:
  - It's difficult to explain what Paz is
  - It requires knowledge of Docker, Fleet and systemd- rare
  - Paz didn't work "out of the box" for everyone
  - The documentation is sorely lacking

---

## PAZ TODAY

- So we did another, smaller hackathon
- Me, @tomgco and @sublimino went to Paris this weekend
- We locked ourselves away and hacked on Paz
- We improved the installation and upgraded Etcd
  - Paz now works better "out of the box"
- Progress was also made on our nascent CLI
- Now the focus will be on adding missing features
  - And documentation!

---

## THE PAZ COMMUNITY

- After the LNUG talk someone posted it to HackerNews
- 1000 GitHub stars & a GitHub trending repository!
  - May sound small but I was proud :)
- Paz wasn't ready for the exposure
- Didn't capitalise with traction
- It would be more ready if this happened today
- More of my time is required to promote Paz to get traction
  - And then more time to manage the community

---

## PERSONAL LESSON: BURNOUT

- Please don't take me as an expert on the subject
- I can only talk about my subjective experience
- From what I've read, I believe it can be different for everyone
  - Therefore so is the solution
- For me it was self-inflicted
  - Nobody was pushing me to do this. It was a personal project
- Therefore it was easily resolveable once I realised it
- I needed a break and some closure for the project
- If you're suffering burnout, you're not alone
  - Do something about it!

---

## PERSONAL LESSON: YOU CAN DO ANYTHING

- If you've ever felt you can't achieve something...
  - Perhaps some stuff you hear at a conferences is over your head
  - e.g. "I could never do that"
  - or "I'm not as smart/good as person X"
- Like most of us, I've felt like this before
- Particular in the area of "DevOps" type skills
- I don't really feel that way anymore
- Push yourself, challenge this self-doubt
- Take on a project that challenges these doubts
- For me, external deadlines help :)

Also remember:
- There are people who feel better by making others feel inferior

---

## TECHNICAL STUFF (+ RANTING)

- There were some definitely some technical lessons learned
- Some directly from Paz
- But difficult to separate from my work

---

## TECHNICAL STUFF (+ RANTING)

- Paz was a huge learning experience re Docker for me
- As always, my vision seemed simple enough
- I soon realised a simple Docker Paz was a toy
- Getting it right and production-ready is another matter
  - It requires solving big, difficult problems
- "Docker in production" is about more than running containers
  - ...and multi-host networking
  - ...and continuous deployment
- It must cover monitoring, logging, fail-over, etc.
- You know, standard stuff about running anything in production

---

## USING NEW TECHNOLOGIES AND METHODOLOGIES

- With new technologies come unexpected challenges
  - For which you may not be prepared
  - That may disrupt project timelines
  - That may pi$$ off the business
  - That may get you fired

---

## USING NEW TECHNOLOGIES AND METHODOLOGIES

- Being a developer is simple:
  - A business has a problem
  - They pay us to build a software solution to it
- But there is more to being a developer:
  - We love to learn and experiment
  - With technologies that inspire and interest us
  - Including new technology

---

## USING NEW TECHNOLOGIES AND METHODOLOGIES

- Sometimes there can be a tension between these two
  - Which can lead to an unfilfilment or unhappy developer
- Perhaps it's like how a commissioned artist might feel:
  - Creatively constrained but glad to be able to buy food etc.
- Some of us are lucky that the two more or less overlap
- ...and some of us are reckless and the two more or less overlap

---

## BEWARE THE SNAKE-OIL SALESPERSON

- Writing quality software and being a good software engineer is hard
- It is based on a few simple principles
  - But it's hard to learn how to apply them
- Anyone who tells you "use new technology X it will make things easy"
  - ...and doesn't follow it up with "but beware A, B and C"
  - ...is probably trying to sell you consulting in technology X

---

## WHAT AM I GETTING AT?

- New technologies and methodologies have a role
  - They challenge the status quo and push our industry forward
- Learning them is a great way to learn and grow as a developer
  - And keep up with the experimental cutting edge of our industry
- This is why i built Paz
- Any of you who've built something for free/fun understand this
- But let's play a little game

---

## IMAGINE THE FOLLOWING STATEMENTS

> Docker solves OS compatibility issues and allows you to deploy
> the same thing from dev to production

---

## IMAGINE THE FOLLOWING STATEMENTS

> Microservices mean you can develop faster, isolate yourself from
> blocking dependencies, allow you to compose services and to onboard
> new developers to a project faster as a result

---

## IMAGINE THE FOLLOWING STATEMENTS

> 0MQ allows you to build faster, more resilient, brokerless distributed
> systems without single points of failure.
> Therefore you shouldn't use RabbitMQ

---

## IMAGINE THE FOLLOWING STATEMENTS

> NoSQL databases are web-scale, you can't reach the scale you need in
> the future with relational databases

---

## IMAGINE THE FOLLOWING STATEMENTS

> Using a large, opinionated framework will lock you in and bring
> constraints that may not suit your problem; you shouldn't use them,
> instead you should choose a set of smaller, better-suited pieces
> and compose them into your system

---

## IMAGINE THE FOLLOWING STATEMENTS

> Distributed, brokerless Docker microservice buses running on
> unicornels are the future, they make everything else obsolete

---

## WHAT DO ALL OF THESE STATEMENTS HAVE IN COMMON?

They're all:
- Partially true (except perhaps the last one)
- Mostly BS
- Over-simplifications
- A dangerous trap for the unwary

But they're all true in the right context and in the right hands.

The warning here is not against using new technologies,
but against recklessness.

---

## SOFTWARE ENGINEERING HASN'T CHANGED A LOT

A developer should (IMHO):
- Write testable code
- Test your code
- Write code others can read, understand and maintain
- Build software as if you'll be on pager duty on launch day

---

## SOFTWARE ENGINEERING HASN'T CHANGED A LOT

- Our industry has been doing this for more than 50 years
- Writing quality software is hard and requires experience
- The notion that Docker, microservices, etc. changes that is laughable
- New tech introduces challenges you may not expect or be prepared for
- I've put most of these into production so if you think it's easy AMA

---

## IN SUMMARY

- New technology is disruptive by nature
- Nothing is a silver bullet
- Don't let anyone lull you into thinking otherwise
- Software engineering hasn't change a lot
- Beware the snake-oil salesperson
- Don't be reckless with your customers' businesses
