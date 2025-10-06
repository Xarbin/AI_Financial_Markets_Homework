Original Directive prompt

I want you to generate a single Markdown file called directive.md. This file will be the full specification that Claude code execution can follow later to build my study tool in one shot. Your job here is only to output the directive, not the code.
Inside directive.md, include the following sections:
Objective – State clearly that the goal is a GUI-based study program that presents exactly 50 randomized multiple-choice questions each run, tracks score, gives immediate feedback, and helps me prepare for a game theory exam.


Scope – List the game theory concepts that must be covered (dominant strategies, Nash equilibrium, mixed strategies, expected utility, zero-sum, minimax, repeated games, Bayesian basics, mechanism design, etc.). Make it clear that all math problems must still be multiple choice with 1 correct answer and 3 distractors.


Question Bank – Provide at least 15 sample questions (mix of conceptual and math). Every question must have:


The question stem


Four labeled options (A–D)


The correct answer marked


Distractors that are plausible, not random junk


Include at least 5 calculation-style questions (e.g., finding equilibria, expected payoff) but still multiple choice.


Program Rules – State exactly how the quiz should function:


Randomly select 50 questions each session


Shuffle answers


Immediate feedback after each selection


Score summary at the end


GUI flow: Start screen → Quiz → Results


Default to the built-in sample bank if no upload is given


Implementation Notes –


Language: Python


GUI: Tkinter (stdlib, single-file simplicity)


Data model: in-memory list/dict for questions


Must validate: 4 unique choices, 1 correct answer, no blanks


Should run as a standalone .py script with no external dependencies


Your output must be only the Markdown file (directive.md) with the above structure filled out. Do not write any Python code, do not explain outside the file
