# Mimo Take-home Assignment (Frontend)

## Welcome!

To give you an idea of how some of the work as mobile engineering team member will look and help us get an impression of how you might approach these tasks, we've put together a take-home assignment. We’re doing this asynchronously because we know that, despite our best efforts to create a laid-back atmosphere, live coding interviews can be stressful and results may not be representative of your work. We believe going through the assignment at your own pace is a more natural way to achieve this goal. We know that completing the assignment will require some time investment and we really appreciate you taking this time. We believe this is a win-win situation and we wouldn't ask you if we didn't already think you're a great fit for the role.

The objective of this take-home assignment is to create a simplified version of the Mimo app that can retrieve a simplified version of our coding lessons from a server and display them.

Fingers crossed!

## Implementation

- You can solve the challenge in any way and framework you feel comfortable with (angular / react / vue / elm / ...).
- Try to think about how you manage your state and how you structure it.
- You won't be judged on the visual design, the only metric is your code.
- While the visual aspect is not important, think about a nice user flow and experience.
- Part of this coding challenge is to read the documentation for the APIs provided to you.
- Use Git to track your changes and upload your Git repo on Github, and once you are done please share your private Repository with us via apply@mimo.recruitee.com

## Goal

Your goal is to write a small app with three simplified Mimo lessons (in the apps, we call these lessons "exercises"). You can get the information for the lessons from the API we provide. The lessons have a specific format (documented below) that defines how they need to be rendered. If a lesson contains an interaction, display the interaction. The initial page displays the first lesson. Also display a "Next" button that, when pressed, checks that the lesson has been solved and continues to the next lesson.

When a lesson has been solved, store this event in a database of your choice in the browser (see "Lesson completion event").

If the user solved the last lesson, display a simple screen that says "Done".

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
      "text": "print"
  },
  {
      "color": "#FFFFDD",
      "text": "(\""
  },
  {
      "color": "#FFFFFF",
      "text": "(Hello world!"
  },
  {
      "color": "#FFFFDD",
      "text": "\")"
  }],
  "input": {
    "startIndex": 0,
    "endIndex": 5
  }
}
```

Each object in the content array represents a text snippet, each of which can have a different color. If the `input` object exists, it represents the range where the user needs to type in the expected input. In this example, the user has to input "print" in order to proceed to the next lesson. If there's an input interaction in the lesson and the user hasn't typed in the input field yet, disable the button. As soon as the user has typed anything, enable the button to allow the user to check for the correct answer and go on to the next lesson or display a message if it is incorrect. If there's no input interaction, keep the button enabled.

Here's an example of how the lesson above could look like:

<img width="894" alt="screenshot 2018-05-15 07 44 38" src="https://user-images.githubusercontent.com/815520/40041124-3db40568-581d-11e8-8327-f939fea207d9.png">


### Lesson completion event

A lesson completion event object is created when a lesson has been completed

It contains the following properties:
- The ID of the lesson
- A timestamp when the lesson started
- A timestamp when the lesson completed

## Server API

The server API for getting the lessons is simple. Just run a GET request on https://file-bzxjxfhcyh.now.sh/, which returns a JSON object containing all of the lesson information.


