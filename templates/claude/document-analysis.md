# Claude Document Analysis Prompt Templates

## Overview

Claude models excel at analyzing and extracting information from long documents or texts. This template collection provides frameworks for effectively prompting Claude to analyze documents, extract specific information, summarize content, compare texts, and identify key patterns or insights.

## Core Document Analysis Templates

### Comprehensive Document Summary

This template guides Claude to provide a thorough, structured summary of a document:

```
I need you to analyze and summarize the following [DOCUMENT TYPE].

Please structure your summary as follows:
1. Executive Summary (3-5 sentences highlighting the most important points)
2. Key Facts and Findings (bullet points of essential information)
3. Main Sections Overview (brief summary of each major section)
4. Important Details (items that require special attention)
5. Context and Significance (how this document relates to [RELEVANT CONTEXT])

As you analyze, please pay particular attention to:
- [SPECIFIC ASPECT 1]
- [SPECIFIC ASPECT 2]
- [SPECIFIC ASPECT 3]

Here is the document:
[PASTE DOCUMENT TEXT HERE]
```

Example:

```
I need you to analyze and summarize the following research paper.

Please structure your summary as follows:
1. Executive Summary (3-5 sentences highlighting the most important points)
2. Key Facts and Findings (bullet points of essential information)
3. Main Sections Overview (brief summary of each major section)
4. Important Details (items that require special attention)
5. Context and Significance (how this paper relates to current AI safety research)

As you analyze, please pay particular attention to:
- Methodology used for evaluating the safety measures
- Limitations acknowledged by the authors
- Recommendations for future research

Here is the document:
[PASTE RESEARCH PAPER TEXT HERE]
```

### Information Extraction

This template helps Claude pull specific information from a document:

```
I need you to extract specific information from the following [DOCUMENT TYPE].

Please locate and provide:
1. [INFORMATION TYPE 1] - including [DETAILS ABOUT WHAT TO EXTRACT]
2. [INFORMATION TYPE 2] - including [DETAILS ABOUT WHAT TO EXTRACT]
3. [INFORMATION TYPE 3] - including [DETAILS ABOUT WHAT TO EXTRACT]

For each piece of information:
- Quote the relevant text directly
- Provide the location (page number, section, or paragraph reference if available)
- Add a brief explanation of context if necessary

If any requested information is not present in the document, explicitly state that it's missing.

Here is the document:
[PASTE DOCUMENT TEXT HERE]
```

Example:

```
I need you to extract specific information from the following legal contract.

Please locate and provide:
1. Termination conditions - including all circumstances under which either party can end the agreement
2. Payment terms - including amounts, schedules, and late payment penalties
3. Confidentiality clauses - including scope and duration of confidentiality obligations

For each piece of information:
- Quote the relevant text directly
- Provide the location (page number, section, or paragraph reference if available)
- Add a brief explanation of context if necessary

If any requested information is not present in the document, explicitly state that it's missing.

Here is the document:
[PASTE CONTRACT TEXT HERE]
```

### Comparative Document Analysis

This template guides Claude to compare multiple documents:

```
I need you to compare the following [NUMBER] [DOCUMENT TYPES].

Please analyze and contrast them across these dimensions:
1. [COMPARISON CRITERION 1]
2. [COMPARISON CRITERION 2]
3. [COMPARISON CRITERION 3]
4. [COMPARISON CRITERION 4]

For each dimension:
- Highlight key similarities
- Note important differences
- Explain the significance of these differences

Also identify any unique elements that appear in only one document.

Conclude with an overall assessment of how these documents [RELATE TO SPECIFIC CONTEXT].

Document 1:
[PASTE FIRST DOCUMENT TEXT HERE]

Document 2:
[PASTE SECOND DOCUMENT TEXT HERE]

[Add more documents as needed]
```

Example:

```
I need you to compare the following 2 privacy policies.

Please analyze and contrast them across these dimensions:
1. Data collection practices
2. Data sharing with third parties
3. User rights and control options
4. Data retention policies

For each dimension:
- Highlight key similarities
- Note important differences
- Explain the significance of these differences

Also identify any unique elements that appear in only one policy.

Conclude with an overall assessment of how these policies compare in terms of user privacy protection.

Document 1:
[PASTE FIRST PRIVACY POLICY TEXT HERE]

Document 2:
[PASTE SECOND PRIVACY POLICY TEXT HERE]
```

## Specialized Analysis Templates

### Policy or Legal Document Analysis

This template is optimized for analyzing complex policy, legal, or regulatory documents:

```
I need you to analyze this [LEGAL/POLICY DOCUMENT TYPE] and break it down into clear, understandable terms.

For this analysis:
1. Explain the key obligations and rights established (What must or can each party do?)
2. Identify important definitions that affect how the document is interpreted
3. Highlight potential areas of concern or ambiguity
4. Note any exceptions, special conditions, or loopholes
5. Explain the practical implications for [RELEVANT STAKEHOLDER]

Please organize your response by sections of the document, using plain language explanations.

Here is the document:
[PASTE LEGAL/POLICY DOCUMENT TEXT HERE]
```

