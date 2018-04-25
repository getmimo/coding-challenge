# Mimo Mobile Coding Challenge

The goal of this challenge is to create an extremely simplified version of the Mimo app that can retrieve some very basic lessons from a server and display them.

## Implementation

- While you can write the challenge any way you want, we use Reactive Extensions + MVVM to build our apps at Mimo, so if you know those technologies, it would make sense to apply them in this challenge
- You won't be judged on the visual design at all, the only metric is your code.
- Part of this coding challenge is to read the documentation for the APIs provided to you.
- Use Git to track your changes and upload your Git repo either on [GitHub](https://github.com) or [Bitbucket](https://bitbucket.com) to share it with us.

## Goal

Write a small app that can display a few very simple Mimo lessons. You get the information for the lessons from an API and should display the first lesson. The lessons have a specific format (documented later) and should be rendered to the screen. If the lesson contains an interaction, display the interaction. Also display a "Next" button that, when pressed, checks that the lesson has been solved and continues to the next lesson.

When a lesson has been solved, store this event in a mobile database of your choice on the device (see "Lesson completion event").

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
      "type": "text",
      "color": "#FFFFFF",
      "format": "bold",
      "text": "Hello "
  },
  {
      "type": "input",
      "color": "#FFFFFF",
      "expected": "World"
  },
  {
      "type": "text",
      "color": "#FFFFFF",
      "format": "italic",
      "text": "!"
  }]
}
```

### Lesson completion event

A lesson completion event object is created when a lesson has been completed

It contains the following properties:
- The ID of the lesson
- A timestamp when the lesson started
- A timestamp when the lesson completed

## API



