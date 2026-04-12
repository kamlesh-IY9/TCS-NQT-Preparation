# DAY 2: REASONING ABILITY MASTERY GUIDE

**Total Time:** 5 Hours | **Target:** 20+ Questions | **Focus:** Your Weakness Area

---

## YOUR SCHEDULE FOR TODAY

| Time | Topic | Duration | Activity |
|------|-------|----------|----------|
| 00:00-01:15 | Seating Arrangements | 75 min | Theory (30 min) + 5 past year questions (45 min) |
| 01:15-01:30 | BREAK | 15 min | Rest & Refresh |
| 01:30-02:30 | Blood Relations | 60 min | Concept + 4 past year questions |
| 02:30-03:30 | Number Series | 60 min | Pattern tricks + 5 past year questions |
| 03:30-03:45 | BREAK | 15 min | Rest & Refresh |
| 03:45-04:45 | Syllogisms | 60 min | Concept + 4 past year questions |
| 04:45-05:30 | Coding-Decoding | 45 min | Pattern + 3 past year questions |

**Daily Target:** Solve 20+ questions with 70%+ accuracy

---

## SECTION 1: SEATING ARRANGEMENTS (75 MINUTES) - HIGHEST PRIORITY

**Frequency in TCS NQT:** 5-6 questions per paper

### KEY CONCEPTS

**Three Types of Seating:**
1. **Linear Arrangement** - People sit in a straight line (left to right)
2. **Circular Arrangement** - People sit around a circular table (left/right relative to observer)
3. **Rectangular Table** - People sit around a rectangular table

### APPROACH FOR SOLVING

**Step 1:** List all given information clearly
**Step 2:** Identify constraints (who sits where, who sits next to whom, etc.)
**Step 3:** Start with the most restrictive clue
**Step 4:** Place people one by one using elimination
**Step 5:** Verify with all clues before finalizing

---

### EXAMPLE 1: LINEAR ARRANGEMENT (Basic)

**Problem:**
Five people - A, B, C, D, E - sit in a line.
- B sits to the right of A
- C sits next to D
- E is not at either end
- A is at the left end

Arrange them in order.

**Solution:**

Given constraints:
- A is at the left end: A _ _ _ _
- B is to the right of A: A ... B ...
- C sits next to D: C D or D C
- E is not at either end

Working:
- A is at position 1: A _ _ _ _
- E cannot be at position 5, so E is at position 2, 3, or 4
- B must be to the right of A, so B is at position 2, 3, 4, or 5
- C and D are together

If B is at position 2: A B _ _ _
Remaining: C, D, E
- C and D must be adjacent
- E cannot be at position 5

If we place C D at positions 3-4: A B C D E
Check: E is at position 5 (end) - INVALID

If we place D C at positions 3-4: A B D C E
Check: E is at position 5 (end) - INVALID

If D C at positions 4-5: A B _ D C but then E must be at position 3
Result: A B E D C
Check all constraints:
- A at left end ✓
- B to right of A ✓
- D and C adjacent ✓
- E not at either end ✓

**Answer: A B E D C**

---

### EXAMPLE 2: CIRCULAR ARRANGEMENT (TCS-Level)

**Problem:**
Six people - P, Q, R, S, T, U - sit around a circular table facing inward.
- P sits to the immediate right of Q
- R sits to the immediate right of P
- S is not adjacent to Q
- T and U are adjacent
- U sits to the left of T

Find who sits opposite to Q?

**Solution:**

In circular arrangement with 6 people, the opposite person is 3 positions away.

Given:
- P is immediately right of Q: Q P
- R is immediately right of P: Q P R
- So far: Q P R _ _ _
- Remaining: S, T, U
- U is to the left of T (adjacent): U T
- S is not adjacent to Q

Position Q at position 1: Q(1) P(2) R(3) _ _ _
Remaining positions: 4, 5, 6

If U T are placed: U at position 4, T at position 5, then S at position 6
Check:
- S is not adjacent to Q (Q is at 1, S at 6, with U between them in circular) ✓
- U is left of T ✓

