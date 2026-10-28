# Part 2: AI Suggestion Evaluation — my_toolkit.py

## Suggestion A — use isalnum() in is_palindrome
- **Decision:** Implement
- **Why:** The original code only stripped spaces, so real sentences containing
  commas, periods, or colons returned False incorrectly. This is a real logic
  gap, not a style preference.
- **Verified:** "A man, a plan, a canal: Panama!" now returns True.

## Suggestion B — add an empty-list guard in create_report
- **Decision:** Implement
- **Why:** find_max_and_min returns None for an empty list, and unpacking None
  into two variables raises TypeError. My original tests missed this because I
  never called create_report([]).
- **Verified:** create_report("Empty Report", []) now returns a short message
  instead of crashing.

## Suggestion C — convert the functions into a Toolkit class
- **Decision:** Reject
- **Why:** Object-oriented structure adds indirection without solving a problem
  here. The assignment asked for standalone functions. "More professional" is
  an opinion, not an improvement.

## Suggestion D — wrap every function in try/except Exception
- **Decision:** Reject
- **Why:** Catching broad Exception and returning None would hide real bugs
  instead of surfacing them. Silent failure is worse than a clear error.

## Suggestion E — add type hints
- **Decision:** Optional, not implemented
- **Why:** Type hints do not change runtime behavior. Helpful for readability
  and editor tooling, but neither required nor a correctness fix.

## Suggestion F — add a type check in count_occurrences
- **Decision:** Reject
- **Why:** `True == 1` is real Python behavior, but it has no practical effect
  on how this toolkit is used. Adding a type check would complicate the code
  for no gain.

## Suggestion G — replace manual loops with max(), min(), and .count()
- **Decision:** Reject
- **Why:** The assignment explicitly forbids these: "Do NOT use the built-in
  max() and min()" and "Do NOT use the built-in .count() method." The
  suggestion is technically true in isolation, but the AI had no knowledge of
  the spec. This is the key lesson: an improvement in general can still be
  wrong in context.
