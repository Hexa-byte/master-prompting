# Structured Output Prompt Template

## Overview

The Structured Output template instructs the LLM to format its response according to specific structures, schemas, or formats. This approach ensures consistent, parseable outputs that can be easily integrated into applications, databases, or further processing steps.

## Template Structure

```
I need you to analyze [INPUT/CONTENT] and provide the information in the following structured format:

Format:
[SPECIFY THE EXACT FORMAT, STRUCTURE, OR SCHEMA]

Rules:
1. Follow the format exactly without deviations
2. [ANY SPECIFIC RULES ABOUT HOW TO HANDLE CERTAIN FIELDS OR VALUES]
3. [ANY CONSTRAINTS OR LIMITATIONS]
4. [REQUIREMENTS FOR DEALING WITH MISSING OR UNCERTAIN INFORMATION]

Here is the [INPUT/CONTENT] to analyze:
[PASTE CONTENT HERE]
```

## When to Use

Use the Structured Output template when you need:

1. **Consistent formatting** - Outputs that follow a predictable structure
2. **Machine-parseable responses** - Data that can be directly processed by other systems
3. **Specific data extraction** - Pulling particular information from larger contexts
4. **Content organization** - Presenting information in a systematic way
5. **Comparison-ready data** - Information structured for easy comparison

## Customization Options

### Output Formats

Structured outputs can be formatted in many ways:

#### JSON
```
Format:
```json
{
  "title": "string",
  "summary": "string",
  "key_points": ["string", "string"],
  "sentiment": "positive|negative|neutral",
  "confidence": 0-100
}
```
```

#### Table
```
Format:
| Category | Description | Priority | Timeline |
|----------|-------------|----------|----------|
| [category1] | [description1] | [priority1] | [timeline1] |
| [category2] | [description2] | [priority2] | [timeline2] |
...and so on
```

#### List Structure
```
Format:
# [MAIN TOPIC]

## [SUBTOPIC 1]
- Key point 1: [explanation]
- Key point 2: [explanation]
- Key point 3: [explanation]

## [SUBTOPIC 2]
- Key point 1: [explanation]
...and so on
```

#### Form-like Structure
```
Format:
TITLE: [title]
AUTHOR: [author name]
YEAR: [year published]
SUMMARY: [1-2 sentence summary]
MAIN ARGUMENTS: 
1. [first argument]
2. [second argument]
...and so on
EVIDENCE QUALITY: [strong/moderate/weak]
RELEVANCE TO [TOPIC]: [high/medium/low with brief explanation]
```

### Handling Uncertain Information

Specify how to handle missing or uncertain information:

```
Rules:
If information is not explicitly provided in the content:
- For numerical fields, use null or N/A
- For text fields that require factual information, use "Information not available"
- For analytical fields where educated guesses are acceptable, provide your best estimate and mark with "[ESTIMATED]"
```

## Examples

### Product Review Analysis Example

```
I need you to analyze these product reviews and provide the information in the following structured format:

Format:
```json
{
  "product_name": "string",
  "average_score": number,
  "review_count": number,
  "sentiment": {
    "positive": number_percentage,
    "neutral": number_percentage,
    "negative": number_percentage
  },
  "top_pros": ["string", "string", "string"],
  "top_cons": ["string", "string", "string"],
  "common_use_cases": ["string", "string"],
  "user_demographics": ["string", "string"],
  "recommendation_rate": number_percentage
}
```

Rules:
1. Follow the JSON format exactly without deviations
2. Percentages should add up to 100% and be represented as numbers (e.g., 75.5 not "75.5%")
3. Extract only information that appears in multiple reviews
4. For any field where information is completely unavailable, use null
5. Include a maximum of 5 items for arrays, prioritizing the most frequently mentioned

Here are the product reviews to analyze:
[PASTE REVIEWS HERE]
```

### Meeting Summary Example

```
I need you to analyze this meeting transcript and provide the information in the following structured format:

Format:
# Meeting Summary

## Basic Information
- Date: [YYYY-MM-DD]
- Duration: [HH:MM]
- Participants: [Names of participants]
- Meeting Type: [Decision/Brainstorming/Status Update/Planning]

## Key Decisions
1. [Decision 1]
2. [Decision 2]
...

## Action Items
| Action | Owner | Deadline | Priority |
|--------|-------|----------|----------|
| [task1] | [owner1] | [deadline1] | [High/Medium/Low] |
| [task2] | [owner2] | [deadline2] | [High/Medium/Low] |

## Discussion Topics
### [Topic 1]
- [Key point 1]
- [Key point 2]
...

### [Topic 2]
- [Key point 1]
- [Key point 2]
...

## Follow-up Required
- [Follow-up item 1]
- [Follow-up item 2]
...

Rules:
1. Follow the markdown format exactly
2. Only include action items that have clear ownership (a person assigned)
3. Prioritize decisions and action items that received the most discussion time
4. For follow-up items, include only items explicitly mentioned as requiring follow-up
5. If a section would be empty, include the heading but note "None identified in transcript"

Here is the meeting transcript:
[PASTE TRANSCRIPT HERE]
```

## Best Practices

1. **Be explicit about format**: Provide the exact structure you want, including all field names and delimiters.
2. **Include type information**: Specify data types (string, number, boolean, etc.) where relevant.
3. **Set clear rules**: Explain how to handle edge cases, missing data, and ambiguities.
4. **Provide format examples**: For complex structures, show examples of correctly formatted outputs.
5. **Limit field count**: For complex structures, limit the number of fields to improve accuracy.

## Combining with Other Techniques

The Structured Output template can be effectively combined with:

- **Expert Role**: "As a data analyst, extract and structure the following information..."
- **Chain-of-Thought**: "Think step by step about what information belongs in each field, then output in this structure..."
- **Few-Shot Learning**: Provide examples of correctly structured outputs before requesting yours

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| Missing required fields | Explicitly list all required fields and specify how to handle if information is absent |
| Format inconsistencies | Provide a complete example of the expected format, not just field names |
| Overly complex structures | Break complex needs into separate, simpler requests with different structures |
| Poor nesting in hierarchical formats | For complex formats like JSON, show the full nesting structure with proper indentation |
| Mixed formats | Specify a single format rather than mixing (e.g., don't mix JSON and markdown) |

