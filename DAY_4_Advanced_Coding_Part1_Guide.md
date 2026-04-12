# DAY 4: ADVANCED CODING - ARRAYS, STRINGS & MATRIX GUIDE

**Total Time:** 5-6 Hours | **Target:** 6 Coding Problems Mastered | **Focus:** High-Frequency Patterns

---

## YOUR SCHEDULE FOR TODAY

| Time | Topic | Duration | Activity |
|------|-------|----------|----------|
| 00:00-01:00 | Arrays: Find 2nd Largest | 60 min | Concept + Code + Complexity + 2 variations |
| 01:00-02:00 | Arrays: Move Zeros to End | 60 min | Concept + Code + Complexity + 2 variations |
| **02:00-02:15** | **BREAK** | 15 min | Rest & Refresh |
| 02:15-03:15 | Arrays: Rotate Array | 60 min | Left/Right rotation + 2 variations |
| 03:15-04:15 | Strings: Palindrome & Anagram | 60 min | Both concepts + code + test |
| **04:15-04:30** | **BREAK** | 15 min | Rest & Refresh |
| 04:30-05:30 | Matrix: Spiral Traversal | 60 min | Clockwise + Code + Examples |

**Daily Target:** Code 6 problems, explain complexity, test with examples

---

## PROBLEM 1: FIND SECOND LARGEST ELEMENT (60 MINUTES)

**Frequency in TCS:** High (2023-2025 papers)

### PROBLEM STATEMENT

Given an array of integers, find the second largest element.

**Examples:**
- Input: [10, 5, 20, 3, 8]
- Output: 10 (largest is 20)

- Input: [5, 5, 5]
- Output: -1 or None (no second largest)

- Input: [100, 50]
- Output: 50

---

### APPROACH 1: Using Sorting (Easier)

```python
def find_second_largest(arr):
    if len(arr) < 2:
        return -1

    unique_arr = list(set(arr))  # Remove duplicates
    unique_arr.sort(reverse=True)  # Sort descending

    if len(unique_arr) < 2:
        return -1

    return unique_arr[1]  # Second element
```

**Time Complexity:** O(n log n) due to sorting
**Space Complexity:** O(n) due to set and new array

---

### APPROACH 2: Two-Pass (Better for TCS)

```python
def find_second_largest(arr):
    if len(arr) < 2:
        return -1

    max_val = -float('inf')
    second_max = -float('inf')

    # First pass: find maximum
    for num in arr:
        max_val = max(max_val, num)

    # Second pass: find second maximum
    for num in arr:
        if num < max_val:
            second_max = max(second_max, num)

    return second_max if second_max != -float('inf') else -1
```

**Time Complexity:** O(n)
**Space Complexity:** O(1)

---

### APPROACH 3: Single Pass (Optimal for TCS)

```python
def find_second_largest(arr):
    if len(arr) < 2:
        return -1

    max_val = -float('inf')
    second_max = -float('inf')

    for num in arr:
        if num > max_val:
            second_max = max_val
            max_val = num
        elif num > second_max and num != max_val:
            second_max = num

    return second_max if second_max != -float('inf') else -1
```

**Time Complexity:** O(n)
**Space Complexity:** O(1)

---

### TEST CASES

```python
# Test 1
assert find_second_largest([10, 5, 20, 3, 8]) == 10
print("Test 1 passed")

# Test 2
assert find_second_largest([5, 5, 5]) == -1
print("Test 2 passed")

# Test 3
assert find_second_largest([100, 50]) == 50
print("Test 3 passed")

# Test 4
assert find_second_largest([1]) == -1
print("Test 4 passed")

# Test 5 - with negatives
assert find_second_largest([-5, -10, -2]) == -5
print("Test 5 passed")
```

---

### VARIATIONS

**Variation 1:** Find Kth largest element
**Variation 2:** Find second smallest
**Variation 3:** Handle duplicates (allow multiple of same value)

---

## PROBLEM 2: MOVE ZEROS TO END (60 MINUTES)

**Frequency in TCS:** High

### PROBLEM STATEMENT

Given an array, move all zeros to the end while maintaining relative order of non-zero elements.

**Examples:**
- Input: [0, 1, 0, 3, 12]
- Output: [1, 3, 12, 0, 0]

- Input: [0]
- Output: [0]

- Input: [1, 2, 3]
- Output: [1, 2, 3]

---

### APPROACH 1: Two-Pointer

```python
def move_zeros_to_end(arr):
    pointer = 0  # Position to place next non-zero

    # Move all non-zero elements to the front
    for i in range(len(arr)):
        if arr[i] != 0:
            arr[pointer] = arr[i]
            pointer += 1

    # Fill remaining positions with zeros
    while pointer < len(arr):
        arr[pointer] = 0
        pointer += 1

    return arr
```

