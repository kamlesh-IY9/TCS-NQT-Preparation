# DAY 5: ADVANCED CODING - KADANE'S, STACK, RECURSION & MOCK EXAM GUIDE

**Total Time:** 5-6 Hours | **Target:** Complete Part B + Mini-Mock Exam | **Focus:** Final mastery & exam simulation

---

## YOUR SCHEDULE FOR TODAY

| Time | Topic | Duration | Activity |
|------|-------|----------|----------|
| 00:00-01:00 | Kadane's Algorithm (Max Subarray) | 60 min | Concept + Code + Variations |
| 01:00-02:00 | Stack: Valid Parentheses + Next Greater | 60 min | Both problems + code |
| **02:00-02:15** | **BREAK** | 15 min | Rest & Refresh |
| 02:15-03:15 | Recursion: Fibonacci + Climbing Stairs | 60 min | Both problems + complexity |
| 03:15-04:15 | **REVISION:** Review Day 4-5 Problems | 60 min | Re-solve 3-4 key problems |
| 04:15-05:15 | **MINI MOCK:** 10-15 Mixed Coding Questions | 60 min | Timed practice (simulate exam) |
| 05:15-05:30 | Review Mini-Mock Mistakes | 15 min | Document weak areas |

**Daily Target:** Complete Part B mastery + Score 70%+ on mini-mock

---

## PROBLEM 1: KADANE'S ALGORITHM - MAXIMUM SUBARRAY (60 MINUTES)

**Frequency in TCS:** Very High (2023-2025 papers)

### PROBLEM STATEMENT

Find the contiguous subarray with the largest sum.

**Examples:**
- Input: [-2, 1, -3, 4, -1, 2, 1, -5, 4]
- Output: 6 (subarray [4, -1, 2, 1])

- Input: [5, 4, -1, 7, 8]
- Output: 23 (entire array)

- Input: [-5, -4, -3]
- Output: -3 (single element)

---

### APPROACH: KADANE'S ALGORITHM

**Intuition:**
- Keep track of maximum sum ending at current position
- If adding current number to previous sum is worse than starting fresh, start fresh
- Track overall maximum seen so far

```python
def max_subarray(arr):
    if not arr:
        return 0

    max_current = arr[0]  # Max sum ending at current position
    max_global = arr[0]   # Overall maximum

    for i in range(1, len(arr)):
        max_current = max(arr[i], max_current + arr[i])
        max_global = max(max_global, max_current)

    return max_global
```

**Time Complexity:** O(n)
**Space Complexity:** O(1)

---

### STEP-BY-STEP EXAMPLE

Array: [-2, 1, -3, 4, -1, 2, 1, -5, 4]

```
i=0: arr[0]=-2
     max_current = -2
     max_global = -2

i=1: arr[1]=1
     max_current = max(1, -2+1) = max(1, -1) = 1
     max_global = max(-2, 1) = 1

i=2: arr[2]=-3
     max_current = max(-3, 1-3) = max(-3, -2) = -2
     max_global = max(1, -2) = 1

i=3: arr[3]=4
     max_current = max(4, -2+4) = max(4, 2) = 4
     max_global = max(1, 4) = 4

i=4: arr[4]=-1
     max_current = max(-1, 4-1) = max(-1, 3) = 3
     max_global = max(4, 3) = 4

i=5: arr[5]=2
     max_current = max(2, 3+2) = max(2, 5) = 5
     max_global = max(4, 5) = 5

i=6: arr[6]=1
     max_current = max(1, 5+1) = max(1, 6) = 6
     max_global = max(5, 6) = 6

i=7: arr[7]=-5
     max_current = max(-5, 6-5) = max(-5, 1) = 1
     max_global = max(6, 1) = 6

i=8: arr[8]=4
     max_current = max(4, 1+4) = max(4, 5) = 5
     max_global = max(6, 5) = 6

RESULT: 6 ✓
```

---

### VARIATION: RETURN SUBARRAY (NOT JUST SUM)

```python
def max_subarray_indices(arr):
    max_current = arr[0]
    max_global = arr[0]
    start = 0
    end = 0
    temp_start = 0

    for i in range(1, len(arr)):
        if arr[i] > max_current + arr[i]:
            max_current = arr[i]
            temp_start = i
        else:
            max_current = max_current + arr[i]

        if max_current > max_global:
            max_global = max_current
            start = temp_start
            end = i

    return max_global, start, end  # Returns max sum, start index, end index
```

