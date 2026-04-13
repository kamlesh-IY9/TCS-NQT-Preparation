# 🚀 TCS NQT — PRIME ROLE CHEAT SHEET
### _Smart Attempt • High Accuracy • Get Selected_

---

> 💡 **Golden Rule:** You don't need 100%. You need **smart skipping + 1 full coding + 1 partial coding = PRIME**

---

# ⏱️ EXAM STRATEGY (READ THIS FIRST)

## Attempt Order

| Step | Section    | Time Budget | Why               |
|------|------------|-------------|-------------------|
| 1️⃣   | Numerical  | 20 min      | Easy marks        |
| 2️⃣   | Verbal     | 20 min      | Fast if prepared  |
| 3️⃣   | Reasoning  | 25 min      | Needs focus       |
| 🔁   | Buffer     | 10 min      | Review/guesses    |

## ⚠️ Time Rule
> **1 question = max 1.25 minutes. If stuck → SKIP. No exceptions.**

### Smart Guessing When Stuck
- Eliminate clearly wrong options first
- Prefer **B or C** when blindly guessing (statistically central options are more likely to be correct)
- Never leave it blank — TCS NQT has **no negative marking**

---

# 📐 PART A — APTITUDE MASTER

---

## 🔢 1. PERCENTAGES

### Core Formula
```
% Change = (New - Old) / Old × 100
```

### Trick: Always Assume Base = 100
> You never need actual numbers. Assume base = 100 and solve mentally.

### Successive % Change
```
Net % = a + b + (a × b) / 100
```

### Examples

| Situation | Calculation | Answer |
|-----------|-------------|--------|
| +20% then +30% | 20 + 30 + (20×30)/100 | **+56%** |
| +20% then −20% | 20 − 20 + (20×−20)/100 | **−4%** (not 0!) |
| Price increases by 30%, what's original if new = 130? | Original = 130/1.3 | **100** |

### Quick Shortcut Table

| % | Fraction | Decimal |
|---|----------|---------|
| 10% | 1/10 | 0.1 |
| 20% | 1/5 | 0.2 |
| 25% | 1/4 | 0.25 |
| 33.3% | 1/3 | 0.33 |
| 50% | 1/2 | 0.5 |

### ❌ If Stuck
- Eliminate any answer > 100% if talking about single-step discount
- Pick the middle value

---

## 💰 2. PROFIT & LOSS

### Core Formulas
```
Profit % = (Profit / CP) × 100
SP = CP × (1 + P/100)
CP = SP / (1 + P/100)
```

### Trick: Always Assume CP = 100

| Scenario | CP | SP | Profit % |
|----------|----|----|----------|
| 20% profit | 100 | 120 | 20% |
| 15% loss | 100 | 85 | −15% |
| SP=150, Profit=50 | 100 | 150 | 50% |

### Successive Discount Formula
```
Net Discount = a + b − (a × b) / 100
```
> 20% + 30% discount = 20 + 30 − (20×30)/100 = **44% discount** (NOT 50%)

### Example
> A item CP = ₹800. Sold at 25% profit. Find SP.
> SP = 800 × 1.25 = **₹1000**

---

## 🚗 3. TIME, SPEED & DISTANCE

### Core Formulas
```
Speed = Distance / Time
Time = Distance / Speed
Distance = Speed × Time
```

### Unit Conversion
```
km/h → m/s : multiply by 5/18
m/s → km/h : multiply by 18/5
```

### Relative Speed

| Direction | Formula |
|-----------|---------|
| Opposite  | Add speeds |
| Same      | Subtract speeds |

### Average Speed (same distance, two speeds)
```
Average Speed = 2ab / (a + b)
```
> If you go at 40 km/h and return at 60 km/h, average speed = 2×40×60 / (40+60) = **48 km/h** (NOT 50!)

### Example
> Train 200m long at 60 km/h crosses a platform 100m long. Time = ?
> Distance = 200 + 100 = 300m. Speed = 60 × 5/18 = 50/3 m/s. Time = 300 / (50/3) = **18 seconds**

---

## 📊 4. DATA INTERPRETATION

### Strategy
1. **Read the question FIRST**, not the graph
2. Look only for what's asked
3. Use **approximation** — avoid exact calculations

### Tricks
- Ratios: cross multiply mentally
- % of total: compare numerator sizes visually
- Growth: check direction of bars/lines

### ❌ If Stuck
- Pick the value closest to your rough estimate
- Eliminate extreme outliers

---

## 🧠 5. REASONING

### 🪑 Seating Arrangement
1. Fix one person as anchor
2. Circular → convert to linear for easier solving
3. Draw the arrangement, don't just imagine it

