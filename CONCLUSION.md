# Lab 05 — Conclusion

<!--
Read this before you write.

This file is graded by your instructor, by hand, and it is worth 6 of the 15 points.

- Type it yourself. Do not use a chatbot, an AI assistant, an AI autocomplete or a "rewrite my
  text" tool for any part of it, not even for grammar. English that is plain and a little
  clumsy but yours is better than polished text that is not.
- Use your own numbers. Every number you quote must be one your own notebook printed. Copy
  the number exactly as it appeared. A number your notebook did not print is marked as wrong.
- Answer in your own words, about 80-200 words per question. A short answer that uses your
  numbers beats a long answer that could have been written by anyone.
- Delete these comment lines if you like. Keep the three headings and the last line.
-->

## 1. Which layer changed your results the most?

Give the numbers before -> after for that layer (correct / wrong / no answer, out of 20) and say
whether it changed what the agent *can do* or only what it *admits*. If no layer changed the
number of correct answers, say so and explain what the layers did change instead.

Workflow is one model call. Then code do the rest. Agent is a loop it call tools many times. On 15 fixed questions workflow got 13 right. Agent got only 9. Workflow used 3852 tokens. Agent used 19835 5 times more. Workflow failed on q21 and q22. Model wrote Nur-Sultan and Chimkent from question. Tool said unknown region. No second try. Only agent can do open questions. It got 7 of 9. I use workflow when question shape is known.

## 2. One failure the full harness did not fix

Pick one question that the full harness (layer 3) still gets wrong or refuses. Give its id
(q01 ... q20). Open its trace in the notebook: at which step did it go wrong, and what did
the model do instead? Name one thing you would add to the harness, and what it would cost
(extra model calls, tokens, time, or a new way to fail).

Layers helped little. Bare agent got 16 of 24. All 3 layers got 18. Layer 1 and 2 fixed q23 and q24. But q21 and q22 became wrong. Layer 3 stopped q18. Agent wrote 0.55 and number was not in tool results. It wrote same thing again. So no answer now. Model calls went from 51 to 74. Tokens went from 39500 to 60100. Time went from 92 to 107 seconds. Four answers still wrong. They are q08 q11 q17 and q21.

## 3. Workflow or agent for the monthly ranking?

Dala Insight wants to publish every month which region is highest and lowest one
indicator in one year. Would you ship the fixed workflow or the agent? Use the accuracy, the
number of model calls, the tokens and the time you measured in Part 1. Then say in one sentence
what kind of question would make you choose the other one.

Notes helped more. Score went from 18 to 21 of 24. Wrong answers went from 4 to 1. q11 q18 and q22 are right now. But q08 and q17 are not wrong anymore. They are just no answer. Ranking is still hard for model. q21 is still wrong. Notes cost more. Tokens went from 60000 to 73000. Time went from 107 to 135 seconds. Model is small. Math is bad sometimes. I check every answer by hand before use.

---

I wrote this file myself, without any AI tool.
