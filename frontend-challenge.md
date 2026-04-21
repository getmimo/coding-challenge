# Mimo Take-home Assignment (Frontend)

## Welcome!

To give you an idea of how some of the work as a frpmtemd engineering team member will look and help us get an impression of how you might approach these tasks, we've put together a take-home assignment. We're doing this asynchronously because we know that, despite our best efforts to create a laid-back atmosphere, live coding interviews can be stressful and results may not be representative of your work. We believe going through the assignment at your own pace is a more natural way to achieve this goal. We know that completing the assignment will require some time investment and we really appreciate you taking this time. We believe this is a win-win situation and we wouldn't ask you if we didn't already think you're a great fit for the role.

The objective of this take-home assignment is to create a simplified version of the Mimo app that can retrieve coding lessons from a server and display them.

**This is an open-ended challenge.** There is no single "right" answer. We care more about your decisions, reasoning, and how you approach problems than about matching a specification exactly. Feel free to change, improve, or reimagine any part of this challenge.

Fingers crossed!



## Important

- **User Experience (UX):** How does the app feel to use? Consider loading states, error handling, feedback, accessibility, and the overall flow. The visual design itself is not important, but the experience is.
- **The learning content** Invest time into the learning content. Your job is to create a great experience for the user.
- **Code Structure and Architecture:** How do you manage state? How is your code organized? We look for clean separation of concerns, maintainability, and thoughtful architectural decisions.
- **LLM Collaboration:** You must use **OpenCode** to build this challenge. We want to see how you work with AI — share your OpenCode session link (or multiple) with your submission. We are interested in your prompts, iterations, and how you leverage LLMs in your workflow.
- **openrouter api key:** We will provide an openrouter api key which you can use with opencode.
- **dont invest more than 5hours:** Rather use the readme to describe what you would work on next. We do want to protect your time.

## What We Value

- Solve the challeng by using react
- Try to think about how you manage your state and how you structure it.
- he main metrics for judgment are your LLM usage, your code and UX.
- While the visual aspect is not important, think about a nice user flow and experience.
- Part of this coding challenge is to design your own API and lesson format.
- Use Git to track your changes and upload your Git repo on GitHub. Once you are done, please share your private repository with us via apply@mimo.recruitee.com.

## Goal

Your goal is to write a small app that teaches a user **how to add a button to a homepage** through a series of interactive lessons. Assume your users are full beginners and understand nearly nothing about coding. You decide how many lessons to include (we suggest 3–5) and how to structure them.

Each lesson must be loaded individually from an API endpoint that **you build yourself**. The initial page should display the first lesson.

If the user solved the last lesson, display a done screen

## Data Structure

- Come up with a fitting data structure you serve via an API

## Server API

You must build your own lightweight API to serve the lessons. We suggest the following endpoint structure, but you can adapt it as needed:

```
GET /lessons          → Returns a list of all lesson IDs and metadata
GET /lessons/:id      → Returns the full content for a specific lesson
```

You can implement this API using any technology you prefer: a static JSON server, a tiny Express app, Next.js API routes, or anything else. The API should be runnable locally with clear instructions in your README.

## Submission

Please include the following in your submission:

1. A link to your private GitHub repository.
2. Your **OpenCode session link** so we can review how you collaborated with AI during the challenge.
3. A README with instructions on how to run both the app and the API locally.

Once you are done, please share everything with us via apply@mimo.recruitee.com.
