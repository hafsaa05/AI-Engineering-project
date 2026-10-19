# Clarimind: An AI Whiteboard Tutor

AI Engineering course project proposal.

## Team

| Name | Student ID |
|---|---|
| Abdul Rahman Azam | 23K-0061 |
| Syeda Sara Ali | 23K-0070 |
| Hafsa Rashid | 23K-0064 |

**Team Lead:** Hafsa Rashid

## Project description

We want to build a tutor that teaches the way a good teacher does at a board. The learner types in
a topic along with their age group and level, and the app draws a lesson step by step on an
on-screen chalkboard while an AI voice explains each step. Short quizzes after each section will
check whether the learner understood.

## Objectives

- Generate a visual, narrated lesson on any topic from one line of input.
- Adapt the explanation to the learner's age and level.
- Test understanding with quizzes during the lesson.
- Keep the app safe for students and reliable when an AI service is down or out of quota.

## Methodology

We plan to split the work across several AI agents instead of using one large prompt. A research
agent will gather facts on the topic using web search. A lesson agent will turn those facts into
steps, each with narration and drawing instructions written in a simple JSON format that the
frontend can draw on a canvas. For common diagrams like the heart or an engine, the model will pick
from a library of ready-made drawings instead of drawing from scratch. A quiz agent will write
questions for each section, and a voice agent will read the lesson aloud, in sync with the board.

If the main model fails, we will fall back to backup models. User input will be filtered for
harmful topics and prompt injection. We will test the backend and frontend with automated tests.

## Tools and frameworks

- **AI:** Google Gemini, Google Agent Development Kit (ADK), Groq as a fallback
- **Backend:** Python, FastAPI, WebSockets, MongoDB
- **Frontend:** React, TypeScript, Vite, HTML Canvas, Web Audio API
- **Testing and deployment:** pytest, Vitest, Docker