**Time Complexity:** O(n)
**Space Complexity:** O(1) - modifies array in place

---

### APPROACH 2: Swap Method (More Visual)

```python
def move_zeros_to_end(arr):
    zero_index = 0  # Index to place next zero

    for i in range(len(arr)):
        if arr[i] != 0 and zero_index < i:
            # Swap
            arr[zero_index], arr[i] = arr[i], arr[zero_index]
            zero_index += 1
        elif arr[i] != 0:
            zero_index = i + 1

    return arr
```

**Time Complexity:** O(n)
**Space Complexity:** O(1)

---

### TEST CASES

```python
# Test 1
arr1 = [0, 1, 0, 3, 12]
assert move_zeros_to_end(arr1) == [1, 3, 12, 0, 0]
print("Test 1 passed")

# Test 2
arr2 = [0]
assert move_zeros_to_end(arr2) == [0]
print("Test 2 passed")

# Test 3
arr3 = [1, 2, 3]
assert move_zeros_to_end(arr3) == [1, 2, 3]
print("Test 3 passed")

# Test 4
arr4 = [0, 0, 1]
assert move_zeros_to_end(arr4) == [1, 0, 0]
print("Test 4 passed")
```

---

## PROBLEM 3: ROTATE ARRAY (60 MINUTES)

**Frequency in TCS:** High

### PROBLEM STATEMENT

Rotate array to the right by k steps.

**Examples:**
- Input: [1, 2, 3, 4, 5], k = 2
- Output: [4, 5, 1, 2, 3]

- Input: [1, 2, 3, 4, 5], k = 7
- Output: [4, 5, 1, 2, 3] (k % n = 7 % 5 = 2)

---

### APPROACH 1: Using Slicing (Simple)

```python
def rotate_array(arr, k):
    n = len(arr)
    k = k % n  # Handle k > n

    return arr[-k:] + arr[:-k]
```

**Time Complexity:** O(n)
**Space Complexity:** O(n) - creates new array

---

### APPROACH 2: Reverse Method (Optimal)

```python
def rotate_array(arr, k):
    def reverse(arr, start, end):
        while start < end:
            arr[start], arr[end] = arr[end], arr[start]
            start += 1
            end -= 1

    n = len(arr)
    k = k % n

    reverse(arr, 0, n - 1)  # Reverse entire array
    reverse(arr, 0, k - 1)  # Reverse first k elements
    reverse(arr, k, n - 1)  # Reverse remaining elements

    return arr
```

**Time Complexity:** O(n)
**Space Complexity:** O(1) - in place

---

### EXAMPLE (Reverse Method):

Array: [1, 2, 3, 4, 5], k = 2

Step 1: Reverse entire array
[5, 4, 3, 2, 1]

Step 2: Reverse first 2 elements
[4, 5, 3, 2, 1]

Step 3: Reverse remaining 3 elements
[4, 5, 1, 2, 3] ✓

---

### TEST CASES

```python
# Test 1
arr1 = [1, 2, 3, 4, 5]
assert rotate_array(arr1, 2) == [4, 5, 1, 2, 3]
print("Test 1 passed")

# Test 2
arr2 = [1, 2, 3, 4, 5]
assert rotate_array(arr2, 7) == [4, 5, 1, 2, 3]
print("Test 2 passed")

# Test 3
arr3 = [1]
assert rotate_array(arr3, 1) == [1]
print("Test 3 passed")
```

---

## PROBLEM 4 & 5: PALINDROME & ANAGRAM (60 MINUTES)

**Frequency in TCS:** Medium-High

### PROBLEM 4: CHECK PALINDROME STRING

**Problem:** Check if a string is a palindrome (ignoring spaces and case).

**Examples:**
- Input: "A man a plan a canal Panama"
- Output: True

- Input: "Hello"
- Output: False

---

### SOLUTION

```python
def is_palindrome(s):
    # Clean: remove non-alphanumeric and convert to lowercase
    cleaned = ''.join(char.lower() for char in s if char.isalnum())

    # Compare with reverse
    return cleaned == cleaned[::-1]
```

**Time Complexity:** O(n)
**Space Complexity:** O(n)

---

### PROBLEM 5: CHECK ANAGRAM

**Problem:** Check if two strings are anagrams (same letters, different order).

**Examples:**
- Input: "listen", "silent"
- Output: True

- Input: "abc", "def"
- Output: False

---

### SOLUTION 1: Using Frequency

```python
def is_anagram(s1, s2):
    if len(s1) != len(s2):
        return False

    # Count frequency of characters
    freq = {}
    for char in s1:
        freq[char] = freq.get(char, 0) + 1

    for char in s2:
        if char not in freq:
            return False
        freq[char] -= 1
        if freq[char] < 0:
            return False

    return True
```

