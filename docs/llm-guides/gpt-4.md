# GPT-4 Prompt Engineering Guide

## Model Overview

GPT-4 is OpenAI's most advanced large language model, representing a significant improvement over previous versions in reasoning, following instructions, and reducing hallucinations. This guide focuses on effective prompting techniques specifically optimized for GPT-4.

## Key Capabilities

- **Complex reasoning**: Capable of multi-step logical reasoning
- **Instruction following**: Excellent ability to follow detailed, multi-part instructions
- **Code generation**: Strong coding abilities across multiple languages
- **Creative content**: Sophisticated creative writing with nuanced tone control
- **System messages**: Support for setting persistent behavior through system prompts
- **Long context window**: Supports 8K-32K tokens depending on the endpoint

## GPT-4 Strengths

- **Nuance understanding**: Grasps subtle distinctions and implicit meaning
- **Self-consistency**: More reliable in maintaining constraints throughout responses
- **Factual accuracy**: Better factual recall than previous models (but still has limitations)
- **Task decomposition**: Effectively breaks down complex problems
- **Multimodal capabilities**: GPT-4V can process images along with text

## GPT-4 Limitations

- **Knowledge cutoff**: Training data ends at a specific date (typically early 2023)
- **Hallucinations**: Can still confidently present incorrect information
- **Mathematical computations**: May make errors in complex calculations
- **Lack of internet access**: Cannot browse the web or access real-time information
- **Context window limits**: Cannot remember indefinitely long conversations

## Optimal Prompting Techniques for GPT-4

### 1. System Messages

GPT-4 responds well to system messages that set the overall behavior:

```
SYSTEM: You are an academic writing assistant specializing in political science. 
You help graduate students improve their research papers. Your communication style 
is scholarly but accessible. You provide constructive criticism while maintaining 
academic rigor. You excel at helping clarify arguments, improving structure, and 
suggesting additional scholarly sources when appropriate. Always maintain academic
integrity and encourage original thinking.

USER: Please review the introduction to my paper on democratic backsliding in 
Hungary and suggest improvements.

[Paper introduction text]
```

System messages are useful for:
- Setting persistent persona or role
- Establishing formatting preferences
- Defining ethical boundaries
- Creating consistent behavior across multiple user prompts

### 2. Specific, Explicit Instructions

GPT-4 excels when given detailed, explicit instructions:

```
Please critique this marketing email draft with the following approach:

1. First, identify the primary value proposition and assess its clarity (2-3 sentences)
2. Next, evaluate the call-to-action for effectiveness (2-3 sentences)
3. Then, highlight any unclear or jargon-heavy language (bullet points)
4. Finally, suggest specific improvements to make the email more compelling (5 specific suggestions)

Use a professional but direct tone. Focus on actionable improvements rather than general observations.

[Marketing email draft]
```

### 3. Chain-of-Thought Prompting

For complex reasoning tasks, guide GPT-4 through a step-by-step thinking process:

```
I need to optimize inventory for our retail business.

We have three product categories:
- Electronics: $120 profit per unit, requires 3 sq ft of storage, 14-day shelf life
- Clothing: $35 profit per unit, requires 1 sq ft of storage, 120-day shelf life
- Home goods: $55 profit per unit, requires 4 sq ft of storage, 60-day shelf life

We have 5,000 sq ft of storage space and want to maximize profit.

Think through this step by step:
1. First, calculate the profit per square foot for each category
2. Then, consider the shelf life constraints
3. Next, determine the optimal allocation of storage space
4. Finally, calculate the expected profit with this allocation
```

### 4. Few-Shot Learning

Provide examples for tasks with specific patterns:

```
I'd like you to convert these customer service emails into friendly responses that address the customer's concern while promoting our premium service tier when relevant.

Example 1:
CUSTOMER EMAIL: "Your website is confusing. I can't figure out how to change my password."
RESPONSE: "I'm sorry to hear you're having trouble with our website! To change your password, simply click on the 'Account' icon in the top right corner, then select 'Security Settings.' You'll find the password change option there. If you upgrade to our Premium tier, you'll get access to our dedicated support line for immediate assistance with any account issues. Can I help with anything else today?"

Example 2:
CUSTOMER EMAIL: "Why was I charged twice this month? This is unacceptable."
RESPONSE: "I sincerely apologize for the duplicate charge – that certainly shouldn't happen! I've initiated a refund for the second charge, which should appear in your account within 3-5 business days. I've also added a note to your account about this issue. Premium members receive priority processing on refunds (typically within 24 hours). Would you like to know more about our Premium benefits?"

Now please respond to this customer email:
CUSTOMER EMAIL: "I ordered a product last week and it still hasn't shipped. Order #45789."
```

### 5. JSON Mode / Structured Output

Request precise structured outputs:

