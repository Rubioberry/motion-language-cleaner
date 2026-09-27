---
name: motion-language-cleaner
description: Turns messy discussion notes into one affirmative draft main motion and optional draft amendments. Use after a committee talks in circles and the clerk needs language the chair can state. Labels every line draft. Does not rule the motion in order or record a vote.
license: MIT
compatibility: Claude, Codex, Cursor, OpenCode, Lovable
allowed-tools: read
inputs:
  - name: source
    type: text
    required: true
    description: Messy discussion notes, chat, or a rambling “we should” paragraph to turn into draft motion language
outputs:
  - name: artifact_markdown
    type: markdown
    description: DRAFT main motion in the affirmative, optional draft amendments, leftovers, and open questions
  - name: artifact_json
    type: json
    description: status, main_motion, amendments, leftovers, open_questions, not_done
side_effects: none
touches:
  - user_input
permissions:
  network: deny
  files: deny
  workspace: read
  secrets: deny
---

# Motion Language Cleaner

## When to use
Use when notes from debate must become a single motion in the affirmative.

## Workflow
1. Read only the provided source.
2. State the decision people appear to want, in one affirmative sentence starting with "I move that…"
3. If they wanted changes to that sentence, list each as a draft amendment ("I move to amend by…").
4. List leftovers that are discussion, not motion language.
5. Flag ambiguity. Do not invent dollar amounts, dates, or ordinance numbers.
6. Mark the whole output DRAFT.

## Input
Discussion notes, chat, or a rambling "we should" paragraph.

## Output
Draft main motion, draft amendments, leftovers, open questions.
JSON with the same fields.

## Guidelines
- Affirmative phrasing only.
- One main motion.
- This is not a ruling that the motion is in order.
- This skill does not put the question or record a vote.