---

### TEST CASES

```python
assert max_subarray([-2, 1, -3, 4, -1, 2, 1, -5, 4]) == 6
assert max_subarray([5, 4, -1, 7, 8]) == 23
assert max_subarray([-5, -4, -3]) == -3
assert max_subarray([1]) == 1
assert max_subarray([-1, -2, -3, -4]) == -1
```

---

## PROBLEM 2 & 3: STACK PROBLEMS (60 MINUTES)

**Frequency in TCS:** Medium

### PROBLEM 2: VALID PARENTHESES

**Problem:** Check if parentheses are balanced.

**Examples:**
- Input: "({})"
- Output: True

- Input: "([)]"
- Output: False (wrong order)

---

### SOLUTION

```python
def is_valid_parentheses(s):
    stack = []
    matching = {'(': ')', '[': ']', '{': '}'}

    for char in s:
        if char in matching:  # Opening bracket
            stack.append(char)
        else:  # Closing bracket
            if not stack or matching[stack.pop()] != char:
                return False

    return len(stack) == 0
```

**Time Complexity:** O(n)
**Space Complexity:** O(n) for stack

---

### PROBLEM 3: NEXT GREATER ELEMENT

**Problem:** For each element, find the next greater element to its right.

**Examples:**
- Input: [1, 5, 0, 3, 4, 5]
- Output: [5, -1, 3, 4, 5, -1]

---

### SOLUTION: USING STACK

```python
def next_greater_element(arr):
    n = len(arr)
    result = [-1] * n
    stack = []  # Stores indices

    for i in range(n - 1, -1, -1):  # Traverse right to left
        # Pop smaller elements
        while stack and arr[stack[-1]] <= arr[i]:
            stack.pop()

        # Top of stack is next greater
        if stack:
            result[i] = arr[stack[-1]]

        stack.append(i)

    return result
```

**Time Complexity:** O(n)
**Space Complexity:** O(n)

---

### EXAMPLE

Array: [1, 5, 0, 3, 4, 5]

```
i=5 (arr[5]=5):
  stack is empty
  result[5] = -1
  stack = [5]

i=4 (arr[4]=4):
  arr[stack[-1]] = arr[5] = 5 > 4, so don't pop
  result[4] = 5
  stack = [5, 4]

i=3 (arr[3]=3):
  arr[4] = 4 > 3, don't pop
  result[3] = 4
  stack = [5, 4, 3]

i=2 (arr[2]=0):
  arr[3] = 3 > 0, don't pop
  result[2] = 3
  stack = [5, 4, 3, 2]

i=1 (arr[1]=5):
  arr[2] = 0 <= 5, pop
  arr[3] = 3 <= 5, pop
  arr[4] = 4 <= 5, pop
  arr[5] = 5 <= 5, pop
  stack is empty
  result[1] = -1
  stack = [1]

i=0 (arr[0]=1):
  arr[1] = 5 > 1, don't pop
  result[0] = 5
  stack = [1, 0]

RESULT: [5, -1, 3, 4, 5, -1] ✓
```

---

### TEST CASES

```python
# Valid parentheses
assert is_valid_parentheses("()") == True
assert is_valid_parentheses("({}[])") == True
assert is_valid_parentheses("([)]") == False
assert is_valid_parentheses("{]") == False

# Next greater element
assert next_greater_element([1, 5, 0, 3, 4, 5]) == [5, -1, 3, 4, 5, -1]
assert next_greater_element([2, 1]) == [-1, -1]
assert next_greater_element([1, 2, 3]) == [2, 3, -1]
```

---

## PROBLEM 4 & 5: RECURSION FUNDAMENTALS (60 MINUTES)

**Frequency in TCS:** Medium-High

### PROBLEM 4: FIBONACCI NUMBER

**Problem:** Find the Nth Fibonacci number.

Fibonacci: 0, 1, 1, 2, 3, 5, 8, 13, ...

**Examples:**
- Input: 5
- Output: 5

- Input: 6
- Output: 8

---