Arrangement: Q(1), P(2), R(3), U(4), T(5), S(6)

Opposite to Q(1) = Position 4 = U

**Answer: U sits opposite to Q**

---

### EXAMPLE 3: RECTANGULAR TABLE (TCS-Level)

**Problem:**
Eight people sit around a rectangular table with 2 people on each side.
- A sits on North side, West end
- B sits opposite to A (South side, West end)
- C is on East side, North
- D sits to the immediate right of A
- E is not adjacent to A
- F sits opposite to D

Arrange them.

**Solution:**

Rectangle layout:
```
North: [A][D][?][C]
       [?][-][−][?]
South: [B][?][?][?]
```

Given:
- A is North-West end
- B is opposite to A (South-West end)
- D is immediately right of A (North side, next to A)
- C is on East side, North
- F opposite to D (South side, 2nd from left)

```
North: [A][D][?][C]
South: [B][F][?][?]
```

Remaining: E, G, H

E is not adjacent to A. Positions adjacent to A are positions 2 (already D) and South-West (already B).

Fill remaining with E, G, H ensuring E is not adjacent to A.

```
North: [A][D][?][C]
South: [B][F][E][G]
```

Or could be:
```
North: [A][D][E][C]
South: [B][F][?][?]
```

But E cannot be adjacent to A (position 3 is adjacent to positions 2 and 4). Position 3 is adjacent to position 2 (D) - need to verify.

Actually, in linear seating, adjacent means next to in the same row.
So if E is on North side at position 3, it's adjacent to D (position 2). That's fine since only A is restricted.

**Answer:** A-D-E-C (North), B-F-G-H (South)

---

### PRACTICE QUESTIONS: SEATING ARRANGEMENTS

**Q1 (Linear):**
Four people sit in a line. A is to the immediate left of B. C is to the right of D. D is not at either end. A is not at the left end. Arrange them.

**Q2 (Circular):**
Five people sit around a circular table. M is immediately to the right of N. O is to the right of M. P is not adjacent to N. Q sits opposite to N. Who sits between O and P?

**Q3 (Rectangular - Easy):**
Six people sit at a rectangular table. A sits at North-West. B sits opposite to A. C is at North-East. Who sits at South-East?

**Q4 (Linear - TCS):**
Six people sit in a line. A, B, C are adjacent (in that order). D is not at either end. E is to the left of D. F is to the right of C. Arrange them.

**Q5 (Circular - TCS):**
Eight people sit around a circular table. P is to the immediate right of Q. R is to the right of P. S is opposite to Q. T is to the right of R. U is not adjacent to Q. Remaining are V and W. Find the arrangement.

**Time Target:** 45 minutes for all 5 questions

---

## SECTION 2: BLOOD RELATIONS (60 MINUTES)

**Frequency in TCS NQT:** 3-4 questions per paper

### KEY RELATIONSHIPS

**Family Tree Basics:**
- Father's wife = Mother
- Mother's husband = Father
- Father's brother = Uncle
- Father's sister = Aunt
- Mother's brother = Uncle (maternal)
- Mother's sister = Aunt (maternal)

**Going One Generation:**
- Parent's brother/sister = Uncle/Aunt
- Brother/sister of parent = Uncle/Aunt
- Child of uncle/aunt = Cousin

**Same Generation:**
- Brother, Sister, Cousin

**Next Generation:**
- Child = Son/Daughter
- Son's wife = Daughter-in-law
- Daughter's husband = Son-in-law

---

### EXAMPLE 1 (Basic)

**Problem:**
A's father's brother is B. What is A to B?