Example:

```
I need you to analyze this Terms of Service agreement and break it down into clear, understandable terms.

For this analysis:
1. Explain the key obligations and rights established (What must or can each party do?)
2. Identify important definitions that affect how the document is interpreted
3. Highlight potential areas of concern or ambiguity
4. Note any exceptions, special conditions, or loopholes
5. Explain the practical implications for an average user

Please organize your response by sections of the document, using plain language explanations.

Here is the document:
[PASTE TERMS OF SERVICE TEXT HERE]
```

### Technical Document Analysis

This template is designed for technical documentation, research papers, or specifications:

```
I need you to analyze this technical [DOCUMENT TYPE] about [TOPIC/TECHNOLOGY].

Please provide:
1. A high-level summary of the key technical concepts (accessible to someone with basic knowledge of [FIELD])
2. A breakdown of the [METHODOLOGY/ARCHITECTURE/SYSTEM] described
3. An analysis of the strengths and limitations of the approach
4. A glossary of the specialized terminology used
5. Practical applications or implications of this information

Where relevant, compare this approach to other common methods in the field.

Here is the document:
[PASTE TECHNICAL DOCUMENT TEXT HERE]
```

Example:

```
I need you to analyze this technical white paper about a new blockchain consensus mechanism.

Please provide:
1. A high-level summary of the key technical concepts (accessible to someone with basic knowledge of blockchain technology)
2. A breakdown of the consensus mechanism described
3. An analysis of the strengths and limitations of the approach
4. A glossary of the specialized terminology used
5. Practical applications or implications of this information

Where relevant, compare this approach to other common consensus mechanisms like Proof of Work and Proof of Stake.

Here is the document:
[PASTE TECHNICAL WHITE PAPER TEXT HERE]
```

### Pattern Recognition and Trend Analysis

This template helps identify patterns, trends, or themes across a document:

```
I need you to analyze this [DOCUMENT TYPE] and identify recurring patterns, themes, or trends.

Specifically, track and analyze:
1. [PATTERN/THEME TYPE 1] - Look for [SPECIFIC INDICATORS]
2. [PATTERN/THEME TYPE 2] - Look for [SPECIFIC INDICATORS]
3. [PATTERN/THEME TYPE 3] - Look for [SPECIFIC INDICATORS]

For each identified pattern:
- Provide 3-5 specific examples from the text
- Describe how the pattern develops or changes throughout the document
- Explain the potential significance or implications

Also note any interesting outliers or exceptions to these patterns.

Here is the document:
[PASTE DOCUMENT TEXT HERE]
```

Example:

```
I need you to analyze this collection of customer feedback and identify recurring patterns, themes, or trends.

Specifically, track and analyze:
1. User interface complaints - Look for mentions of navigation issues, confusion, or visual problems
2. Performance concerns - Look for mentions of speed, crashes, loading times, or reliability
3. Feature requests - Look for explicit suggestions or mentions of missing functionality

For each identified pattern:
- Provide 3-5 specific examples from the text
- Describe how the pattern develops or changes throughout the feedback collection
- Explain the potential significance or implications

Also note any interesting outliers or exceptions to these patterns.

Here is the document:
[PASTE CUSTOMER FEEDBACK TEXT HERE]
```

## Best Practices for Claude Document Analysis

1. **Be specific about document type**: Mention whether it's a legal contract, research paper, report, etc.
2. **Specify output structure**: Request clearly formatted responses with sections, bullet points, etc.
3. **Focus attention on priorities**: Tell Claude which aspects of the document are most important to analyze.
4. **Provide context**: Briefly explain why you're analyzing the document to help Claude provide relevant insights.
5. **Request direct quotes**: Ask Claude to quote relevant sections directly rather than just paraphrasing.
6. **Set appropriate scope**: For very long documents, consider focusing on specific sections or questions.
7. **Use specialized terminology**: Include field-specific terms to guide Claude toward the right type of analysis.
8. **Request comparisons**: Ask Claude to compare sections within a document or compare to standard practices.

## Handling Common Challenges

### For Very Long Documents

If your document exceeds Claude's context window:
- Split the document into logical sections and analyze each separately
- Prioritize the most important sections for analysis
- Consider asking Claude to focus on specific elements rather than the entire document
- Request a brief initial scan to identify the most important sections for deeper analysis

### For Highly Technical Content

For specialized technical documents:
- Ask Claude to create a glossary of technical terms alongside the analysis
- Request that complex concepts be explained in progressively greater detail
- Specify your level of familiarity with the subject matter
- Ask for analogies or comparisons to more familiar concepts

### For Ambiguous Content

When analyzing documents with unclear or ambiguous information:
- Request that Claude identify areas of ambiguity explicitly
- Ask Claude to provide alternative interpretations where text is unclear
- Request confidence levels for different interpretations
- Ask Claude to explain what additional information would help resolve ambiguities

By using these templates and practices, you can leverage Claude's document analysis capabilities to quickly extract insights, summarize complex information, and identify patterns across various document types.