### SOLUTION 1: Basic Recursion (Simple but Slow)

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n - 1) + fibonacci(n - 2)
```

**Time Complexity:** O(2^n) - very slow!
**Space Complexity:** O(n) due to recursion stack

---

### SOLUTION 2: Memoization (Better)

```python
def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]

    if n <= 1:
        return n

    memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
    return memo[n]
```

**Time Complexity:** O(n)
**Space Complexity:** O(n)

---

### SOLUTION 3: Iterative (Best for Interview)

```python
def fibonacci(n):
    if n <= 1:
        return n

    prev, curr = 0, 1
    for _ in range(2, n + 1):
        prev, curr = curr, prev + curr

    return curr
```

**Time Complexity:** O(n)
**Space Complexity:** O(1)

---

### PROBLEM 5: CLIMBING STAIRS

**Problem:** You can climb 1 or 2 stairs at a time. How many ways to reach Nth stair?

**Examples:**
- Input: n = 2
- Output: 2 (ways: [1+1], [2])

- Input: n = 3
- Output: 3 (ways: [1+1+1], [1+2], [2+1])

- Input: n = 4
- Output: 5 (ways: [1+1+1+1], [1+1+2], [1+2+1], [2+1+1], [2+2])

---

### SOLUTION

```python
def climb_stairs(n):
    if n <= 1:
        return 1

    dp = [0] * (n + 1)
    dp[0] = 1  # 1 way to stay at ground
    dp[1] = 1  # 1 way to reach stair 1

    for i in range(2, n + 1):
        dp[i] = dp[i - 1] + dp[i - 2]

    return dp[n]
```

**Why:** To reach stair i, you can:
- Come from stair (i-1) by taking 1 step
- Come from stair (i-2) by taking 2 steps
- So ways[i] = ways[i-1] + ways[i-2]

**Time Complexity:** O(n)
**Space Complexity:** O(n)

---

### SPACE-OPTIMIZED VERSION

```python
def climb_stairs(n):
    if n <= 1:
        return 1

    prev2, prev1 = 1, 1
    for i in range(2, n + 1):
        curr = prev1 + prev2
        prev2, prev1 = prev1, curr

    return prev1
```

**Time Complexity:** O(n)
**Space Complexity:** O(1)

---

### TEST CASES

```python
# Fibonacci tests
assert fibonacci(0) == 0
assert fibonacci(1) == 1
assert fibonacci(5) == 5
assert fibonacci(6) == 8
assert fibonacci(10) == 55

