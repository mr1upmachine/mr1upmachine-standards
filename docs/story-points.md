# The Problem

When building large scale projects with many different people, its necessary to provide general estimations on how long the project will take to be completed. Within the realm of software development however, you'll often find that nearly all estimations will be inaccurate. This can be due to requirements changing from what was originally agreed upon, unforeseen hiccups as the system is actually being built, or simply incorrect assumptions from the beginning.

We could try and give loose estimations based on time. However if something seems like an easy & straightforward answer, one should ponder for a moment.

Very often, software engineers will find themselves estimating the length of a task incorrectly as they will vastly under or over estimate what needs to be done. To them, the task is so clear in their head! They don't consider delving into the documentation for syntax or writing automated tests or simply not being at 100% brain capacity for a given day or two. Or the inverse is true, where the task is so complex that they cannot see where to begin. You cannot plan an effective heist without knowing your point of entry, the shift schedule of the guards, where the treasure is located, and so on.

From the business side, projects ***must*** be given deadlines. How would any project be approved without them? The business owners cannot be in charge of defining these deadlines either. They do not know the system or its complexities and wouldn't know where to begin with an accurate estimation either. It's not their job to know these sorts of things. You wouldn't go to the doctor and tell them the exact illness and how long they have to fix it. You tell them the symptoms and they prescribe the treatment and go from there.

So estimating tasks in software is impossible right? If the developers can't estimate anything accurately and the business owners don't have enough knowledge then estimation would be impossible right?

# What CAN we estimate?

Surprisingly there is a way to make mostly accurate estimations by taking a page out of statistics. Using the [Law of Large Numbers](https://en.wikipedia.org/wiki/Law_of_large_numbers) we can predict the chaos and begin to make estimations across many iterations. However this still requires some sort of metric to calculate against.

**This metric cannot include time as that is what we are trying to calculate.** Thus we will create an arbitrary metric in which to size up the story. So what DO we know? What CAN we estimate if we can't use time?

There are three factors we can reasonably predict prior to the task.

## T-shirt Sizing

We can use the concepts from [T-shirt Sizing](https://asana.com/resources/t-shirt-sizing) as a place to start. A software engineer might not be able to give an accurate estimate on time, but they should still be able to guess about how large a task would be. We'll use XS, S, M, L, XL as our sizes.

## Collaboration

Anytime you involve more than one person in a project, there will be some sort of collaboration necessary. This collaboration will always take time, and is often the most underestimated part of any given project. Initial requirement gathering, meetings, coordination, follow-up requirement gathering, clarifications, sign offs, demos... All these take time. We can look at an individual task and get a general sense of how many people this will require to collaborate with to accomplish.

Note, this sort of collaboration metric is mostly geared toward measuring **external** collaboration. Software engineers within a team will often work amongst themselves to get past problems as a large part of the job for them is problem solving.

## The Unknown

Lastly, the biggest things that will affect the timeline will be the ones we don't know yet. How could we know the system isn't set up for this specific thing, or there was some kind of edge case not covered by the requirements, or that there is some sort of refactor that must be done. The list goes on and on. These drain our time just like any other thing. What we can do however, is list what we know we don't know. If the engineer looks at the task and sees that some questions needs to be answered, then that should be accounted for.

# Story Points

So now lets pull all these together and try to build some sort of metric. In comes story points. For each rank, we'll follow the [Fibonacci Sequence](https://en.wikipedia.org/wiki/Fibonacci_number) as it is exponential and we can do rough calculations around it. Often the bigger the task, the more you have to collaborate, the more unknown you are working with... The larger the overall task.

Let's build a chart of rough guidelines that will let us gauge how many points to give to a particular task.

| Points | T-shirt Size | Collaboration  | Unknowns   |
|--------|--------------|----------------|------------|
| 1      | XS           | Little to none | None       |
| 2      | XS-S         | Little to none | Maybe one  |
| 3      | S-M          | A little       | One or two |
| 5      | M            | Some           | A few      |
| 8      | M-L          | Some to a lot  | Several    |
| 13     | L-XL         | A lot          | Many       |
| 21     | XL           | Constant       | Too many   |

Some important notes on this chart:

- Each task should be single purpose. If you have a task that tries to accomplish two or three different things, then it should be broken into smaller tasks. If the work cannot be broken down any further, try and create subtasks to complete the issue.
- If a task is a M sized task with no unknowns, it should still be rated as a 5. Each column should be treated as a sort of loose guideline as to what to lookout for when giving estimations.
- If a task is given a 13 or higher, its often a sign that the task should be broken down into smaller tasks. It should be very rare that a single task be given a 13.
- Two 1 point tasks is not equivalent to one 2 point task. There is a very large cost to context switching that has to be accounted for as well.
- This is only one way to estimate these. Teams may choose other metrics or thresholds for how to assign story points. This is fine as long as the team as a whole agrees on the metrics used. In a scrum environment, this should be part of the team agreement.

## Tasks are too large

If a particular task pointed too high, then we must break it into smaller chucks that can be addressed. This keeps things from being insurmountable and will help with visibility on how far along the project is throughout development.

## Dependencies between tasks

You might notice that this does not account for dependencies between tasks. This is by design. These dependencies should be listed as requirements before the task can be completed. This keeps each task single purpose and can convey a flow of what needs to be done in what order.

In Jira, you can do this using the issue linking feature. You can link issues together as "blocks" & "blocked by" and view them in a Roadmap plan to see dependencies between issues. https://confluence.atlassian.com/jirasoftwareserver/linking-issues-939938934.html

## Under promise, over deliver

Delays are inevitable. If something will take x amount of time, then say it will take x + 1 time to complete. If you are unsure that a task should be 3 or 5 points, always pick 5. If an estimate is determined to be too small early on, then report immediately.

There is a natural unconscious desire to be 100% accurate or to not disappoint the business when giving estimations for a project. However nobody wants to arrive at launch day to hear that it will take 3 more months. Its always better to be up front on the estimation and surprise them when it gets done a month early.

# Velocity

After some time, you will begin to have an average of what a team can accomplish over the course of a single iteration. This is known as the team's velocity. Assuming no drastic changes to team dynamics, you should be able to view the amount of points completed on average for each iteration and converge on an educated guess of how many points can be accomplished.

While planning each iteration period, there will be a rough gauge of how evenly to spread the workload amongst the team but the specifics will come down to how the team self organizes. The goal of this exercise is to focus on the bigger picture, not individuals.

# Final Thoughts

At the end of the day, the goal is to have a semi-accurate estimation as to how long tasks will take in a large scale project. There will be delays. There will be slip ups. Note these and try to account for them in the next iteration. The use of story points is meant to try and give educated guesses to difficult to estimate tasks. Its a constantly evolving metric that will only grow more accurate with time.
