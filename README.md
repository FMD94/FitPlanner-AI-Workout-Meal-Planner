# FitPlanner – AI Workout & Meal Planner
## Course Project


## 1. Project Overview

FitPlanner is an AI-powered fitness and nutrition planning web application built as a course project.
The system leverages a Large Language Model (LLM) to generate personalized weekly workout and meal plans based on user inputs such as age, height, weight, fitness goal, experience level, diet preference, and preferred language.

The application demonstrates practical usage of LLMs for structured content generation, user-driven prompt engineering, and real-time interaction through a web-based UI.

## 2. Key Features

- Personalized weekly workout plans

- Personalized weekly meal plans

- Dynamic number of training days (3–6 days)

- BMI calculation and ideal weight range

- Input validation (age, height, weight required)

- English and Arabic language support

- RTL (Right-to-Left) layout support for Arabic

- Clean, user-friendly web interface using Gradio

- JSON-based structured AI output for reliability

## 3. Technologies Used

Programming Language: Python 3

LLM API: OpenAI Responses API (gpt-4.1-mini)

Frontend / UI: Gradio

Backend Logic: Python functions

Deployment Environment: Google Colab (demo), extendable to cloud hosting

Version Control: Git / GitHub


## 4. System Architecture

The system follows a simple but effective architecture:

1. **User Interface (Gradio)**  
   Collects user inputs such as age, height, weight, fitness goal, and language.

2. **Backend Logic (Python)**  
   Validates inputs, calculates BMI, and prepares structured prompts.

3. **LLM Integration (OpenAI Responses API)**  
   Generates structured workout and meal plans in JSON format.

4. **Post-processing & Formatting**  
   Parses AI output and renders it in a readable, user-friendly layout.


## 5. Prompt Engineering Strategy

The prompt design in **FitPlanner** is intentionally structured to ensure reliable, consistent, and machine-processable AI outputs. The strategy focuses on constraining the LLM’s behavior while still allowing meaningful personalization.

### Objectives of the Prompt Design

The prompt is carefully engineered to achieve the following goals:

- Enforce JSON-only output  
- Prevent markdown or natural-language explanations  
- Control output structure and field names  
- Enforce an exact number of workout days  
- Support multilingual content while keeping JSON keys in English  

### JSON Schema Enforcement

To reduce ambiguity and improve parsing reliability, the prompt includes an explicit JSON schema example that the model must follow.

```json
```json
{
  "weekly_workout": [
    {
      "day": "Monday",
      "focus": "Full body",
      "exercises": [
        { "name": "Squats", "sets": 3, "reps": "10-12" }
      ],
      "notes": "Warm up properly"
    }
  ],
  "weekly_meals": [
    {
      "day": "Monday",
      "meal": "Breakfast",
      "description": "Meal description",
      "approx_calories": 350
    }
  ],
  "disclaimers": [
    "Not medical advice",
    "Consult a professional"
  ]
}

```

## 6. API and Model Details

API: OpenAI Responses API

Model: gpt-4.1-mini

Max Tokens: 1400

Input: Custom structured prompt

Output: Strict JSON parsed programmatically

The application includes safeguards to:

Extract only valid JSON blocks

Repair common JSON formatting issues

Gracefully handle API or parsing errors

## 7. BMI and Health Calculations

The system calculates:

BMI (Body Mass Index)

Ideal weight range based on BMI standards (18.5–24.9)

These values are computed locally (not by the LLM) to ensure correctness and reliability.

## 8. User Interface Design

Clean dark-themed UI

Responsive layout

Centered output section

RTL support for Arabic language

Clear form labels and dropdowns

Real-time language switching

## 9. Setup and Usage Instructions
Run on Google Colab

Open the notebook

Install dependencies:

pip install openai gradio


Add your OpenAI API key using environment variables

Run all cells

Access the Gradio public URL

Local Setup (Optional)
pip install openai gradio
python app.py

## 10. Known Limitations

Generated plans are not medical advice

Nutrition values are approximate

LLM output may vary slightly between runs

Requires active internet connection and API key

## 11. Future Enhancements

User accounts and saved plans

PDF export of plans

More diet types and health conditions

Mobile-first UI

Deployment as a standalone website

Database integration

## 12. Conclusion

FitPlanner demonstrates how Large Language Models can be used effectively in real-world applications to generate structured, personalized content.
The project highlights skills in prompt engineering, API integration, UI development, and responsible AI usage.