```
Analyze the following product review data and return the results in a JSON object with the following structure:
{
  "overall_sentiment": "positive|neutral|negative",
  "key_themes": [array of identified themes],
  "product_strengths": [array of mentioned strengths],
  "product_weaknesses": [array of mentioned weaknesses],
  "improvement_suggestions": [array of suggestions if any]
}

REVIEW:
"I've been using this wireless headset for about 3 weeks now. The sound quality is 
really impressive for the price point, and I love how comfortable the ear cups are for 
long meetings. Battery life is decent - about 15 hours as advertised. My biggest 
complaint is the microphone quality, which my colleagues say makes me sound muffled. 
Also, the Bluetooth connection occasionally drops for a second or two. Would be great 
if they improved the mic and connection stability in the next version."
```

### 6. Multi-step Decomposition

Break complex tasks into clearly defined steps:

```
Help me write a comprehensive business case for implementing a new customer relationship 
management (CRM) system. Let's approach this step-by-step:

1. First, create an executive summary (max 150 words)
2. Then, write the "Current Situation" section describing typical problems faced without a modern CRM
3. Next, develop the "Proposed Solution" section outlining key features needed
4. After that, create a "Benefits Analysis" section with quantifiable outcomes
5. Then, construct a "Cost Analysis" section with typical implementation expenses
6. Follow with a "Risk Assessment" section identifying potential obstacles
7. Finally, write a "Timeline and Implementation" section with major milestones

For each section, let me review and provide feedback before moving to the next section.

Let's start with the executive summary.
```

## Advanced Techniques

### 1. Persona-Based Prompting

Enhance outputs by assigning specific expertise:

```
Assume the role of a senior financial analyst with expertise in market trends and cryptocurrency. 
You have 15+ years of experience advising high-net-worth clients on emerging investment opportunities.

Analyze the current state of non-fungible tokens (NFTs) as an investment vehicle with these considerations:
- Long-term viability vs. speculative bubble characteristics
- Correlation with traditional market movements
- Regulatory landscape and future implications
- Risk assessment for different investor profiles

Provide your professional analysis with specific insights that would be valuable to investors.
```

### 2. Calibrated Question Sequences

Use a series of increasingly specific questions:

```
I'm trying to understand quantum computing principles better. Let's explore this topic through a sequence of questions:

1. At the most basic level, how does a quantum computer differ from a classical computer?

[After receiving answer]

2. Now, explain how quantum entanglement specifically enables computational advantages.

[After receiving answer]

3. Can you explain the concept of quantum supremacy, with specific examples of problems where quantum computers outperform classical ones?

[After receiving answer]

4. What are the primary engineering challenges preventing widespread quantum computing adoption today?
```

### 3. Boundary Testing and Refinement

Iteratively clarify boundaries to refine outputs:

```
I'd like to create custom workout plans. Initially, I'll need a template with appropriate sections.

[After receiving initial template]

This looks good, but I need to specifically include heart rate zones in the cardio section. Also, could you add a warm-up routine section?

[After receiving revised template]

Perfect. Now let's fill this template for a specific case: a 40-year-old beginner with knee issues who wants to improve general fitness and can work out 3 times per week for 45 minutes each session.
```

### 4. Multimodal Prompting (for GPT-4V)

Combine image and text inputs for richer context:

```
[Attach image of a printed circuit board]

I've attached a photo of a circuit board from our drone prototype. Please:
1. Identify the main components visible in this image
2. Suggest possible improvements to the layout for better heat dissipation
3. Note any potential issues with the current design from what you can see
4. Recommend additional components that might enhance functionality
```

## Troubleshooting GPT-4 Responses

### Issue: Hallucinations or Factual Errors

If GPT-4 provides incorrect information:

```
I notice that some details in your previous response might not be accurate. 
Please re-examine your answer regarding [specific point]. If you're uncertain 
about any particular facts, please explicitly state that you don't have 
definitive information rather than speculating.
```

### Issue: Response Too Verbose

If responses are too long:

```
Your previous response was very comprehensive, but I need a more concise version. 
Please condense your answer to a maximum of [X] words/paragraphs, focusing only 
on the most essential points.
```

### Issue: Lack of Creativity

If responses are too generic:

```
That's a good start, but I'm looking for more innovative and original ideas. 
Please give me more creative and unconventional approaches that most people 
wouldn't typically consider.
```

## Best Practices for GPT-4

1. **Use system messages for persistent behavior**: Set the tone, role, and constraints
2. **Be explicit about formats**: Clearly specify output structure when needed
3. **Break down complex tasks**: Use step-by-step instructions for complicated tasks
4. **Request self-verification**: Ask the model to check its work for certain tasks
5. **Leverage iterative refinement**: Start broad and refine with follow-up prompts
6. **Control verbosity**: Specify desired length and level of detail
7. **Combine techniques**: Mix approaches like few-shot learning with CoT prompting
8. **Specify audience**: Indicate the knowledge level of the intended reader
9. **Use formatting for clarity**: Utilize markdown, numbering, and clear sections

By applying these GPT-4 specific techniques and best practices, you can significantly improve the quality, accuracy, and usefulness of the responses you receive.
