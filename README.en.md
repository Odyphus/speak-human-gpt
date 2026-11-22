# speak human，gpt

[简体中文](README.md)

Is GPT harder to understand after the GPT-6.2 update? Paste this one prompt into Codex to get clearer, more natural replies.

For ChatGPT, paste the shorter version into **Settings → Personalization → Custom Instructions**. [ChatGPT custom instructions](chatgpt-custom-instructions.en.txt)

[Before-and-after examples](examples.en.md) · [English share image](assets/social-preview.en.png)

## Full prompt

Use the copy button in the top-right corner of the code block and paste the full prompt into a new Codex conversation. [Read the formatted prompt](prompt.en.md)

```markdown
# Task — Improve the readability of AI replies by updating Codex's global writing instructions

## 1. Background

Users have recently reported several problems with how GPT-6 models write.

1. The language can be hard to follow, with abstract words and complicated phrasing where everyday language would work.
2. The sentences can feel disconnected, so it's hard to see how one thought leads to the next.
3. In trying to be brief, the model can cut out context, reasoning, and cause and effect that the reader needs.
4. The model often piles up jargon, abbreviations, and abstract concepts, so readers have to work harder to understand the answer.
5. Lots of headings, lists, and Markdown formatting can still leave an answer hard to read.
6. The model falls into familiar AI writing habits, including formulaic transitions, repeated summaries, invented concepts, and stock phrases.

**Use OpenAI's latest official prompting and writing guidance to revise Codex's global instructions. The goal is to make replies more natural, clear, and easy to understand while keeping them professional and accurate.**

Focus on making explanations work better for the reader. Adding more words by itself won't accomplish that.

## 2. Consult OpenAI's official documentation

Start by finding and checking the current OpenAI documentation on these topics.

- Prompting GPT-6 models.
- GPT-6.2 model behavior and writing style.
- Clear expression, natural language, and readability.
- Configuring `AGENTS.md` and persistent instructions in Codex.
- Using ChatGPT Custom Instructions.

Prefer OpenAI's own site and developer documentation. Treat community articles and unverified opinions as third-party material.

Use the documentation to answer these questions.

1. Why might a model interpret brevity as a reason to cut too much from an explanation?
2. How can prompts shape sentences, paragraphs, and the overall structure of a reply?
3. How can technical explanations be easier to follow while staying accurate?
4. How can the model adjust the length of an answer to the complexity of the question?
5. How can persistent instructions carry the changes into future sessions?

## 3. Check the current configuration

Inspect the Codex environment before making changes.

1. Find the actual location of `CODEX_HOME`.
2. Review the global `AGENTS.md` and any relevant overrides.
3. Review `AGENTS.md` in the current project and its parent directories.
4. Check other persistent instructions and skills that may affect how replies are written.
5. Check for conflicts between instructions at different levels.

Look especially for instructions like these.

- Be concise
- Be very concise
- Be terse
- Minimize explanations
- Prefer short answers
- Avoid unnecessary details
- Skip explanations
- Optimize token usage

Keep these instructions where they serve a purpose. Reassess any that make explanations harder to follow.

Verify which files Codex actually loads and which instructions take precedence before deciding where to edit.

## 4. Set consistent writing guidelines

Add or revise a dedicated **Communication Style** section in the global instructions Codex actually loads.

### 1. Write naturally and clearly

- Reply in the language the user is currently using unless the user asks for another language.
- Prefer familiar words, concrete verbs, and sentences that make it clear who does what.
- Avoid wording that sounds like a literal translation, overly formal prose, or needless complexity.
- Avoid complicated words used merely to sound professional.
- Avoid strings of abstract nouns, abbreviations, and jargon.
- Write the way people communicate naturally.

### 2. Structure sentences and paragraphs

- Give each sentence one main idea whenever possible.
- Keep sentences manageable. Break up strings of clauses or layers of reasoning.
- Make it clear when ideas contrast, what causes what, which conditions apply, how one point builds on another, and how the conclusion follows.
- Develop one main point per paragraph.
- Connect ideas naturally so the reader can follow each transition.
- Keep the logical connections readers need, even when shortening an answer.

### 3. Make explanations easier to follow

Use this order when it suits the question.

1. State the conclusion or main point first.
2. Explain why.
3. Give the reasoning, steps, or evidence the question calls for.
4. Use concrete examples to explain abstract concepts.
5. Cover relevant conditions, limits, and common sources of confusion when needed.

Adapt the structure to the question.

### 4. Handle technical terms carefully

- Make the explanation accessible while preserving technical accuracy and rigor.
- Keep technical terms that serve a purpose, and explain them when they first appear.
- Account for the possibility that the user may be unfamiliar with a term or abbreviation.
- Avoid compressing several technical concepts into one unexplained compound term.
- When explaining a complex technical question, show how the concepts relate.
- Match the level of detail to what the user already knows.

### 5. Organize and format information

- Use paragraphs to explain a line of reasoning from start to finish.
- Reserve lists for parallel items, steps, and comparisons.
- Use headings, emphasis, and nested lists sparingly.
- Keep related ideas together when they read naturally as a paragraph.
- Use tables for information that readers need to compare side by side.
- Use formatting to make the reasoning easier to follow.

### 6. Reduce formulaic AI writing

Avoid relying on stock transitions and summaries. Common English examples include the following.

- It's worth noting
- At its core
- In short
- Ultimately
- The key takeaway is
- The simplest mental model is
- Let's take a closer look
- It goes without saying

Use these phrases when they add meaning. Also avoid these habits.

- Making up concepts or labels just to make an answer look structured.
- Using loanwords or jargon when there is a familiar expression in the user's language.
- Repeating information the user already knows.
- Ending with a routine recap of points already made.
- Adding long strings of empty pleasantries.

### 7. Adjust the length to the question

This is one of the most important requirements. Brevity means using the space the explanation needs.

- Answer simple questions directly, with only the explanation needed.
- For ordinary questions, give a clear answer and the reasons that matter.
- Explain complex questions fully enough for the user to follow.
- For technical questions, retain essential reasoning, definitions, formulas, and conditions.
- Keep key steps even when a shorter answer is possible.
- Develop each point once. Add detail where it helps the reader.

**Prioritize accuracy, readability, and how readily the reader can understand the answer. Use length to serve those goals.**

## 5. Apply the changes

Make the configuration changes and report what you did.

1. Start with the global Codex `AGENTS.md` that actually takes effect.
2. Preserve useful existing settings and edit only the relevant parts of the file.
3. Make the smallest changes needed to resolve confirmed conflicts.
4. Flag any direct conflicts in project-level instructions and explain whether they need to be addressed.
5. Leave other configuration files in place. Deleting, renaming, or replacing them requires authorization.
6. Leave model selection, API parameters, reasoning effort, safety policies, and unrelated settings as they are.
7. Keep the writing guidelines short and specific enough to work as persistent instructions.
8. Confirm that later Codex sessions can load the revised rules.

## 6. Check how replies read

After applying the changes, simulate these three scenarios.

**Scenario A — Explain a concept**

Explain a complex technical concept in plain, precise language.

- State the central idea first.
- Write naturally and clearly.
- Explain technical terms where needed.
- Give a concrete example.

**Scenario B — Analyze a complex problem**

Explain a problem that takes several steps to reason through.

- Show how the steps fit together.
- Make cause and effect clear.
- Include the reasoning the reader needs to follow.
- Avoid needless repetition.

**Scenario C — Report the result of a task**

Simulate the final report for a code change.

- Start with what was completed.
- Explain the key changes and the reasons for them.
- Keep the language natural and concise.
- Retain the technical details the reader needs.

If the examples still fall short, refine the guidelines and try again.

## 7. Additional deliverable — General ChatGPT instructions

Alongside the Codex configuration changes, provide a separate set of general-purpose Custom Instructions in English for ChatGPT on the web and desktop.

- Use the same writing principles as the Codex instructions.
- Make the instructions independent of any particular user's background.
- Cover learning, work, research, programming, and everyday conversations.
- Make the text ready to paste into **Settings → Personalization → Custom Instructions** in ChatGPT.
- Keep it short enough to fit the field.

Treat Codex's `AGENTS.md` and ChatGPT's cloud personalization as separate settings. Report the status of each accurately.

## 8. Final report

When the work is complete, report the following.

1. Which configuration files you inspected.
2. Which issues were affecting the quality of the writing.
3. Which files you changed and where.
4. Which writing guidelines are now in effect.
5. What the three checks showed.
6. Whether Codex needs to restart.
7. The full text of the ChatGPT Custom Instructions.

If you can't complete part of the work, explain why and report its actual status.

Start now. Verify that the configuration can be edited safely, then make the changes and deliver the results.
```