**Time Complexity:** O(n)
**Space Complexity:** O(26) = O(1) for English letters

---

### SOLUTION 2: Using Sorting

```python
def is_anagram(s1, s2):
    return sorted(s1) == sorted(s2)
```

**Time Complexity:** O(n log n)
**Space Complexity:** O(n)

---

### TEST CASES

```python
# Palindrome tests
assert is_palindrome("A man a plan a canal Panama") == True
assert is_palindrome("Hello") == False
assert is_palindrome("racecar") == True

# Anagram tests
assert is_anagram("listen", "silent") == True
assert is_anagram("abc", "def") == False
assert is_anagram("anagram", "nagaram") == True
```

---

## PROBLEM 6: SPIRAL MATRIX TRAVERSAL (60 MINUTES)

**Frequency in TCS:** Medium

### PROBLEM STATEMENT

Print matrix elements in spiral order (clockwise from outside to inside).

**Example:**
```
Matrix:
1  2  3
4  5  6
7  8  9

Spiral Output:
1 2 3 6 9 8 7 4 5
```

---

### SOLUTION

```python
def spiral_traversal(matrix):
    if not matrix or not matrix[0]:
        return []

    result = []
    top, bottom = 0, len(matrix) - 1
    left, right = 0, len(matrix[0]) - 1

    while top <= bottom and left <= right:
        # Traverse right
        for col in range(left, right + 1):
            result.append(matrix[top][col])
        top += 1

        # Traverse down
        for row in range(top, bottom + 1):
            result.append(matrix[row][right])
        right -= 1

        # Traverse left (if there's a row left)
        if top <= bottom:
            for col in range(right, left - 1, -1):
                result.append(matrix[bottom][col])
            bottom -= 1

        # Traverse up (if there's a column left)
        if left <= right:
            for row in range(bottom, top - 1, -1):
                result.append(matrix[row][left])
            left += 1

    return result
```

**Time Complexity:** O(m × n) where m = rows, n = columns
**Space Complexity:** O(1) excluding output

---

### STEP-BY-STEP EXAMPLE

```
Matrix:
1  2  3
4  5  6
7  8  9

Initial: top=0, bottom=2, left=0, right=2

Step 1 (Traverse right, top=0):
[1, 2, 3], top becomes 1

Step 2 (Traverse down, right=2):
[1, 2, 3, 6, 9], right becomes 1

Step 3 (Traverse left, bottom=2):
[1, 2, 3, 6, 9, 8, 7], bottom becomes 1

Step 4 (Traverse up, left=0):
[1, 2, 3, 6, 9, 8, 7, 4], left becomes 1

Step 5 (top=1, bottom=1, left=1, right=1):
[1, 2, 3, 6, 9, 8, 7, 4, 5]
```

---

### TEST CASES

```python
# Test 1: 3x3 matrix
matrix1 = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
assert spiral_traversal(matrix1) == [1, 2, 3, 6, 9, 8, 7, 4, 5]
print("Test 1 passed")

# Test 2: 2x3 matrix
matrix2 = [
    [1, 2, 3],
    [4, 5, 6]
]
assert spiral_traversal(matrix2) == [1, 2, 3, 6, 5, 4]
print("Test 2 passed")

# Test 3: 1x4 matrix
matrix3 = [[1, 2, 3, 4]]
assert spiral_traversal(matrix3) == [1, 2, 3, 4]
print("Test 3 passed")
```

---

## DAY 4 CHECKLIST

- [ ] Understood and coded Find 2nd Largest (3 approaches)
- [ ] Understood and coded Move Zeros (2 approaches)
- [ ] Understood and coded Rotate Array (2 approaches)
- [ ] Understood and coded Palindrome Check
- [ ] Understood and coded Anagram Check
- [ ] Understood and coded Spiral Traversal
- [ ] Can explain time complexity for each problem
- [ ] Tested all solutions with given test cases
- [ ] Can solve each problem in <15 minutes

**PROBLEMS COMPLETED:** 6 major coding problems

---

## IMPORTANT CODING REMINDERS

✓ **Always think of multiple approaches** - Write O(n log n), then optimize to O(n)
✓ **Time Complexity matters** - TCS asks about it explicitly
✓ **Space Complexity** - Some problems have O(1) space solution
✓ **Test with edge cases** - Empty arrays, single element, duplicates
✓ **Write clean code** - Variables names should be clear
✓ **Comment your logic** - Help understand your thought process

**TOMORROW:** You'll complete Kadane's, Stack problems, Recursion, and take the Mini-Mock!

**Excellent progress! Half-way through Part B!** 💪
