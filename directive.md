# directive.md

## Objective
The goal is to build a **GUI-based study program** that presents **exactly 50 randomized multiple-choice questions** per session to help prepare for a **Game Theory exam**.  
The program must:
- Track score and progress in real-time.  
- Give **immediate feedback** after each question (showing whether the selected answer was correct and why).  
- Provide a **final score summary** and percentage at the end.  
- Be **interactive**, user-friendly, and run in a single standalone Python file.

---

## Scope
The study tool must cover key **Game Theory concepts**, ensuring both conceptual understanding and mathematical problem-solving practice.  
Concepts to include:
- Dominant and dominated strategies  
- Nash equilibrium (pure and mixed strategies)  
- Best responses  
- Expected utility and payoffs  
- Zero-sum and non-zero-sum games  
- Minimax and maximin principles  
- Repeated games and the Folk Theorem  
- Bayesian games (incomplete information basics)  
- Mechanism design and incentive compatibility  
- Prisoner’s Dilemma and coordination games  
- Pareto efficiency  
- Evolutionary stable strategies (ESS)  

**All questions, including mathematical ones, must be multiple choice** with:  
- Exactly 4 options (A–D)  
- 1 correct answer  
- 3 plausible distractors (not random nonsense)  

At least **5 questions must require calculations**, such as computing equilibria, payoffs, or expected values.

---

## Question Bank
Below is the **sample built-in question bank (15 questions)**.  
Claude code execution should expand this into a larger pool when generating the full tool.

---

### 1. Dominant Strategy
**Q1.** In a game, if one strategy always provides a higher payoff regardless of what the opponent does, it is called:  
A. Nash equilibrium  
B. Dominant strategy  
C. Best response  
D. Mixed strategy  
✅ **Correct:** B  

---

### 2. Pure Strategy Equilibrium
**Q2.** In a 2x2 payoff matrix, a pure strategy Nash equilibrium occurs when:  
A. Both players choose random strategies  
B. Each player’s strategy is a best response to the other’s  
C. Both players have dominant strategies  
D. No player can deviate unilaterally  
✅ **Correct:** B  

---

### 3. Mixed Strategy Definition
**Q3.** A mixed strategy is defined as:  
A. A randomization over pure strategies  
B. A guaranteed win condition  
C. A strategy that minimizes losses  
D. The same as a dominant strategy  
✅ **Correct:** A  

---

### 4. Expected Utility
**Q4.** If a player values a 50% chance at \$10 and a 50% chance at \$0 as \$4, their expected utility is:  
A. 4  
B. 5  
C. 10  
D. 2  
✅ **Correct:** A  

---

### 5. Zero-Sum Concept
**Q5.** In a zero-sum game:  
A. Both players can win  
B. Total payoffs sum to zero  
C. Both players lose equally  
D. Only mixed strategies exist  
✅ **Correct:** B  

---

### 6. Calculation – Best Response
**Q6.** Player A’s payoffs are (3,1) for Player B’s strategies (L,R). If B plays L with probability 0.6, what is A’s expected payoff for strategy 1?  
A. 2.2  
B. 1.8  
C. 2.0  
D. 3.0  
✅ **Correct:** A  

---

### 7. Calculation – Expected Payoff
**Q7.** Player X earns 10 with probability 0.3, and 4 with probability 0.7. The expected payoff is:  
A. 5.8  
B. 6.2  
C. 7.2  
D. 4.0  
✅ **Correct:** A  

---

### 8. Prisoner’s Dilemma
**Q8.** In the classic Prisoner’s Dilemma, the dominant strategy for both players is to:  
A. Cooperate  
B. Defect  
C. Randomize  
D. Stay silent  
✅ **Correct:** B  

---

### 9. Repeated Games
**Q9.** Cooperation in repeated Prisoner’s Dilemma is possible if:  
A. Players are short-sighted  
B. Discount factor is low  
C. Players value future payoffs  
D. Payoffs are symmetric  
✅ **Correct:** C  

---

### 10. Bayesian Game
**Q10.** A Bayesian game differs from a standard game because:  
A. It involves infinite players  
B. Payoffs are unknown  
C. Players have incomplete information  
D. Players move simultaneously  
✅ **Correct:** C  

---

### 11. Calculation – Mixed Strategy Equilibrium
**Q11.** If Player A is indifferent when Player B plays Left with probability p, and A’s payoffs are (3,1) vs (0,2), find p.  
3p + 0(1−p) = 1p + 2(1−p)  
A. 0.4  
B. 0.5  
C. 0.6  
D. 0.7  
✅ **Correct:** C  

---

### 12. Mechanism Design
**Q12.** Mechanism design focuses on:  
A. Predicting strategic behavior  
B. Designing rules to achieve desired outcomes  
C. Repeated game analysis  
D. Solving mixed strategy equilibria  
✅ **Correct:** B  

---

### 13. Calculation – Minimax
**Q13.** In a zero-sum game, Player A’s payoffs for strategies (A1, A2) are [4, -2] against B’s best responses. The minimax value is:  
A. -2  
B. 1  
C. 2  
D. 4  
✅ **Correct:** B  

---

### 14. Pareto Efficiency
**Q14.** An outcome is Pareto efficient if:  
A. No one can be made better off without making someone worse off  
B. Everyone gains equally  
C. Total payoff is maximized  
D. One player dominates  
✅ **Correct:** A  

---

### 15. Calculation – Expected Utility
**Q15.** If U(A)=0.5, U(B)=0.8, and the player chooses A with probability 0.4, expected utility is:  
A. 0.64  
B. 0.66  
C. 0.62  
D. 0.70  
✅ **Correct:** B  

---

## Program Rules
1. **Question Selection**
   - Randomly select **50 questions** per session from the available pool.  
   - Shuffle **answer choices (A–D)** each time.  

2. **Feedback**
   - After each response, immediately display whether the answer was correct.  
   - Optionally show a one-line rationale (can be minimal).  

3. **Score Tracking**
   - Maintain running score and progress (e.g., “Question 10/50, Score: 7”).  
   - Show percentage and number correct at the end.  

4. **GUI Flow**
   - **Start Screen:** “Start Quiz” button.  
   - **Quiz Screen:** Display question text, 4 radio buttons, “Submit” button.  
   - **Feedback Screen (inline):** Highlight correct answer.  
   - **Results Screen:** Show total correct, percentage, and “Restart” option.  

5. **Default Bank**
   - Use the **built-in sample bank** above if no external question file is provided.  

---

## Implementation Notes
- **Language:** Python 3  
- **GUI Framework:** Tkinter (standard library only)  
- **Data Model:** In-memory list/dict of question objects  
  - Each question includes: `"question"`, `"options"`, `"correct_answer"`, `"explanation"` (optional).  
- **Validation Requirements:**
  - Each question must have exactly 4 unique options.  
  - One and only one correct answer.  
  - No blanks or missing fields.  
- **Program Structure:**
  - Single `.py` file.  
  - No external dependencies.  
  - Designed for local standalone execution (`python game_theory_quiz.py`).  
- **Interface Goals:**
  - Minimal, clean layout.  
  - Clearly readable question text.  
  - Progress indicator and immediate feedback.  
  - End-of-quiz summary with “Retry” option.

---

**End of directive.md**
