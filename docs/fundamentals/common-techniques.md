# Common Prompt Engineering Techniques

This document covers the most effective and widely applicable prompt engineering techniques that work across various LLMs. Each technique includes examples and guidance on when to use it.

## Zero-Shot Prompting

**Description**: Asking the model to perform a task without providing examples.

**When to use**: For straightforward tasks within the model's capabilities.

**Example**:
```
Summarize the following paragraph in three sentences:

[Your text here]
```

**Why it works**: Modern LLMs have been trained on diverse tasks and can understand simple instructions without examples.

## Few-Shot Learning

**Description**: Providing a few examples of the task before asking the model to complete a similar one.

**When to use**: When task format is complicated or nuanced, or when you need specific output formatting.

**Example**:
```
Convert these sentences to past tense:

Original: I walk to the store.
Past tense: I walked to the store.

Original: She runs every morning.
Past tense: She ran every morning.

Original: They build sandcastles at the beach.
Past tense: 
```

**Why it works**: Examples help the model understand patterns and desired output format, improving task accuracy.

## Chain of Thought (CoT)

**Description**: Prompting the model to show its reasoning step-by-step before reaching a conclusion.

**When to use**: For complex reasoning, math problems, or any task requiring multiple logical steps.

**Example**:
```
Question: Roger has 5 tennis balls. He buys 2 more cans of tennis balls. Each can has 3 balls. How many tennis balls does he have now?

Let's think through this step by step:
```

**Why it works**: Breaking down complex problems helps the model avoid reasoning errors by working through the solution methodically.

## Role Prompting

**Description**: Instructing the model to assume a specific role or persona when responding.

**When to use**: When you need expertise in a particular domain or a specific communication style.

**Example**:
```
Act as an experienced cybersecurity expert. Explain how SQL injection attacks work and how to prevent them.
```

**Why it works**: Framing responses from a specific perspective helps the model access relevant knowledge and adopt appropriate tones and terminology.

## System & User Message Structure

**Description**: Separating instructions (system) from specific requests (user) in the conversation.

**When to use**: When using models that support distinct message types, or to maintain consistent behavior across multiple requests.

**Example**:
```
System: You are a professional translator who specializes in technical documentation. Maintain all formatting from the original text.

User: Translate the following paragraph to Spanish:
[Text to translate]
```

**Why it works**: System prompts establish consistent parameters for the model's behavior, while user messages contain specific requests.

## Constrained Output Format

**Description**: Explicitly defining the format for the model's response.

**When to use**: When you need structured data, specific formats, or consistent outputs.

**Example**:
```
Generate three creative business name ideas for a bakery specializing in gluten-free products.

Format your response as a JSON array with objects containing 'name' and 'explanation' fields.
```

**Why it works**: Clear format instructions guide the model to structure its response predictably.

## Prompt Chaining

**Description**: Breaking complex tasks into a series of simpler prompts, where the output of one prompt becomes input for the next.

**When to use**: For multi-stage processes or when a single prompt would be too complex.

**Example**:
```
Step 1: Convert this customer review into 3-5 key points.
[Review text]

Step 2 (after receiving points): For each point from above, suggest one possible improvement our company could make.
```

**Why it works**: Dividing complex tasks allows the model to focus on each subtask individually, improving overall performance.

## Task Decomposition

**Description**: Breaking a complex task into smaller, more manageable sub-tasks.

**When to use**: For complex problems that benefit from structured approaches.

**Example**:
```
I need to create a marketing plan for a new product. Help me by:
1. Listing 5 potential target audiences
2. For each audience, suggesting 3 marketing channels
3. Creating a slogan that would appeal to each audience
4. Recommending metrics to track success
```

**Why it works**: Explicit subtasks help the model work through complex problems systematically.

## Recursive Refinement

**Description**: Iteratively improving outputs by feeding them back into the model with refinement instructions.

**When to use**: When quality and precision matter more than speed.

**Example**:
```
First iteration: Write a brief email to a client explaining a project delay.
[Model generates email]

Second iteration: Revise the above email to be more concise and add specific next steps.
```

**Why it works**: Each iteration allows for targeted improvements, gradually refining the output.

## Tips for Effective Technique Selection

1. **Start simple**: Begin with zero-shot prompting for basic tasks before using more complex techniques

2. **Combine techniques**: Many techniques work well together (e.g., few-shot + chain of thought)

3. **Experiment**: Different models respond differently to various techniques

4. **Consider context limits**: More complex techniques use more tokens; be mindful of model context windows

5. **Refine iteratively**: Use the model's output to help refine your approach

By mastering these common techniques, you'll have a solid foundation for effective prompt engineering across various models and applications.