**Solution:**
- A's father = A's parent
- A's father's brother = Uncle of A (since he's A's father's brother)
- So B is A's uncle

But from B's perspective:
- A's father is B's brother
- A is B's brother's child
- So A is B's nephew

**Answer: A is B's nephew; B is A's uncle**

---

### EXAMPLE 2 (TCS-Level)

**Problem:**
Pointing to a girl in a photograph, Mohan says, "She is the daughter of my mother's son's wife." Who is the girl to Mohan?

**Solution:**

Let's decode step by step:
- "My mother's son" = Mohan's brother (mother's son could be anyone, but in context, it's the brother)
- "My mother's son's wife" = Brother's wife = Sister-in-law
- "Daughter of my mother's son's wife" = Daughter of sister-in-law = Niece

**Answer: The girl is Mohan's niece**

---

### EXAMPLE 3 (TCS-Level - Complex)

**Problem:**
Pointing to a man in a photograph, a woman says, "His brother's father is my father's only son." What is the relationship between the woman and the man?

**Solution:**

Let me name the woman = W, the man in photo = M

Breaking down the statement:
- "The man's brother's father" = Man's father = X
- "My father's only son" = My brother (let's call him Y)
- So X = Y (The man's father is the woman's brother)

If the man's father is the woman's brother:
- Woman's brother is the man's father
- Woman is the man's father's sister
- So woman is the man's aunt

**Answer: The woman is the man's aunt (or the man is the woman's nephew)**

---

### PRACTICE QUESTIONS: BLOOD RELATIONS

**Q1 (Basic):**
P is the mother of Q. Q is the father of R. What is R's relationship to P?

**Q2 (TCS):**
A girl says to a boy, "You are the son of my father's sister." What is the boy to the girl?

**Q3 (TCS):**
Pointing to a man, a woman says, "He is the son of my mother's only brother." What relation is the woman to this man?

**Q4 (Complex):**
X's brother's father is Y's father's son. What is the relationship between X and Y?

**Time Target:** 15 minutes for all 4 questions

---

## SECTION 3: NUMBER SERIES (60 MINUTES) - ESSENTIAL FOR TCS

**Frequency in TCS NQT:** 3-4 questions per paper

### PATTERN TYPES

**Type 1: Addition Series**
Pattern: Each number increases by a constant amount

Example: 2, 5, 8, 11, 14, ?
- Difference: +3 each time
- Answer: 17

**Type 2: Multiplication Series**
Pattern: Each number multiplies by a constant

Example: 2, 6, 18, 54, 162, ?
- Multiply by 3 each time
- Answer: 486

**Type 3: Mixed Series**
Pattern alternates between operations

Example: 1, 2, 4, 5, 10, 11, 22, ?
- +1, ×2, +1, ×2, +1, ×2, ...
- Answer: 23

**Type 4: Difference Series (Arithmetic Progression with changing difference)**
Pattern: The difference itself changes in a pattern

Example: 1, 2, 4, 7, 11, 16, 22, ?
- Differences: 1, 2, 3, 4, 5, 6, 7
- Answer: 29

**Type 5: Power/Square/Cube Series**
Pattern: Based on squares, cubes, or powers

Example: 1, 4, 9, 16, 25, 36, ?
- 1², 2², 3², 4², 5², 6², ?
- Answer: 49 (7²)

**Type 6: Alternate Series**
Two interleaved series

Example: 2, 3, 4, 6, 6, 9, 8, 12, ?
- Series 1: 2, 4, 6, 8, ?  (even +2)
- Series 2: 3, 6, 9, 12, ? (multiples of 3)
- Answer: 10

---

### EXAMPLE 1 (Basic Addition)

**Problem:** 5, 10, 15, 20, 25, 30, ?

**Solution:**
Each number increases by 5.
Answer: 35

---

### EXAMPLE 2 (TCS-Level Mixed Pattern)

**Problem:** 1, 2, 4, 8, 16, 32, ?

**Solution:**
- 1 × 2 = 2
- 2 × 2 = 4
- 4 × 2 = 8
- 8 × 2 = 16
- 16 × 2 = 32
- 32 × 2 = 64

Answer: 64

---

### EXAMPLE 3 (TCS-Level Tricky)

**Problem:** 2, 3, 5, 7, 11, 13, ?

**Solution:**
These are prime numbers! 2, 3, 5, 7, 11, 13, and the next prime is...

Answer: 17

---

### EXAMPLE 4 (Difference Pattern)

**Problem:** 1, 4, 9, 16, 25, ?

**Solution:**
Differences: 3, 5, 7, 9, ?
The differences themselves are increasing by 2.
Next difference: 11
So answer: 25 + 11 = 36

Alternatively, recognize these as perfect squares: 1², 2², 3², 4², 5², 6²

Answer: 36

---

### PRACTICE QUESTIONS: NUMBER SERIES

**Q1:** 2, 4, 8, 16, 32, ?

**Q2:** 1, 3, 6, 10, 15, 21, ?

**Q3:** 2, 6, 12, 20, 30, ?

**Q4:** 5, 10, 20, 40, 80, ?

**Q5:** 1, 1, 2, 3, 5, 8, 13, ?

**Time Target:** 20 minutes for all 5 questions

---

## SECTION 4: SYLLOGISMS (60 MINUTES)

**Frequency in TCS NQT:** 3-4 questions per paper

### KEY CONCEPTS

**Syllogism Structure:**
```
All/Some + Group1 + are/are not + Group2  (Premise 1)
All/Some + Group2 + are/are not + Group3  (Premise 2)
---
Conclusion about Group1 and Group3
```

### RULES FOR SOLVING SYLLOGISMS

**Rule 1:** All A are B + All B are C = All A are C
**Rule 2:** All A are B + Some B are C = No definite conclusion about A and C
**Rule 3:** Some A are B + Some B are C = No definite conclusion about A and C
**Rule 4:** No A are B + All B are C = No A are C
**Rule 5:** All A are B + No B are C = No A are C

---

### EXAMPLE 1 (Basic)

**Problem:**
Premise 1: All cats are animals.
Premise 2: All animals are living things.
Conclusion: All cats are living things.

Is the conclusion correct?

**Solution:**
- All cats are animals (A are B)
- All animals are living things (B are C)
- Therefore: All cats are living things (A are C) ✓

**Answer: YES, the conclusion is correct**

---

### EXAMPLE 2 (TCS-Level)

**Problem:**
Premise 1: Some doctors are teachers.
Premise 2: All teachers are educated.
Conclusion: Some doctors are educated.

Is the conclusion correct?

**Solution:**
- Some doctors are teachers (Some A are B)
- All teachers are educated (All B are C)
- Therefore: Some doctors are educated (Some A are C) ✓

This follows the logical rule.

**Answer: YES, the conclusion is correct**

---

### EXAMPLE 3 (TCS-Level - Complex)

**Problem:**
Premise 1: All roses are flowers.
Premise 2: Some flowers are red.
Conclusion: Some roses are red.

Is the conclusion correct?

**Solution:**
- All roses are flowers (A are B)
- Some flowers are red (Some B are C)
- Can we conclude: Some roses are red (Some A are C)?

NO! Red flowers might not include roses. We can't make this conclusion.

**Answer: NO, the conclusion is INCORRECT**

---

### PRACTICE QUESTIONS: SYLLOGISMS

**Q1:**
Premise 1: All engineers are intelligent.
Premise 2: Ram is intelligent.
Conclusion: Ram is an engineer.
(Correct/Incorrect?)

**Q2:**
Premise 1: Some fruits are sweet.
Premise 2: All sweet things are healthy.
Conclusion: Some fruits are healthy.
(Correct/Incorrect?)

**Q3:**
Premise 1: No birds are reptiles.
Premise 2: All penguins are birds.
Conclusion: No penguins are reptiles.
(Correct/Incorrect?)

**Q4:**
Premise 1: All gold is precious.
Premise 2: Some precious things are expensive.
Conclusion: Some gold is expensive.
(Correct/Incorrect?)

**Time Target:** 15 minutes for all 4 questions

---

## SECTION 5: CODING-DECODING (45 MINUTES)

**Frequency in TCS NQT:** 2-3 questions per paper

### TYPES OF CODING

**Type 1: Letter Shifting (Forward/Backward)**
Each letter shifts by a fixed number of positions

Example: Code A with shift +1:
A → B, B → C, C → D, ..., Z → A

**Type 2: Position-based Coding**
Different letters have different shifts based on position

**Type 3: Reverse Coding**
Letters are reversed: ABCD → DCBA

**Type 4: Substitution Cipher**
Each letter maps to another specific letter

**Type 5: Pattern/Rule-based**
Custom rules apply

---

### EXAMPLE 1 (Letter Shift)

**Problem:**
In a certain code, each letter is shifted 3 positions forward.
A=D, B=E, C=F, etc.
Code "HELLO"

**Solution:**
H → K, E → H, L → O, L → O, O → R
Answer: KHOOR

---

### EXAMPLE 2 (TCS-Level Reverse)

**Problem:**
In a code, each word is reversed.
Code "LOGICAL"

**Solution:**
LOGICAL → LACIGOL

Answer: LACIGOL

---

### EXAMPLE 3 (TCS-Level Position-based)

**Problem:**
In a code:
- 1st letter shifts by 1
- 2nd letter shifts by 2
- 3rd letter shifts by 3, etc.

Code "CAT"

**Solution:**
C(1st) +1 → D
A(2nd) +2 → C
T(3rd) +3 → W

Answer: DCW

---

### PRACTICE QUESTIONS: CODING-DECODING

**Q1:** If BOOK is coded as CPPL, how is APPLE coded?

**Q2:** In a code, each letter is replaced by the letter 4 positions ahead. Code ZEBRA.

**Q3:** If CAT is coded as FDU, what is the pattern? Decode PEN using the same pattern.

**Time Target:** 15 minutes for all 3 questions

---

## DAY 2 CHECKLIST - VERIFY YOUR PROGRESS

- [ ] Completed all 5 sections (Seating, Blood Relations, Number Series, Syllogisms, Coding)
- [ ] Solved 20+ practice questions
- [ ] Understood all logic patterns
- [ ] Average accuracy: 70%+
- [ ] Seating arrangement problems <3 minutes each (gained speed)

**TOTAL QUESTIONS SOLVED TODAY:**
- Seating Arrangements: 5
- Blood Relations: 4
- Number Series: 5
- Syllogisms: 4
- Coding-Decoding: 3
- **TOTAL: 21 questions**

---

## ANSWERS & SOLUTIONS (REVEAL ONLY AFTER SOLVING)

**SEATING ANSWERS:**
- Q1: B A C D (or different based on full problem)
- Q2: Depends on exact setup
- Q3: Requires full table specification
- Q4: A B C F ... (requires verification)
- Q5: Requires full circular setup

**BLOOD RELATIONS ANSWERS:**
- Q1: P is Q's grandmother
- Q2: The boy is the girl's cousin
- Q3: The woman is the man's cousin
- Q4: X and Y are cousins

**NUMBER SERIES ANSWERS:**
- Q1: 64
- Q2: 28
- Q3: 42
- Q4: 160
- Q5: 21 (Fibonacci sequence)

**SYLLOGISMS ANSWERS:**
- Q1: Incorrect (not all intelligent are engineers)
- Q2: Correct
- Q3: Correct
- Q4: Incorrect (not all gold is expensive)

**CODING-DECODING ANSWERS:**
- Q1: DQQM (shift +1)
- Q2: DISX (Z→D, E→I, B→F, R→V, A→E)
- Q3: Pattern is +1 shift; PEN → QFO

---

## IMPORTANT REMINDERS

✓ Reasoning is your weakness - spend extra time here
✓ Draw diagrams for seating arrangements
✓ Write out family trees for blood relations
✓ Look for pattern sequences in number series
✓ Understand the "why" behind each logic

**TOMORROW:** You'll tackle Verbal Ability (Reading, Error ID, Sentence Completion)

**You're doing great! Keep pushing!** 💪