# Climbing stairs tests
assert climb_stairs(1) == 1
assert climb_stairs(2) == 2
assert climb_stairs(3) == 3
assert climb_stairs(4) == 5
assert climb_stairs(5) == 8
```

---

## SECTION 6: REVISION & MINI-MOCK (120 MINUTES)

### REVISION GUIDE (First 60 minutes)

**Re-solve without looking at solutions:**

1. **Find 2nd Largest** (from Day 4)
   - Time yourself: should be <5 minutes
   - Ask: What's the optimal approach?

2. **Move Zeros** (from Day 4)
   - Time yourself: should be <5 minutes
   - Ask: Can you do it in-place?

3. **Rotate Array** (from Day 4)
   - Time yourself: should be <7 minutes
   - Ask: Why is reverse method better?

4. **Kadane's Algorithm** (from Day 5)
   - Time yourself: should be <8 minutes
   - Ask: Why track max_current and max_global separately?

---

### MINI MOCK EXAM (60 MINUTES)

**Set a timer for 1 hour. Choose 2-3 problems and solve them as if in real exam.**

**Mixed Coding Problems (pick 2-3):**

1. **Easy:** Find maximum element in array
2. **Easy:** Check if array is sorted
3. **Medium:** Find second largest element
4. **Medium:** Valid parentheses
5. **Medium:** Palindrome check
6. **Hard:** Kadane's algorithm
7. **Hard:** Next greater element

---

### SCORING RUBRIC

**For each problem:**
- ✓ Correct solution = 10 points
- ✓ Correct logic but syntax error = 5 points
- ✓ Partial solution = 2 points
- ✗ No solution = 0 points

**Target:** 20+ points out of 30 (70%+)

---

### COMMON MISTAKES TO AVOID IN EXAM

1. **Not reading problem carefully** - Miss edge cases
2. **Rushing into code** - Think first, code second
3. **Forgetting test cases** - Always test with examples
4. **Not explaining complexity** - Interviewers ask about it
5. **Using wrong data structures** - Array vs List vs Dictionary
6. **Off-by-one errors** - Be careful with loop indices
7. **Not handling edge cases** - Empty arrays, single element

---

## DAY 5 CHECKLIST - FINAL PUSH

- [ ] Understood Kadane's algorithm (multiple times)
- [ ] Implemented 2 stack problems (Valid parentheses, Next greater)
- [ ] Implemented 2 recursion problems (Fibonacci, Climbing stairs)
- [ ] Revised Day 4 problems (timed, under pressure)
- [ ] Completed mini-mock exam (scored 70%+)
- [ ] Identified weak areas from mini-mock
- [ ] Can explain time complexity for all 10+ problems
- [ ] Confident about approaching unfamiliar coding problems

**CODING PROBLEMS MASTERED:**
- Day 4: Find 2nd Largest, Move Zeros, Rotate Array, Palindrome, Anagram, Spiral
- Day 5: Kadane's, Valid Parentheses, Next Greater, Fibonacci, Climbing Stairs

**TOTAL: 11 Coding Problems** ✓

---

## 5-DAY COMPLETION SUMMARY

### PART A FOUNDATION (Days 1-3, 75 minutes in exam)
✓ **Day 1 - Numerical Ability:**
  - Percentages, Profit & Loss, Averages, Data Interpretation, Ratio & Proportion, Time-Speed-Distance
  - 25+ questions solved

✓ **Day 2 - Reasoning Ability:**
  - Seating Arrangements, Blood Relations, Number Series, Syllogisms, Coding-Decoding
  - 20+ questions solved

✓ **Day 3 - Verbal Ability:**
  - Reading Comprehension, Error Identification, Sentence Completion, Synonyms/Antonyms
  - 15+ questions solved

### PART B ADVANCED CODING (Days 4-5, 115 minutes in exam)
✓ **Day 4 - Arrays, Strings, Matrix:**
  - Find 2nd Largest, Move Zeros, Rotate Array, Palindrome, Anagram, Spiral Traversal
  - 6 problems mastered

✓ **Day 5 - Advanced + Recursion:**
  - Kadane's Algorithm, Valid Parentheses, Next Greater, Fibonacci, Climbing Stairs
  - 5 problems mastered
  - Mini-mock completed (70%+ target)

---

## EXAM DAY STRATEGY (FINAL)

### Part A (75 minutes) - Do This Order:
1. **First (20 mins):** Numerical Ability (your strength)
2. **Third (20 mins):** Verbal Ability (medium)
3. **Last (25 mins):** Reasoning Ability (your weakness)
4. **Buffer (10 mins):** Return to skipped questions

### Part B (115 minutes) - Do This Order:
1. **First (30 mins):** Advanced Quant/Reasoning (warm-up)
2. **Last (85 mins):** Coding Problems (2-3 problems)
   - 1st problem: 35-40 mins (must get this)
   - 2nd problem: 35-40 mins (try to get)
   - 3rd problem: 10-15 mins (only if easy)

---

## FINAL TIPS FOR SUCCESS

**In Exam Hall:**
1. Read ALL problems first - Choose easiest ones
2. Write pseudocode before actual code
3. Test with at least 2 examples
4. Explain your complexity when submitting
5. Don't panic if stuck - move to next problem

**For Scoring 65%+ (Prime Eligible):**
- Get 50%+ in Part A (30 out of 60 questions)
- Get 55%+ in Part B (coding + quant)
- Time management is KEY

**Remember:**
- You've prepared 28+ aptitude questions
- You've mastered 11+ coding problems
- You understand the patterns TCS tests

---

## FINAL CHECKLIST BEFORE EXAM

- [ ] All 5 days studied
- [ ] All problems solved and understood
- [ ] Mini-mock scored 70%+
- [ ] Weak areas identified and reviewed
- [ ] Comfortable explaining time complexity
- [ ] Ready for exam day

---

## YOU'VE GOT THIS! 💪

Your 5-day intense preparation is complete. You now have:
- ✓ Solid Part A foundation
- ✓ Advanced coding problem-solving skills
- ✓ Exam strategy and time management
- ✓ 70%+ capability to crack Prime role

**Go nail that TCS NQT exam!**

Remember: Confidence + Preparation = Success

---

**END OF 5-DAY PREPARATION PLAN**
