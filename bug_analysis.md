# Part 1: Bug Analysis — buggy_program.py

## Bug 1
- **Line:** `def calculate_stats(numbers)`
- **Error type:** SyntaxError
- **Problem:** The function definition is missing the colon that ends it.
  Python cannot parse the file at all, so nothing runs.
- **Fix:** `def calculate_stats(numbers):`
- **Found by:** myself

## Bug 2
- **Line:** `if num > average`
- **Error type:** SyntaxError
- **Problem:** The `if` statement opens a block but has no colon at the end.
- **Fix:** `if num > average:`
- **Found by:** myself

## Bug 3
- **Line:** `print(f"Average: {result[average]}")`
- **Error type:** NameError
- **Problem:** `average` is used as if it were a variable. Python looks for a
  variable with that name and finds none. Dictionary keys must be strings.
- **Fix:** `print(f"Average: {result['average']}")`
- **Found by:** myself

## Bug 4
- **Line:** `scores = [85, 92, 78, 95, 88, "70", 93]`
- **Error type:** TypeError
- **Problem:** `"70"` is a string, not a number. `sum()` tries to add it to the
  other numbers and fails with "unsupported operand type(s) for +: 'int' and 'str'".
  The line looks correct on inspection — the bug only appears at runtime.
- **Fix:** `scores = [85, 92, 78, 95, 88, 70, 93]`
- **Found by:** myself, with one hint

## Verified output after fixes

    Total: 601
    Average: 85.85714285714286
    Above average: 4 scores
