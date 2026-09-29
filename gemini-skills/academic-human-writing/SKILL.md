---
name: academic-human-writing
description: "Rewrite AI-sounding or overly formal academic text into natural, clear, student-level writing. Use when the user pastes an academic paragraph, essay section, or assignment and asks to make it sound more natural, less AI-generated, or more like a student wrote it. Preserves meaning, facts, citations, and structure; never invents content and never claims the output will beat AI detectors."
---
# Academic Human Writing

## Non-negotiables (check every rewrite against this list)

- Do not change the argument or its conclusion.
- Do not add facts, statistics, citations, or sources that weren't in the original.
- Do not remove evidence, citations, or required content.
- Do not change citation placement or citation format.
- Do not preserve or introduce grammar errors on purpose.
- Do not claim the output is "100% human," "undetectable," or "guaranteed to pass" any AI detector. If the user asks for that claim, say plainly that this can't be promised — the goal is natural writing, not detector evasion.
- Keep the level of formality appropriate to a university student, not a professional researcher, unless the source text is already at that level (e.g., a thesis).
- Preserve first-person voice if the original uses it. Never invent personal anecdotes or experience that wasn't stated.
- Preserve headings and section order unless the user asks to change them.

## AI-tell checklist — find and fix these

Scan the text for these patterns. Each one is a rewrite trigger.

**Generic openings**
- "In today's rapidly evolving world / society / digital age..."
- "Since the beginning of time..."
- "X has become increasingly important in recent years."

**Mechanical transitions (overused / stacked)**
- Furthermore, Moreover, Additionally, In conclusion, To sum up, Overall, It is important to note that

**Paragraph-summary tic**
- Every paragraph ending with a mini-restatement of what it just said.

**Hedge-and-inflate combo**
- Vague hedges ("many experts believe," "it could be argued") paired with inflated claims ("plays a crucial/vital role," "has a significant impact") with no specific support.

**Repetition**
- Same noun/verb reused across consecutive sentences where a pronoun or synonym would read more naturally.
- Every sentence in a paragraph following the same subject-verb-claim structure.

**Abstract padding**
- Sentences that state something true but empty ("Communication is an important part of daily life") that don't advance the argument.

If a sentence contains none of these and already reads like normal student writing, leave it alone. Don't rewrite for the sake of rewriting.

## Workflow

1. **Read the whole excerpt first.** Note subject, academic level, and whether it uses first person.
2. **Mark sentences against the AI-tell checklist above.** Only these need rewriting.
3. **Rewrite marked sentences:**
   - Vary sentence length — mix short and long.
   - Replace stacked transitions with plain connectors or none at all.
   - Cut paragraph-summary sentences that add nothing.
   - Replace vague claims with the specific point the source evidence actually supports — don't invent specifics that weren't there; if the original claim was vague, make the *wording* concrete, not the *facts*.
   - Fix grammar/punctuation issues you find along the way.
4. **Verify against the non-negotiables list** before returning output.
5. **Return the revised text.** Don't add commentary, a changelog, or a "here's what I changed" summary unless the user asked for one.

## Example

**Before (AI-sounding):**
> In today's rapidly evolving digital age, social media has become increasingly important in shaping public opinion. Furthermore, platforms such as Twitter and Facebook play a significant role in political discourse. Moreover, studies have shown that misinformation spreads rapidly online. In conclusion, social media's impact on democracy cannot be overstated.

**After (natural student writing):**
> Social media now shapes public opinion in ways traditional media never could. Platforms like Twitter and Facebook have become default spaces for political discussion, for better or worse. Research on misinformation shows it spreads faster online than corrections ever can (cite as in original). That gap between speed and accuracy is what makes social media's role in democracy worth taking seriously.

Note what changed: no generic opener, no stacked transitions, varied sentence length, the vague final claim replaced with a specific point tied to the actual evidence mentioned in the paragraph — not new evidence.

## Long documents

Process section by section. Keep a mental (or explicit) note of terminology already used so word choice stays consistent across sections — don't call the same concept by three different names.

## Output

Return only the revised text unless the user explicitly asks for an explanation of changes.
