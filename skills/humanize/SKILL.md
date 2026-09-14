---
name: humanize
description: >-
  Use whenever drafting or substantially revising human-facing prose, including emails,
  posts, articles, documentation, product and UI copy, essays, scripts, and fiction,
  even when the user does not explicitly ask to humanize it. Also use when asked to
  humanize, de-AI, make text less robotic or generic, match an existing voice, or audit
  a draft for recognizable AI-writing patterns. Apply it alongside any more specific
  writing skill. Do not use for code, structured data, or purely mechanical spelling
  and grammar correction.
---

# Humanize

Make the text feel chosen rather than generated. Preserve what the author means; improve
how deliberately and naturally they say it.

Humanization is an editorial task, not a word-substitution task. Surface cleanup helps,
but generic structure, over-explanation, and overly tidy reasoning are often stronger
signals than any individual word or punctuation mark.

## Route the task

- **Foundation** applies to every draft or substantial rewrite of human-facing prose.
  When another skill owns the genre or surface, use both: the specific skill controls
  requirements and format; this skill controls authorial quality and naturalness.
- For technical documentation, use `documentation` when it is available. It owns the
  reader's task, information architecture, established terminology, commands, code,
  and technical accuracy. Never change those elements to make the prose sound smoother.
- **Rewrite** is the default. Edit or draft the text and return the result.
- **Audit** applies when the user asks to detect, scan, flag, critique, or explain AI-like
  writing without asking for a rewrite. Read
  [references/editorial-patterns.md](references/editorial-patterns.md), report the
  observed patterns, and stop without rewriting.
- For a standard or deep rewrite, also read
  [references/editorial-patterns.md](references/editorial-patterns.md). A light edit can
  use this file alone.
- For fiction, scripts, personal essays, case studies, or any text whose effect depends
  on narrative structure, also read
  [references/narrative-revision.md](references/narrative-revision.md) before rewriting.
- If the user supplies samples of their writing, treat those as the primary voice
  reference. This skill provides diagnostics, not a replacement personality.

Proceed without questions when the draft and request provide enough context. Ask only
when a missing fact, audience, or intended meaning would materially change the result.

## Preserve the authorial contract

Before editing, determine privately:

- the text's job, audience, language, medium, and desired level of formality;
- the claims, facts, numbers, names, links, quotations, citations, commitments, and calls
  to action that must survive;
- the author's existing attitude: confident, skeptical, excited, annoyed, dry, warm,
  technical, playful, or mixed, including useful digressions and their level of polish;
- any explicit length, structure, terminology, or formatting constraints.

Keep the source language unless asked to translate. Preserve domain terms when they are
the clearest terms. Never invent personal experience, anecdotes, emotions, opinions,
sources, named references, or facts to make a draft seem human. Do not turn uncertainty
into certainty or add vulnerability the author did not express.

## Diagnose before rewriting

Look for the few patterns that most weaken this particular draft. Common problems:

- **Generic decisions:** the text could have been written for almost any person,
  company, or situation.
- **Over-explanation:** it announces the point, makes the point, interprets it, and then
  summarizes it again.
- **Artificial balance:** every topic receives equal weight; every paragraph has a tidy
  counterpart; every argument resolves cleanly.
- **Template structure:** scene-setting preamble, numbered coverage, generic takeaway,
  and a conclusion that repeats the introduction.
- **Uniform rhythm:** similar sentence lengths, paragraph sizes, openings, transitions,
  and clause patterns.
- **Over-segmented thought:** one continuous thought is split into a row of tidy declarative
  sentences or independent clauses, so every qualification receives the same clean pause.
- **Synthetic texture:** abstract nouns, stock metaphors, generic sensory detail,
  ceremonial transitions, inflated praise, or intensity unsupported by the content.
- **Missing judgment:** the draft lists considerations but never reveals what matters,
  what does not, or what the author actually thinks.
- **Voice mismatch:** vocabulary, humor, politeness, or certainty that does not fit the
  author, audience, or medium.

Do not apply a blacklist mechanically. A phrase is a problem only when it is vague,
predictable, redundant, or wrong for the voice. Em dashes, headings, lists, transitions,
and polished grammar are all legitimate when they serve the text.

## Choose the depth of the edit

Use the least invasive level that can solve the problem:

- **Light:** keep the order and claims; remove stiffness, repetition, and awkward rhythm.
- **Standard:** reorganize paragraphs, change emphasis, cut generic framing, and rewrite
  sentences. Use this by default for requests to humanize a draft.
- **Deep:** reconsider the argument, progression, examples, scenes, or ending. Use when
  surface edits would leave the underlying text generic, or when the user asks for a
  substantial rewrite.

