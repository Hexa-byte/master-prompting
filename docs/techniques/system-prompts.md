# System Prompts

## Overview

System prompts are special instructions that set the overall behavior, constraints, and characteristics of an LLM's responses. Unlike regular user prompts, system prompts establish persistent guidelines that should apply throughout the entire conversation. They're particularly useful for establishing consistent persona, setting guardrails, and providing meta-instructions about how the model should respond.

## Key Benefits

- **Persistent guidance**: Applies throughout the conversation without repetition
- **Behavior framing**: Sets overall tone, style, and approach
- **Consistent persona**: Maintains a coherent character or expert role
- **Meta-instructions**: Provides guidance about how to handle various situations
- **Efficiency**: Reduces need to repeat instructions in each prompt
- **Constraint setting**: Establishes clear boundaries and limitations

## Implementation Across Different LLMs

### OpenAI GPT Models

In the OpenAI API (ChatGPT, GPT-4), system prompts are implemented as a distinct message type:

```json
{
  "messages": [
    {
      "role": "system",
      "content": "You are a helpful assistant that specializes in explaining complex scientific concepts in simple terms appropriate for high school students. Use analogies, avoid jargon, and keep explanations under 3 paragraphs."
    },
    {
      "role": "user",
      "content": "Explain quantum entanglement."
    }
  ]
}
