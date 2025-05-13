# GPT System Prompt Examples

## Overview

System prompts provide persistent instructions that guide an LLM's behavior throughout a conversation. Unlike regular user prompts, system prompts establish ongoing parameters, constraints, and characteristics for how the model should respond. This document provides effective system prompt templates specifically optimized for the GPT series of models (GPT-3.5, GPT-4).

## Basic Structure

In OpenAI's API format, system prompts appear as:

```json
{
  "messages": [
    {
      "role": "system",
      "content": "Your system instructions here"
    },
    {
      "role": "user",
      "content": "User's first message"
    }
  ]
}
