# Step-by-Step Reasoning Prompt Template

## Overview

The Step-by-Step Reasoning template instructs the LLM to break down complex problems or tasks into explicit, sequential steps. This approach encourages methodical thinking, reduces errors, and produces more thorough and traceable results.

## Template Structure

```
I need a detailed, step-by-step approach to [TASK/PROBLEM].

Please:
1. Break down this task into [NUMBER] clear, sequential steps
2. For each step, provide:
   - A clear explanation of what needs to be done
   - Why this step is important
   - Any potential challenges or considerations
   - Resources or tools that might be helpful
3. After listing all steps, summarize the key points and critical success factors

The [TASK/PROBLEM] is: [DETAILED DESCRIPTION OF TASK OR PROBLEM]

Additional context: [ANY RELEVANT CONSTRAINTS, PREFERENCES, OR BACKGROUND INFORMATION]
```

## When to Use

Use the Step-by-Step Reasoning template when you need:

1. **Methodical problem-solving** - Breaking down complex tasks into manageable pieces
2. **Clear instruction sequences** - Creating "how-to" guides or procedures
3. **Educational explanations** - Teaching concepts in a structured manner
4. **Decision frameworks** - Evaluating options through a defined process
5. **Planning assistance** - Developing project plans or implementation strategies

## Customization Options

### Depth of Analysis

Adjust the level of detail based on your needs:

- **High-level overview**: "Break this down into 3-5 major steps"
- **Detailed procedure**: "Provide 7-10 comprehensive steps with sub-steps where necessary"
- **Exhaustive analysis**: "Create a detailed 15+ step plan covering every aspect of the process"

### Focus Areas

Specify particular aspects to emphasize:

```
For each step, place special emphasis on [SAFETY CONSIDERATIONS/COST FACTORS/TIME EFFICIENCY/etc.]
```

### Perspective

Request steps from different viewpoints:

```
Provide steps from the perspective of a [BEGINNER/EXPERT/MANAGER/CUSTOMER/etc.]
```

## Examples

### Project Planning Example

```
I need a detailed, step-by-step approach to launching a small e-commerce website.

Please:
1. Break down this task into 8-10 clear, sequential steps
2. For each step, provide:
   - A clear explanation of what needs to be done
   - Why this step is important
   - Any potential challenges or considerations
   - Resources or tools that might be helpful
3. After listing all steps, summarize the key points and critical success factors

The task is: Creating an e-commerce website selling handmade jewelry, from initial planning through to launch and first sales.

Additional context: I have a small budget (under $5,000), basic technical skills, and about 3 months to complete this project. I already have product photos and descriptions prepared.
```

### Problem-Solving Example

```
I need a detailed, step-by-step approach to reducing customer churn for a SaaS business.

Please:
1. Break down this problem into 6-8 clear, sequential steps
2. For each step, provide:
   - A clear explanation of what needs to be done
   - Why this step is important
   - Any potential challenges or considerations
   - Resources or tools that might be helpful
3. After listing all steps, summarize the key points and critical success factors

The problem is: Our B2B software company has seen customer churn increase from 5% to 12% over the past six months, and we need a structured approach to identify causes and implement solutions.

Additional context: We're a 30-person company with customers primarily in the financial services sector. Our average contract value is $15,000/year, and most customers who churn do so within the first 4 months.
```

## Best Practices

1. **Be specific about the problem/task**: The more detailed your description, the more relevant the steps will be.
2. **Specify the number of steps**: This helps control the granularity of the response.
3. **Request explanations**: Ask for the reasoning behind each step, not just what to do.
4. **Include context**: Mention constraints, resources available, and background information.
5. **Ask for potential challenges**: This prompts more thorough consideration of each step.

## Combining with Other Techniques

The Step-by-Step template can be effectively combined with:

- **Expert Role**: "As an experienced project manager, provide step-by-step instructions for..."
- **Few-Shot Learning**: Provide an example of a well-structured step-by-step breakdown before asking for yours
- **Structured Output**: "For each step, format your response as Step X: [Title], Description: [explanation], Challenges: [list], Resources: [list]"

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| Steps are too general | Specify the desired number of steps and request sub-steps for complex items |
| Missing important considerations | Add specific categories to address: "For each step, address time requirements, cost implications, and necessary skills" |
| Steps not practical for your situation | Include more context about your constraints and resources in the prompt |
| Lack of prioritization | Request that steps be ordered by importance or that critical paths be identified |

