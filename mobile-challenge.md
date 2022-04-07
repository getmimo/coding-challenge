# Mimo Take-home Assignment (Mobile)

## Welcome!

To give you an idea of how some of the work as mobile engineering team member will look and help us get an impression of how you might approach these tasks, we've put together a take-home assignment. We’re doing this asynchronously because we know that, despite our best efforts to create a laid-back atmosphere, live coding interviews can be stressful and results may not be representative of your work. We believe going through the assignment at your own pace is a more natural way to achieve this goal. We know that completing the assignment will require some time investment and we really appreciate you taking this time. We believe this is a win-win situation and we wouldn't ask you if we didn't already think you're a great fit for the role.

The objective of this take-home assignment is to create a simplified version of the Mimo app that can retrieve a simplified version of our coding lessons from a server and display them.

Fingers crossed!

## Implementation

- While you can write the challenge any way you want, we use Reactive Extensions + MVVM to build our apps at Mimo, so if you know those technologies, it would make sense to apply them in this challenge.
- We'll only evaluate your submission based on your code - there's no need to worry about the visual design
- Part of this coding challenge is to read the documentation for the APIs we provide.
- Use Git to track your changes and upload your Git repo either on [GitHub](https://github.com) or [Bitbucket](https://bitbucket.com) to share it with us.

## Goal

Write a small app that can display a few very simple Mimo lessons. You get the information for the lessons from an API and should display the first lesson. The lessons have a specific format (documented later) and should be rendered to the screen. If the lesson contains an interaction, display the interaction. Also display a "Next" button that, when pressed, checks that the lesson has been solved and continues to the next lesson.

When a lesson has been solved, store this event in a mobile database of your choice on the device (see "Lesson completion event").

When the last lesson has been solved, display a simple screen that says "Done".

## Data structure

### Lessons

- Each lesson has an ID and JSON content that describes how the lesson is formatted
- Lessons come in a specific order

#### Lesson Content Format

Every lesson contains content, formatted as JSON, that represents an array of content objects:

```json
{
  "id": 5,
  "content": [{
      "color": "#FFFFFF",
      "text": "Hello "
  },
  {
      "color": "#FFFFFF",
      "text": "World"
  },
  {
      "color": "#FFFFFF",
      "text": "!"
  }],
  "input": {
    "startIndex": 7,
    "endIndex": 11
  }
}
```

Each object in the content array represents a text snippet, each of which can have a different color. If the `input` object exists, it represents the range where the user has to type in the expected input. In this example, the user has to input "World" in order to proceed to the next lesson. If an input interaction exists, and the user hasn't typed in the correct input yet, disable the button. As soon as the input is the correct text, enable the button so the user can proceed to the next lesson. If there's no input interaction, the button should always be enabled.

Here's an example of how this lesson could look like:

<img width="217" alt="challengedisplay" src="https://user-images.githubusercontent.com/964691/39253366-fe542ad0-48a7-11e8-98c4-8e1c2c6a470d.PNG">

### Lesson completion event

A lesson completion event object is created when a lesson has been completed.

It contains the following properties:
- The ID of the lesson
- A timestamp when the lesson was started
- A timestamp when the lesson was completed

## Server API

The server API for getting the lessons is simple: just send a GET request to https://mimochallenge.azurewebsites.net/api/lessons and you'll receive a JSON object that contains all the lesson information.

