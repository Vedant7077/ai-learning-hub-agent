# AI Learning Hub Agent

A multi-agent AI learning workflow built with n8n and Google Gemini.

## What it does

The workflow accepts learning content through a webhook and generates:

- Summaries
- Detailed study notes
- Multiple-choice quizzes
- Flashcards

It also supports YouTube content by fetching the video transcript and enriching the generated content using web search and Wikipedia.

## Architecture

1. Receive content through webhook
2. Normalize input
3. Detect content type
4. Fetch YouTube transcript when required
5. Run four specialized AI agents
6. Enrich information using web search and Wikipedia
7. Validate and format outputs
8. Merge results
9. Return structured JSON response

## Tech Stack

- n8n
- Google Gemini
- SerpAPI
- Wikipedia
- Supadata
- JavaScript
- REST APIs

## Agents

### Summary Agent
Generates a structured summary with additional context.

### Notes Agent
Creates detailed study notes with definitions and examples.

### Quiz Agent
Generates 5 MCQs with answers and explanations.

### Flashcards Agent
Generates 8 concept-based flashcards.

## Setup

1. Import `workflow/learning-hub.json` into n8n.
2. Configure the required credentials.
3. Configure the webhook.
4. Activate the workflow.
5. Send content to the webhook.

## Example Input

```json
{
  "content": "Your learning content or YouTube URL",
  "contentType": "youtube",
  "language": "English"
}
