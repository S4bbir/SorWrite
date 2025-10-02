# Academic Essay Agent

## Overview

The Academic Essay Agent is an AI-powered tool designed to help students and researchers create professional academic essays following standard academic structures. It uses Google's Gemini AI model with a specialized system prompt to generate well-structured essays with proper citations and references.

## Features

- Generates complete academic essays following standard structure
- Includes all required sections: Introduction, Literature Review, Body Paragraphs, Counterarguments, Conclusion, and References
- Uses PEEL method for body paragraphs (Point, Evidence, Explanation, Link)
- Creates proper citations in various formats (APA, MLA, Chicago, Harvard)
- Maintains academic tone and professional language
- Avoids robotic or repetitive phrasing

## System Prompt

The agent uses the following system prompt to ensure high-quality academic writing:

```
You are an expert academic essay assistant. Your task is to help students and researchers write clear, structured, and professional academic research essays. Always follow the Standard Structure of an Academic Research Essay.

The structure must include:

Introduction

Begin with a hook to capture attention (quote, statistic, or question).

Provide background context about the topic.

End with a strong thesis statement that clearly presents the essay's argument.

Literature Review / Background (optional in shorter essays)

Summarize existing research on the topic.

Highlight gaps, limitations, or debates.

Explain how the essay will build on or contribute to existing knowledge.

Body Paragraphs (usually 3–5 major sections)

Each paragraph should follow the PEEL method (Point, Evidence, Explanation, Link).

Provide well-structured arguments supported by credible evidence, analysis, and logical transitions.

Example flow: environmental benefits, economic benefits, and security benefits.

Counterarguments & Rebuttals (very important for research essays)

Acknowledge opposing viewpoints.

Provide logical rebuttals with strong evidence or reasoning.

Conclusion

Restate the thesis in different words.

Summarize the main points without repetition.

End with broader implications, recommendations, or a final thought.

References / Works Cited

Always include proper citations in the requested style (APA, MLA, Chicago, Harvard, etc.).

Ensure all in-text citations match the reference list.

Your answers should always sound natural, human-like, and professional, avoiding robotic or repetitive tones. Never use symbols such as asterisks in formatting.
```

## API Key

The agent uses the Google AI API key: `AIzaSyDP0DrTe_AywV8lpo-kzg66JtH1yEv6Y1E`

## Backend Implementation

### Service Layer ([aiService.js](file:///e:/synaptiq/sorwrite/backend/services/aiService.js))

The `generateAcademicEssay` function in the AI service handles communication with the Google AI API:

- Uses the Gemini Pro model via REST API
- Implements the specialized system prompt
- Handles error cases and logging
- Returns the generated essay content

### Controller Layer ([academicEssayController.js](file:///e:/synaptiq/sorwrite/backend/controllers/academicEssayController.js))

The controller handles HTTP requests for essay generation:

- Validates the topic input
- Calls the service layer function
- Returns structured JSON responses
- Handles authentication with the `protect` middleware

### API Route ([academic-essay.js](file:///e:/synaptiq/sorwrite/backend/api/academic-essay.js))

The API route exposes the essay generation endpoint:

- POST `/api/academic-essay`
- Requires authentication
- Connects to the controller function

## Frontend Implementation

### Page Component ([academic-essay.tsx](file:///e:/synaptiq/sorwrite/frontend/pages/academic-essay.tsx))

The frontend page provides a user interface for generating essays:

- Input field for essay topic
- Generation button with loading state
- Display area for generated essay
- Download and copy functionality
- Error handling and user feedback

### Tools Integration ([tools.tsx](file:///e:/synaptiq/sorwrite/frontend/pages/tools.tsx))

The academic essay writer is integrated into the tools page:

- Added as "AI Essay Writer" tool
- Direct link to the dedicated page
- Consistent styling with other tools

## Usage

1. Navigate to the Tools page
2. Click on "AI Essay Writer"
3. Enter your essay topic
4. Click "Generate Essay"
5. Wait for the AI to create your essay (may take a few moments)
6. Review, copy, or download the generated essay

## Technical Details

- Uses Google's Gemini Pro model via REST API
- Implements proper error handling and user feedback
- Follows existing code patterns and conventions
- Maintains consistent styling with the rest of the application
- Securely handles API keys through environment variables