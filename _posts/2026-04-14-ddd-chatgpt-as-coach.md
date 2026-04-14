---
title: "DDD by Yourself: ChatGPT As a Coach"
date: 2026-04-14
---

Getting started with implementing a DDD style codebase can be overwhelming. I wanted to do it anyway to really grasp the concepts, and I used ChatGPT as a coach to cut through the noise. But before consulting ChatGPT about implementation details, I came up with the idea and its corresponding domain by myself. Want to do the same? Check out [my first blog here](https://ejorritsma.github.io/blog/2026/04/14/ddd-just-pick-a-dumb-idea.html)!

### Why use ChatGPT at all?
Once I had my idea and domain entities, I had to implement it. I opted for a small MVP containing only an API for CRUD actions concerning `Asset`s. This might sound boring, and while the final result might be a bit boring indeed, I learned a lot by building this piece by piece.

One problem I immediately ran into is the fact that there were *very little* examples on the internet for how to implement a DDD application in C#, apart from ridiculously simple examples. 

One thing I definitely wanted to avoid, is that ChatGPT would come up with all the answers for me and even build the entire thing for me, leaving me as the "copy-and-paster". Then I would not have learned anything. Learning is supposed to be a little uncomfortable.

### Setting up with ChatGPT
Since I started from scratch, I first used ChatGPT like teacher ssistant. I imagined asking questions during seminar about building an application from the vague ideas and domain entities. The goal was to have a sparring partner to set up the framework of the project and get going. A few messages I sent to ChatGPT during this stage are (unedited):
- "Most important thing is a "solid, finished .NET-project". I'd also like to use EF Core, which is often used. An exposed API would also be nice. And perhaps a frontend in the same or a separate repository, later down the line."
- "Let's start with building the Domain for Asset. And only asset, nothing more. Then tests building and further implement how to add an asset, delete, update, etcetera, in the application/infrastructure/api layers."

As you can see, these messages are quite undirectional, leaving a lot of space for interpretation by ChatGPT. By being critical and asking the right questions or indicating what I was unsure about, I could incrementally build the backbone of the application.

### Guarding my learning process
After this initial stage, I needed to shield my ability to learn on my own from ChatGPT's tendency to provide full implementations. So I thought of ChatGPT like a casual junior professor I could ask questions during office hours. Generally, the time of a professor is limited, so you want to keep it short and to the point. And they will usually only provide a few guiding ideas, not complete implementations. A few examples of questions I asked during this stage:
* When working on testing: "Is Xunit a good test framework? I know `unittest` from Python, that's kind of garbage, I'd rather use `pytest`"  (answer: Xunit is fine and widely used)
- When working on the database: "Earlier you recommended to put an AssetRepository in the Domain. Seems like a bad idea to me to put database knowledge in the Domain Layer?" (got me a nice explanation that a repository does not know anything about the database)

During this stage, it was especially important to stay vigilant in two ways. First, I had to be very clear that I did not want cookie cutter answers. And secondly, when asking follow-up questions, ChatGPT would sometimes respond with more complex, enterprise solutions than before (such as introducing CQRS). Use your engineering spidey senses (think of YAGNI or KISS)!

### Final thoughts
I think ChatGPT can be a useful tool during any learning process, especially when you're doing it by yourself. However, you need to be clear about the guardrails (no cookie-cutter answers) and stay critical of overly complex solutions.

I learned a lot about DDD by building the software piece by piece with my ChatGPT sidekick. I'd recommend it to anyone who wants to learn a new concept by implementing it, especially when doing it by yourself!