Preserve strong original lines. Do not rewrite merely to demonstrate activity.

## Rewrite the decisions first

For standard and deep edits:

1. State the real point early enough for the medium. Remove throat-clearing that delays it.
2. Establish hierarchy. Give more space to what matters and compress what is obvious.
3. Replace generic coverage with concrete, supported choices: a real constraint, a precise
   example already present in the source, a meaningful exception, or a clear tradeoff.
4. Let the author take a position when the source supports one. Calibrate confidence
   honestly; retain uncertainty and mixed feelings where they exist.
5. Group paragraphs by thought and emphasis rather than by a perfectly repeated template.
6. Remove explanations the reader can infer. Do not attach a lesson or summary to every
   example, section, or ending.
7. Allow asymmetry. A short aside, a one-line paragraph, an abrupt but clear transition,
   or an unresolved qualification can be natural when the thought warrants it.
8. End when the work is done. Avoid a ceremonial recap or inspirational final sentence
   unless the genre expects one.

Natural variation must follow meaning. Do not add randomness, tangents, contradictions,
or arbitrary roughness.

## Rewrite the prose second

- Prefer concrete nouns and active verbs over abstract packaging.
- Protect specific facts. Do not smooth a useful name, number, date, mechanism, or
  consequence into a vague claim about importance or improvement.
- Use the shortest wording that preserves the intended nuance and voice.
- Vary sentence length and syntax according to emphasis. A short sentence should land a
  point; it should not appear on a timer.
- Read adjacent sentences as a unit. When two or three clauses belong to the same spoken
  thought and none deserves its own emphasis, connect them with an explicit relationship
  such as `and`, `but`, `while`, or `though` instead of presenting each as a separate point.
- Vary paragraph length according to the size of the thought.
- Cut meta-introductions, generic transitions, duplicated qualifiers, inflated adjectives,
  empty intensifiers, and conclusions that merely restate the preceding line.
- Keep contractions, fragments, colloquialisms, technical shorthand, humor, or profanity
  only when they fit the author and context.
- Prefer a specific familiar word to a conspicuous synonym. Do not use a thesaurus to
  simulate personality.
- Repeat the correct term when consistency matters. Do not rotate between near-synonyms
  merely to avoid repetition.
- Prefer plain verbs, including `is`, `has`, and `does`, when a more impressive verb would
  make the sentence less precise.
- Use idioms only when they sound native in the target language and region.
- Preserve useful formatting. Break a repetitive list into prose, or prose into a list,
  only when readability improves.
- Keep punctuation organic. Never replace every em dash, semicolon, colon, or parenthesis
  just because it is associated with AI writing.

## Match an existing voice

When voice samples are available, infer tendencies rather than copying catchphrases:

- sentence and paragraph length;
- directness, warmth, humor, and tolerance for bluntness;
- vocabulary level and use of jargon;
- how the author qualifies claims and expresses uncertainty;
- preferred openings, transitions, punctuation, and endings;
- which imperfections are authentic and which are merely errors.

Preserve occasional rough edges that belong to the author. Do not manufacture typos,
bad grammar, false starts, fake quotes, or inconsistent facts.

## Final pass

Read the result as a skeptical editor and check:

- Could this text only belong to this author, audience, and situation, or is it still
  interchangeable?
- Does each paragraph add information, judgment, tension, or movement?
- Is any point explained twice?
- Are the rhythm and structure varied for a reason?
- Are any neighboring sentences really one thought cut into polished pieces?
- Did the rewrite preserve every material fact, constraint, citation, and commitment?
- Did it introduce an anecdote, belief, reference, or experience the author never supplied?
- Does the ending stop naturally?

For a standard or deep rewrite, run the portability, evidence, deletion, rhythm, and
ending checks in [references/editorial-patterns.md](references/editorial-patterns.md).
For narrative work, also run the review in
[references/narrative-revision.md](references/narrative-revision.md).

If the answer exposes a problem, fix it once. Do not keep polishing until the author's
voice disappears.

## Output

Return the finished text directly unless the user asks for commentary, alternatives, a
diff, or an explanation. Preserve the requested format and approximate length. Do not
preface the rewrite with a summary of what changed or append a change log unless asked.

For an audit, do not score the draft or guess whether a human or model wrote it. For each
material issue, provide the pattern name, a short excerpt, why it weakens this text, and a
concise revision direction. Group repeated instances of the same pattern. Distinguish a
real pattern from a phrase that merely appears on a watch list.

Do not promise that a text is undetectable or optimize blindly for a detector score.
Detection is probabilistic and model-specific; the useful target is credible authorship,
semantic fidelity, and writing that makes deliberate choices.
