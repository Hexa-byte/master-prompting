# Constrained Generation

## Overview

Constrained generation is a prompt engineering technique that places specific limitations on how an LLM responds. By setting clear boundaries, formats, or rules, you can control the model's output to ensure it meets your exact requirements. This approach is particularly valuable when you need precise, structured responses or when you want to avoid certain types of content.

## Key Benefits

- **Precise outputs**: Gets exactly the format and content you need
- **Reduced irrelevance**: Minimizes off-topic or unnecessary information
- **Consistent structure**: Creates predictable, uniform responses
- **Better compliance**: Helps avoid unwanted or inappropriate content
- **Format control**: Ensures outputs match required templates or schemas
- **Focus maintenance**: Keeps the model on task for specific objectives

## Effective Implementation

### Basic Constraints

The simplest constraints specify content type, length, or format:

```
Explain quantum computing in exactly three paragraphs. 
The first paragraph should define what quantum computing is.
The second paragraph should explain how it differs from classical computing.
The third paragraph should describe one potential application.
Use simple language suitable for a high school student.
```

**Why it works**: Clear boundaries help the model organize information effectively while maintaining focus on the requested content structure.

### Format Constraints

Specify exact output formats for structured data:

```
Create a JSON object representing a recipe with the following structure:
{
  "name": "Recipe name",
  "prep_time_minutes": number,
  "cook_time_minutes": number,
  "ingredients": [
    {
      "name": "ingredient name",
      "quantity": number,
      "unit": "measurement unit"
    },
    ...more ingredients
  ],
  "steps": [
    "step 1 description",
    "step 2 description",
    ...more steps
  ],
  "nutrition": {
    "calories": number,
    "protein_grams": number,
    "carbs_grams": number,
    "fat_grams": number
  }
}

Make it a recipe for a vegetarian pasta dish.
```

### Output Length Constraints

Control the verbosity of responses:

```
Summarize the key features of blockchain technology in:
1. A single sentence (maximum 20 words)
2. A single paragraph (maximum 100 words)
3. A comprehensive explanation (maximum 300 words)

Keep each summary at or under the specified word count.
```

### Content Exclusion Constraints

Specify what should NOT be included:

```
Write a short guide about online privacy. 
Do NOT include:
- Recommendations for specific VPN products
- Technical instructions requiring coding knowledge
- Legal advice or interpretations of privacy laws
- Discussion of hacking or unauthorized access techniques

Focus only on practical, easy-to-implement privacy measures for ordinary internet users.
```

## Advanced Techniques

### Constraint Combinations

Combine multiple constraints for highly specific outputs:

```
Create social media post about sustainable living with these specifications:
- Platform: Instagram
- Exactly 150 characters (not words)
- Include exactly 3 hashtags
- Must contain one statistic about waste reduction
- Must end with a question to encourage engagement
- Tone should be informative but optimistic
- Do not use emojis
```

### Reasoning Constraint

Force the model to apply specific reasoning frameworks:

```
Analyze the environmental impact of electric vehicles using the following framework:

1. Lifecycle Analysis:
   - Manufacturing impacts
   - Operational impacts
   - End-of-life impacts

2. Comparative Assessment:
   - Direct comparison to conventional vehicles
   - Quantification where possible
   - Regional variations to consider

3. Balanced Perspective:
   - Benefits must be supported by specific data
   - Limitations must be acknowledged
   - No overall conclusion without addressing both points

Ensure that each section addresses only its specific aspect and avoids repeating information from other sections.
```

### Guided Exploration

Provide a structured path through complex issues:

```
Examine the ethical implications of facial recognition technology by considering these questions in sequence:

1. What are the primary privacy concerns?
   (Answer in 3-4 sentences maximum)

2. How might this technology benefit public safety?
   (Provide exactly 3 specific examples)

3. What technical limitations affect reliability?
   (Focus only on algorithmic and implementation issues)

4. What guardrails or regulations might address the concerns while preserving benefits?
   (Suggest 2-3 specific policies)

Address each question separately and do not refer to your answers to later questions when answering earlier ones.
```

### Output Templating

Provide a specific template for the model to follow:

```
Complete the following case study template for the Netflix business model:

COMPANY OVERVIEW:
[2-3 sentences describing what Netflix is and its industry position]

KEY VALUE PROPOSITION:
[1-2 sentences on the main value Netflix offers customers]

REVENUE STREAMS:
- Primary: [Description]
- Secondary: [Description, if applicable]

COST STRUCTURE:
- Fixed costs: [List top 2-3]
- Variable costs: [List top 2-3]

COMPETITIVE ADVANTAGES:
1. [First advantage]
2. [Second advantage]
3. [Third advantage]

CHALLENGES:
1. [First challenge]
2. [Second challenge]

FUTURE OUTLOOK:
[2-3 sentences on potential future directions]

Fill in the bracketed sections while maintaining the exact structure provided.
```

## Applications

Constrained generation is particularly effective for:

1. **Structured data creation**: Generating JSON, CSV, or other data formats
2. **Standardized communications**: Creating consistent customer emails, reports, or documentation
3. **Content moderation**: Ensuring outputs meet specific guidelines
4. **Educational materials**: Creating questions or explanations at specific knowledge levels
5. **Technical writing**: Generating documentation that follows precise conventions
6. **Creative writing with parameters**: Stories or content with specific requirements

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| Model ignores constraints | Break constraints into numbered lists and remind at the end |
| Incomplete application of constraints | Ask the model to verify compliance before concluding |
| Constraints conflict with each other | Prioritize constraints or reduce their number |
| Over-constrained prompts limit quality | Balance constraints with room for quality and creativity |
| Constraints misunderstood | Define terms clearly and provide examples |

## Tips for Effective Constraints

1. **Be explicit and precise**: Clearly state what you want and don't want.

2. **Use numbered or bulleted lists**: Makes constraints more visible and harder to ignore.

3. **Prioritize constraints**: If using multiple constraints, indicate which are most important.

4. **Verify compliance**: Ask the model to check its response against the constraints.

5. **Balance constraint and quality**: Too many constraints can result in rigid, low-quality outputs.

## Real-World Example

Here's how constrained generation can be used for creating standardized customer responses:

```
Generate a customer service response email with these constraints:

SCENARIO:
- Customer name: [INSERT NAME]
- Issue: Order #12345 arrived with a damaged product (coffee maker)
- Customer tone: Frustrated but polite
- Customer requested: Replacement and expedited shipping

CONSTRAINTS:
1. Email must be between 150-200 words
2. Must begin with empathy for their situation
3. Must clearly state what actions we will take
4. Must include a timeline for resolution
5. No generic platitudes (e.g., "We value your business")
6. No requests for additional information (assume we have everything needed)
7. Must include exactly ONE relevant policy statement about our quality guarantee
8. Closing must offer additional assistance if needed

FORMAT:
Subject line: [Clear, specific subject line]

[Email body]

[Professional sign-off]
[Company name]
```

Constrained generation helps you harness the creative and analytical abilities of LLMs while maintaining precise control over their outputs. By setting clear boundaries and expectations, you can get more reliable, consistent, and useful responses tailored to your exact needs.