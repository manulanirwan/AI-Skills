---
name: study-helper
description: "Turn pasted class notes on any subject into a structured study guide. Use this whenever Manula pastes notes and asks for a summary, exam prep, or key points to memorize. Produces a clean, printable document with a structured summary, 10 key points, 5 likely exam questions with model answers, and plain explanations of hard concepts."
---
# Study Helper

## Purpose

Convert raw pasted notes into a printable study guide. Output must be clean, direct, and free of filler.

## When to use

Trigger this skill when Manula pastes notes from any subject and asks for a summary, study guide, key points, or exam prep.

## Output structure

Always produce these four sections, in this order, with clear Markdown headings:

### 1. Structured Summary
- Reorganize the notes under clear subheadings based on the topics present.
- Use short sentences and bullet points.
- Keep all facts, names, dates, numbers, and definitions from the original notes.
- Do not add outside information not present in the notes.
- Cut repetition and filler.

### 2. 10 Key Points to Memorize
- Numbered list, exactly 10 items unless the notes are too short to support 10 distinct points (state this if so).
- Each point should be one short, standalone fact or concept.
- Order by importance, most important first.

### 3. 5 Likely Exam Questions with Model Answers
- Exactly 5 questions.
- Mix question types where the notes support it (definition, explain, compare, apply).
- Each question gets a concise model answer directly below it, based only on the notes.
- Format:
  **Q1: [question]**
  A: [model answer]

### 4. Simple Explanations of Difficult Concepts
- Identify concepts in the notes that are technical, abstract, or likely to confuse a student.
- Explain each in plain, simple language.
- If nothing in the notes is genuinely difficult, say so briefly instead of inventing complexity.

## Formatting rules

- Use `#`/`##`/`###` headings so the output is scannable and printable.
- Use bullet points and numbered lists, not dense paragraphs.
- No em dashes.
- No banned filler words (e.g. delve, deep dive, leverage, framework, synergy, holistic, cutting-edge, innovative, unpack, ideation, insightful, compelling, transform, elevate, empower, optimize, disruptive, ecosystem, paradigm, subsequently, remnant, foster, seamless, mission-critical, turnkey, drill down, synthesis, realm, captivating).
- No "in conclusion" or "to sum up" type phrasing.
- Address Manula as "you" and "your" where narration is needed.
- Keep sentences short and active.
- Do not add facts, examples, or context that were not in the pasted notes.

## Steps

1. Read the pasted notes fully before writing anything.
2. Identify the subject and main topics to build the summary headings.
3. Write the Structured Summary first.
4. Extract the 10 most important points from the summary.
5. Write 5 exam questions with model answers grounded only in the notes.
6. Scan the notes for genuinely hard concepts and explain them simply.
7. Check the whole output against the formatting rules before finishing.

## Notes

- If pasted notes are very short (e.g. a few lines), scale down section 2 and 3 rather than padding with invented content, and say so.
- If notes cover multiple unrelated subjects, split the Structured Summary by subject with top-level headings per subject, and produce one combined set of 10 points, 5 questions, and difficult-concept explanations covering all subjects together (unless Manula asks for them separated by subject).
