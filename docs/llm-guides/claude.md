# Claude Prompt Engineering Guide

## Model Overview

Claude (developed by Anthropic) is a family of large language models known for helpfulness, harmlessness, and honesty. The Claude family includes models like Claude 2, Claude Instant, and Claude 3 (Opus, Sonnet, and Haiku), each with different capabilities and performance characteristics. This guide focuses on effective prompt engineering specifically for Claude models.

## Key Capabilities

- **Long context window**: Supports up to 100K tokens in the latest models
- **Constitutional AI**: Designed with safety and alignment as core principles
- **Document analysis**: Excellent at processing and analyzing lengthy documents
- **Detailed reasoning**: Strong logical reasoning capabilities
- **Reduced hallucinations**: Designed to admit uncertainty rather than fabricate
- **XML and structured output**: Good at formatting responses in structured formats

## Claude Strengths

- **Nuanced understanding**: Excels at grasping subtle implications and complex instructions
- **Balanced responses**: Generally provides measured, balanced perspectives
- **Document comprehension**: Particularly strong at synthesizing information from long texts
- **Straightforward responses**: Tends to be direct and on-topic
- **Safety boundaries**: Built-in guardrails against harmful content

## Claude Limitations

- **Knowledge cutoff**: Training data ends at a specific date
- **Mathematical reasoning**: May struggle with complex calculations
- **Coding capabilities**: Generally less optimized for code generation than some competitors
- **Over-cautiousness**: May sometimes be overly cautious in responses

## Optimal Prompting Techniques for Claude

### 1. XML Tagging for Structure

Claude responds well to XML-style tags for organizing prompts and desired outputs:

```
<context>
This is background information about the company's refund policy. Refunds are
processed within 30 days of approval and can be issued as store credit or returned
to the original payment method.
</context>

<customer_inquiry>
I returned my purchase two weeks ago, but haven't received my refund yet. 
Order #12345. When should I expect it?
</customer_inquiry>

<instructions>
Write a helpful customer service response that explains our refund process timeline.
Be empathetic, clear, and provide a specific timeframe for when they should expect 
their refund based on our policy. Include information about how they can check their
refund status.
</instructions>
```

### 2. Constitution Style Guidelines

One of Claude's unique features is its responsiveness to clear ethical or style guidelines:

```
I'd like you to analyze the following research paper on climate change.

When providing your analysis:
- Focus on the methodology and data interpretations
- Highlight strengths and limitations without politicizing the topic
- Identify any areas where additional research would be helpful
- Use scientific terminology, but explain complex concepts
- Remain neutral even if findings are controversial
- Point out any potential funding biases or conflicts of interest

<paper>
[Insert paper text here]
</paper>
```

### 3. Document Analysis Structure

For document analysis, use a clear structure:

```
<document>
[Insert document text here]
</document>

Please analyze this document with the following approach:
1. Summarize the main points (maximum 3 paragraphs)
2. Identify key stakeholders mentioned
3. Extract any dates, deadlines, or timeframes
4. List any action items or next steps
5. Highlight areas that need clarification or contain ambiguities
```

### 4. Multimodal Prompting (Claude 3)

For models that support image inputs:

```
<image>
[Image of a complex data visualization chart]
</image>

Please analyze this chart with the following steps:
1. Describe what the visualization is showing
2. Explain the key trends or patterns visible in the data
3. Identify any outliers or anomalies
4. Suggest possible implications of these findings
5. Recommend how this visualization could be improved for clarity
```

### 5. Role and Format Guidance

Clearly defining the role and output format helps Claude generate more appropriate responses:

```
You are a professional report writer specializing in market analysis.

<data>
[Market data about electric vehicle adoption rates across different countries]
</data>

Create a structured market analysis report with these sections:
- Executive Summary (5 sentences maximum)
- Regional Trends Analysis (3 paragraphs)
- Growth Drivers (5 bullet points)
- Market Barriers (5 bullet points)
- Future Outlook (2 paragraphs)

Use professional business language, include specific data points from the information provided, and format the report with clear headings and subheadings.
```

## Advanced Techniques

### 1. Preference Matrix

When you need Claude to evaluate options, provide a clear evaluation framework:

```
<options>
Option A: Expand into the European market first
Option B: Focus on growing our presence in existing North American markets
Option C: Enter emerging markets in Southeast Asia
</options>

Evaluate these strategic options for our e-commerce business using the following criteria:
- Initial capital requirements (lower is better)
- Expected time to profitability (shorter is better)
- Market competition intensity (lower is better)
- Regulatory complexity (lower is better)
- Long-term growth potential (higher is better)

For each criterion, rate each option on a scale of 1-5, explain your reasoning, and then provide an overall recommendation with justification.
```

### 2. Chain-of-Thought with Checkpoints

Claude performs better with explicit reasoning checkpoints:

```
<problem>
A company manufactures widgets at three factories. Factory A produces 1000 widgets per day with a 2% defect rate. Factory B produces 1500 widgets per day with a 3% defect rate. Factory C produces 800 widgets per day with a 1% defect rate. What is the total number of non-defective widgets produced across all factories in a 5-day work week?
</problem>

Please solve this step-by-step:

1. First, calculate the daily production of non-defective widgets for each factory.
2. Then, calculate the total daily production of non-defective widgets across all factories.
3. Finally, calculate the weekly production by multiplying by 5 work days.

Show your calculations at each step and explain your reasoning.
```

### 3. System vs. Human Message Simulation

While Claude doesn't have a formal system/user message distinction like some models, you can simulate it:

```
<system>
You are a specialized medical terminology assistant. Your purpose is to help
medical students understand complex terminology. Always provide definitions that are
accurate but accessible. Include etymology when relevant. When multiple definitions
exist, list the most common medical usage first. Always include a simple example of
the term used in context.
</system>

<user>
What does "idiopathic thrombocytopenic purpura" mean?
</user>
```

## Troubleshooting Claude Responses

### Issue: Overly Cautious Responses

If Claude is being too cautious about a reasonable request:

```
I understand you're designed to be careful, but the analysis I'm requesting is
for educational purposes about [legitimate topic]. Please provide a thorough
analysis focusing on these specific aspects:
- [aspect 1]
- [aspect 2]
- [aspect 3]

You can assume I have a professional/academic interest in this information and
will use it responsibly.
```

### Issue: Hallucinations or Incorrect Information

If you notice Claude generating incorrect information:

```
Please analyze the following statement for accuracy. If you're uncertain about
any aspect, explicitly state that you don't have enough information rather than
making assumptions.

<statement>
[Include the potentially incorrect statement here]
</statement>
```

### Issue: Verbose Responses

To get more concise outputs:

```
Please provide a concise response to the following question. Limit your answer
to 3-5 sentences maximum, focusing only on the most essential information.

<question>
[Your question here]
</question>
```

## Model-Specific Tips

### Claude 3 Opus
- The most capable model for complex reasoning and nuanced understanding
- Can handle very detailed instructions with multiple constraints
- Excellent for document analysis and creative tasks
- Use for tasks requiring deep comprehension and detailed outputs

### Claude 3 Sonnet
- Best balance of capabilities and efficiency
- Good for most business applications and content generation
- Strong at following complex instructions
- Use for day-to-day tasks requiring good comprehension and quality

### Claude 3 Haiku
- Fastest and most efficient model
- Best for straightforward tasks and quick responses
- Use when speed is more important than nuance
- Ideal for simple interactions and basic content generation

## Best Practices for Claude

1. **Be explicit about boundaries**: Clearly state what the model should and shouldn't do
2. **Structure matters**: Use XML tags, numbered lists, and clear sections
3. **Set clear evaluation criteria**: Tell Claude how to judge or evaluate options
4. **Provide examples when needed**: For unusual formats or styles
5. **Use checkpoints for complex reasoning**: Break down multi-step problems
6. **Specify format precisely**: Describe exactly how you want information presented
7. **Ask for uncertainty**: Explicitly request that Claude identify areas of uncertainty
8. **Request verification**: Ask Claude to check its own work for specific tasks
9. **Iterate with refinement**: Use follow-ups to refine initial responses

By leveraging these Claude-specific techniques, you can get more accurate, helpful, and appropriately formatted responses tailored to your specific needs.

