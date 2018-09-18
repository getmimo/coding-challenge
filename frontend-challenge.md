# Mimo Frontend Coding Challenge

The goal of this challenge is to create an extremely simplified version of the Mimo app that can retrieve some very basic lessons from a server and display them.

## Implementation

- You can solve the challenge in any way and framework you feel comfortable with (angular / react / vue / elm / ...). 
- Try to think about how you manage your state and how you structure it.
- You won't be judged on the visual design at all, the only metric is your code.
- Part of this coding challenge is to read the documentation for the APIs provided to you.
- Use Git to track your changes and upload your Git repo either on [GitHub](https://github.com) or [Bitbucket](https://bitbucket.com) to share it with us.

## Goal

Write a small app that can display a few very simple Mimo lessons. You get the information for the lessons from an API and should display the lessons. The lessons have a specific format (documented later) and should be rendered to the screen. If the lesson contains an interaction, display the interaction. Also display a "Next" button that, when pressed, checks that the lesson has been solved and continues to the next lesson.

When a lesson has been solved, store this event in a database of your choice in the browser (see "Lesson completion event").

If the user solved the last lesson, display a simple screen that says "Done".

Each lessons should have its own unique url. It might make sense to use the lesson ID for that.

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

Each object in the content array represents a text snippet that can have color. If the `input` object exists, it represents the range where the user has to type in the expected input. In place of that range there should be an input field instead of the text. In this example the user has to input "print" in order to proceed to the next lesson. If an input interaction exists, and the user hasn't typed in the correct input yet, disable the button. As soon as the input is the correct text, enable the button, so the user can proceed to the next lesson. If there is no input interaction, the button should always be enabled.

Here's an example of how the lesson above could look like:

<img width="894" alt="screenshot 2018-05-15 07 44 38" src="https://user-images.githubusercontent.com/815520/40041124-3db40568-581d-11e8-8327-f939fea207d9.png">


### Lesson completion event

A lesson completion event object is created when a lesson has been completed

It contains the following properties:
- The ID of the lesson
- A timestamp when the lesson started
- A timestamp when the lesson completed

## Server API

The server API for getting the lessons is extremely simple. Just do a GET request on https://file-bzxjxfhcyh.now.sh/, which returns a JSON object that contains all of the lesson information.