> Example: 5 people A,B,C,D,E sit in circle. A is between B and C. B is to the left of A.
> Fix A → B is on left → C is on right → place D and E in remaining

### 👨‍👩‍👦 Blood Relations
- Draw a **family tree always**
- Use symbols: M = Male, F = Female
- Don't trust verbal descriptions alone

> Example: "A is the brother of B's father" → A is B's uncle

### 🔢 Number Series
Check these patterns in order:
1. Add/subtract constant: 2, 5, 8, 11 → +3
2. Multiply: 2, 6, 18, 54 → ×3
3. Squares: 1, 4, 9, 16, 25
4. Cubes: 1, 8, 27, 64
5. Alternate: odd terms one pattern, even terms another

> Example: 2, 3, 5, 8, 13, 21 → Fibonacci (each = sum of prev two)

### ❌ If Stuck on Any Reasoning
- Skip within 30 seconds
- Reasoning is the lowest ROI — don't get trapped

---

## 📖 6. VERBAL

### Reading Comprehension
1. **Read questions first** — know what to look for
2. Scan the passage for keywords from the question
3. Answers are almost always directly stated (TCS doesn't test inference heavily)

### Sentence Correction — What to Check
1. Subject-Verb agreement (singular/plural)
2. Tense consistency
3. Preposition usage (in/on/at/for)
4. Articles (a/an/the)

### Quick Rules

| Wrong | Correct |
|-------|---------|
| "He don't know" | "He doesn't know" |
| "More better" | "Better" |
| "Since 3 years" | "For 3 years" |
| "I am knowing" | "I know" (no continuous for stative verbs) |

---

# 💻 PART B — CODING MASTER

> 🏆 **Coding decides PRIME. Focus 50% of prep here.**

---

## 🧩 CORE PATTERNS

### Pattern 1: Array Traversal
```python
arr = [3, 1, 4, 1, 5, 9]
for i in range(len(arr)):
    print(arr[i])

# Or simpler:
for x in arr:
    print(x)
```

### Pattern 2: Two Pointer (Reverse / Palindrome)
```python
arr = [1, 2, 3, 4, 5]
i, j = 0, len(arr) - 1
while i < j:
    arr[i], arr[j] = arr[j], arr[i]
    i += 1
    j -= 1
# arr is now [5, 4, 3, 2, 1]
```

### Pattern 3: Dictionary — Frequency Count ⭐
```python
arr = [1, 2, 2, 3, 3, 3]
d = {}
for x in arr:
    d[x] = d.get(x, 0) + 1
# d = {1:1, 2:2, 3:3}
```
> Most important pattern in TCS NQT. Used in 60%+ of coding questions.

### Pattern 4: String Tricks
```python
s = "hello"
s[::-1]              # Reverse → "olleh"
s.upper()            # "HELLO"
s.count('l')         # 2
s.replace('l', 'r')  # "herro"
sorted(s)            # ['e','h','l','l','o'] — use for anagram check
```

### Pattern 5: Sorting
```python
arr = [3, 1, 4, 1, 5]
arr.sort()               # Ascending: [1, 1, 3, 4, 5]
arr.sort(reverse=True)   # Descending: [5, 4, 3, 1, 1]

# Sort list of tuples
pairs = [(1,'b'), (2,'a'), (1,'a')]
pairs.sort(key=lambda x: (x[0], x[1]))
# [(1,'a'), (1,'b'), (2,'a')]
```

---

## 🔥 HIGH-PROBABILITY QUESTIONS

### ✅ Q1: Move Zeros to End
```python
def move_zeros(arr):
    index = 0
    for i in range(len(arr)):
        if arr[i] != 0:
            arr[index], arr[i] = arr[i], arr[index]
            index += 1
    return arr

# Example:
# Input:  [0, 1, 0, 3, 12]
# Output: [1, 3, 12, 0, 0]
```

### ✅ Q2: Second Largest Element
```python
def second_largest(arr):
    first = second = float('-inf')
    for num in arr:
        if num > first:
            second = first
            first = num
        elif num > second and num != first:
            second = num
    return second

# Example:
# Input:  [10, 20, 4, 45, 99]
# Output: 45
```

### ✅ Q3: Rotate Array by 1
```python
def rotate(arr):
    return [arr[-1]] + arr[:-1]

# Example:
# Input:  [1, 2, 3, 4, 5]
# Output: [5, 1, 2, 3, 4]
```

### ✅ Q4: Check Anagram
```python
def is_anagram(s1, s2):
    return sorted(s1.lower()) == sorted(s2.lower())

# Example:
# is_anagram("listen", "silent") → True
# is_anagram("hello", "world")  → False
```

### ✅ Q5: Count Vowels in String
```python
def count_vowels(s):
    return sum(1 for c in s.lower() if c in 'aeiou')

# Example:
# Input:  "Hello World"
# Output: 3
```

### ✅ Q6: Find Duplicates
```python
def find_duplicates(arr):
    d = {}
    for x in arr:
        d[x] = d.get(x, 0) + 1
    return [k for k, v in d.items() if v > 1]

# Example:
# Input:  [1, 2, 3, 2, 4, 3]
# Output: [2, 3]
```

### ✅ Q7: Palindrome Check
```python
def is_palindrome(s):
    s = s.lower().replace(" ", "")
    return s == s[::-1]

# Example:
# is_palindrome("racecar") → True
# is_palindrome("hello")   → False
```

### ✅ Q8: FizzBuzz (Classic)
```python
for i in range(1, 101):
    if i % 15 == 0:
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```

### ✅ Q9: Fibonacci Series
```python
def fibonacci(n):
    a, b = 0, 1
    result = []
    for _ in range(n):
        result.append(a)
        a, b = b, a + b
    return result

# fibonacci(6) → [0, 1, 1, 2, 3, 5]
```

### ✅ Q10: Prime Number Check
```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

# is_prime(7) → True
# is_prime(9) → False
```

---

## 🔥 ADVANCED PATTERNS

### Fraud Detection Pattern
```python
# Key pattern: detect same transaction within 60 seconds
transactions = [(sender, receiver, amount, timestamp), ...]

seen = {}
for t in transactions:
    key = (t[0], t[1], t[2])  # sender, receiver, amount
    if key in seen:
        if t[3] - seen[key] <= 60:
            print("FRAUD DETECTED")
    seen[key] = t[3]
```

### Lexicographic Sort (Name + Score)
```python
students = [("Alice", 90), ("Bob", 85), ("Charlie", 90)]
students.sort(key=lambda x: (-x[1], x[0]))
# Sort by score descending, then name ascending
# [('Alice', 90), ('Charlie', 90), ('Bob', 85)]
```

### Sum of Digits
```python
def digit_sum(n):
    return sum(int(d) for d in str(n))

# digit_sum(1234) → 10
```

---

## 🚨 CODING EXAM STRATEGY

### Step-by-Step Approach
1. **Read BOTH questions first** (30 seconds)
2. Pick the easier one → solve fully
3. Second question → solve as much as possible

### If Stuck on Coding
- Write brute force (loops, if-else)
- Use Python built-ins (`sorted()`, `max()`, `min()`, `sum()`, `len()`)
- Add comments explaining your logic (partial credit)
- Even a half-working solution beats nothing

### Python One-Liners to Remember
```python
max(arr)              # Maximum
min(arr)              # Minimum
sum(arr)              # Sum
len(arr)              # Length
sorted(arr)           # Returns sorted list (doesn't modify original)
arr.sort()            # Modifies arr in-place
"".join(list)         # List to string
list(map(int, input().split()))  # Read integers from input
```

---

# 🎯 SECTION-WISE TARGET

| Section | Questions | Target Score | Min to Aim |
|---------|-----------|-------------|-----------|
| Numerical | ~26 | 70%+ | 18/26 |
| Verbal | ~24 | 65%+ | 15/24 |
| Reasoning | ~30 | 55%+ | 16/30 |
| Coding | 2 problems | 1 full + 1 partial | Must do |

---

# 🧠 SURVIVAL RULES

| Rule | Why |
|------|-----|
| Don't spend > 1.25 min per question | Time is your biggest enemy |
| Skip fast, come back | Momentum matters |
| No negative marking → Guess always | Never leave blank |
| Coding > Aptitude for PRIME | Coding has more weight |
| Accuracy > Attempts | Wrong answers waste time |
| Stay calm if stuck | Everyone gets stuck |

---

# ✅ DAY-OF CHECKLIST

- [ ] Get to center 30 min early
- [ ] Carry valid ID proof
- [ ] Follow section attempt order strictly
- [ ] Start coding section with the easier problem
- [ ] Never spend more than 25 min on one coding problem

---

# 🚀 FINAL REMINDER

```
You need 60–70%. Not 100%.
1 coding solution fully working = biggest boost.
Smart skipping = more time for coding.
You are ready. Trust your prep.

👉 GO GET THAT PRIME ROLE 🎯
```

---

_Last updated: TCS NQT Preparation Guide — Prime Target Edition_
