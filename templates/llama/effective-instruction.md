# Effective Instruction Prompts for Llama Models

## Overview

Llama models (and their derivatives like Mistral, Vicuna, or Alpaca) often respond best to clear, explicit instructions that follow specific patterns. This document provides templates optimized for effective prompting of Llama-family models across various use cases.

## Core Instruction Templates

### Basic Instruction Format

The fundamental instructional format that works well across most Llama models:

```
I want you to [ACTION] about [TOPIC].

The output should be [FORMAT DESCRIPTION].

Make sure to [SPECIFIC REQUIREMENTS].

Do not [CONSTRAINTS/LIMITATIONS].
```

Examples:

```
I want you to write a blog post about renewable energy.

The output should be a 500-word article with a catchy headline, 3-4 main sections, and a conclusion.

Make sure to include recent innovations in solar and wind technology, and explain their practical applications for homeowners.

Do not use technical jargon without explaining it, and avoid making specific price predictions.
```

### Step-by-Step Task Format

For complex tasks requiring sequential processing:

```
I want you to help me with [COMPLEX TASK].

Follow these steps:
1. First, [INITIAL ACTION]
2. Then, [SECOND ACTION]
3. Next, [THIRD ACTION]
4. Finally, [FINAL ACTION]

For each step, explain your reasoning briefly before moving to the next step.
```

Example:

```
I want you to help me evaluate which electric vehicle would best fit my needs.

Follow these steps:
1. First, ask me 5 key questions about my driving habits, budget, and preferences
2. Then, analyze my answers to determine my priority factors (range, performance, price, etc.)
3. Next, recommend 3 specific EV models that match my requirements
4. Finally, provide a comparison table of these models highlighting their strengths and weaknesses

For each step, explain your reasoning briefly before moving to the next step.
```

## Specialized Templates

### Technical Problem-Solving

For debugging or technical assistance:

```
I need help solving a technical problem with [TECHNOLOGY/SYSTEM].

Problem description:
[DETAILED DESCRIPTION OF THE ISSUE]

What I've tried so far:
- [APPROACH 1]
- [APPROACH 2]
- [APPROACH 3]

Error messages or symptoms:
[ERROR TEXT OR BEHAVIOR DESCRIPTION]

Please:
1. Identify potential causes of this issue
2. Suggest specific solutions, starting with the most likely cause
3. Explain how to prevent this problem in the future
```

Example:

```
I need help solving a technical problem with my React.js application.

Problem description:
My component re-renders infinitely when I use useState and useEffect together.

What I've tried so far:
- Added console.logs to track re-renders
- Wrapped the function in useCallback
- Tried using useRef instead

Error messages or symptoms:
No error messages, but the browser becomes unresponsive and the console shows endless logging.

Please:
1. Identify potential causes of this issue
2. Suggest specific solutions, starting with the most likely cause
3. Explain how to prevent this problem in the future
```

### Content Creation Template

For generating creative or informational content:

```
I need you to create [CONTENT TYPE] about [TOPIC].

Target audience: [AUDIENCE DESCRIPTION]
Tone: [TONE DESCRIPTION]
Length: [LENGTH SPECIFICATION]

Key points to include:
- [POINT 1]
- [POINT 2]
- [POINT 3]

Style requirements:
- [STYLE ELEMENT 1]
- [STYLE ELEMENT 2]
```

Example:

```
I need you to create a sales email about our new productivity software.

Target audience: Small business owners with 10-50 employees
Tone: Professional but conversational, solution-focused
Length: 250-300 words

Key points to include:
- The software integrates with all major communication platforms
- Users report saving 5+ hours per week on administrative tasks
- We offer a 14-day free trial with no credit card required

Style requirements:
- Include a compelling subject line
- Use at least one relevant statistic
- End with a clear, low-pressure call to action
```

### Analysis and Evaluation Template

For analyzing information and providing evaluation:

```
I need you to analyze [SUBJECT] according to the following criteria:

Key areas to evaluate:
1. [CRITERION 1]
2. [CRITERION 2]
3. [CRITERION 3]

For each criterion, please:
- Provide an assessment score (1-10)
- Explain the reasoning behind the score
- Suggest specific improvements or alternatives

Additional considerations:
[ANY SPECIAL FACTORS TO CONSIDER]

Here is the [SUBJECT] to analyze:
[CONTENT FOR ANALYSIS]
```

Example:

```
I need you to analyze this product landing page according to the following criteria:

Key areas to evaluate:
1. Visual clarity and user experience
2. Persuasiveness of value proposition
3. Effectiveness of call-to-action elements

For each criterion, please:
- Provide an assessment score (1-10)
- Explain the reasoning behind the score
- Suggest specific improvements or alternatives

Additional considerations:
This page is targeting enterprise customers who prioritize security and reliability over price.

Here is the landing page copy to analyze:
[LANDING PAGE TEXT]
```

## Best Practices for Llama Models

1. **Be direct and specific**: Clearly state what you want the model to do.
2. **Use numbered lists for steps**: Llama models follow numbered instructions particularly well.
3. **Specify output format**: Be explicit about how you want information structured.
4. **Provide examples**: When possible, include examples of desired outputs.
5. **State constraints clearly**: Explicitly mention what not to do or include.
6. **Break down complex tasks**: Divide multi-part requests into clear steps.
7. **Use explicit section headers**: Mark different parts of your prompt with clear headers.

## Troubleshooting

If your Llama model isn't producing the expected results:

1. **Simplify your request**: Break complex prompts into simpler, sequential prompts.
2. **Rephrase as direct instructions**: Change questions to statements ("Tell me about..." instead of "What is...?").
3. **Add structure markers**: Use bullet points, numbering, and clear section demarcations.
4. **Provide more context**: Give additional background information or examples.
5. **Try different instruction verbs**: Replace "analyze" with "examine," "evaluate," or "assess."

## Adapting for Different Llama Variants

Different Llama variants may respond better to slightly modified approaches:

### For Alpaca-tuned models:
Emphasize the instruction format with clear "Instruction:" and "Response:" markers.

### For Vicuna-tuned models:
These often work well with conversational setups that include "USER:" and "ASSISTANT:" role markers.

### For Mistral-based models:
These generally handle longer, more complex instructions well and benefit from detailed context.

By applying these templates and practices, you can significantly improve the quality and consistency of outputs from Llama-family models across a wide range of applications.

