---
title: "DDD By Yourself 1: Just Pick a Dumb Idea"
date: 2026-04-14
---

I mostly work on prototypes in Python. And while Python has a place in my heart, a couple of months ago I decided that it was time to learn more about building applications at scale. I set out to learn Domain Driven Design, a common design pattern used in large scale enterprise applications, especially within the C# community. 

I watched a few talks ([this one](https://www.youtube.com/watch?v=STKCRSUsyP0) is nice) and read a few blogs. And while they were certainly insightful, I felt like this was not enough.

### Come up with a dumb idea
First, think of a problem that your software will solve. Don't get bogged down by the idea that your software must be useful - we're trying to learn DDD, not change the world. So anything will do. How about these dumb ideas:
 - A scheduling system for who can use the microwave at work? 
 - A system that will detect by webcam when you really need a coffee?
 - A system that will optimally close the blinds just enough so you do not go blind yourself from the sun?

All of these will do. I came up with the idea of keeping track of maintenance for my household applicances. Maybe not as funny as the ideas above, but it is definitely good enough.

### Think about your domain
So you picked a problem that your software will solve. At the core of DDD lie the domain entities: the unshakable core of your application that will outlive all other parts. For my idea, the maintenance tracking of household appliances, I came up with a few domain entities. 

How do you do that? Pick up a piece of paper and pen or pencil and start jotting and/or sketching. What are the most important core entities? How are they related? Don't think of implementation just yet.

When building a realworld application, you will also want to pull in a domain expert for this (such as a microwave-user at work, or a sleep-deprived caffienated coworker). Since I was building this on my own, I did my best to put myself in the shoes of the common household appliance maintainer. 

Of course, that household appliance maintainer will usually also be me. However, we can imagine that potential users of our system will not be as technical as me, the software developer. So I tried as best as I could to put myself in the shoes of a not-as-technical household appliance maintainer.

### Lessons learned
By thinking about my domain on pen and paper, I learned a few things:
- Naming things is hard, and forces you to really think your problem through. I eventually named my most important domain entity "Asset", since I eventually also want to support more than just household appliances - there is so much that needs maintenance as an adult living in a house!
- I incidentally inserted CRUD jargon here and there. For example, I had the UpdateStatus domain method for the Asset entity, but later I changed this to ChangeStatus, which is probably more natural to the nontechnical user.


Eventually, I came up with two domain entities: `Asset` and `MaintenanceTask`. The idea is that an `Asset` can have one or more `MaintenanceTask`'s. Think of an asset called "Dishwasher", that could have a MaintenanceTask to clean the filter once a week, and another to run a full self cleaning programme every four weeks.

### To the task!
Now that we have our problem domain, it is time to start building! However, I immediately ran into the problem that there are very few understandable examples of implementing DDD onilne, except for a few very basic ones. That's why I used ChatGPT during my learning process. I'd encourage you to do this, too! Check out [the next blog](https://ejorritsma.github.io/blog/2026/04/14/ddd-chatgpt-as-coach.html) for some helpful tips!
