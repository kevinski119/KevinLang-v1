Kevin Coder Text Language – Core Rules v1
===========================================

Goal:
  A compact texting language for coders that feels like code,
  but is meant for humans to read, not machines to execute.


0. Base Concepts
----------------

- X, Y, Z, T  = tokens or sequences (like "A", "hello", list of items, etc.)
- n, i, j, k  = integers (1-based indexing, like humans usually count)
- Sequences   = ordered lists of tokens, e.g. ["A", "A", "A"]
- Indexing    = starts at 1 (so 1 = first element, 2 = second, ...)


1. Assignment
-------------

Syntax:
  NAME = VALUE

Examples:
  A = A
  B = hello
  K = Kevin
  M = mood

Meaning:
  Give a reusable name (A, B, K...) to a token or sequence.
  In casual texting, people can assume earlier definitions from context.


2. Concatenation
----------------

Concept:
  Writing tokens next to each other means "put them in sequence".

Example:
  AB      → ["A", "B"] or "A B"
  BK      → "B" followed by "K"  (e.g. "am Kevin")
  A[BK]   → A applied to sequence [B, K] (interpretation depends on A's definition)


3. Repeat
---------

Rule:
  repeat: X[n]

Meaning:
  Create a sequence with X repeated n times.

Example:
  A = A
  A[3]          → AAA      (["A", "A", "A"])
  hello[2]      → hello hello


4. Replace (single)
-------------------

Rule:
  replace: X[n[i]:Y]

Expanded meaning:
  1) First: repeat X exactly n times → a sequence.
  2) Then: replace the item at index i with Y.

Example:
  A = A
  A[5[3]:"b"]   → A A b A A
                  1 2 3 4 5

  A[100[50]:"b"]
    → 100 A’s where the 50th is "b".


5. Replace (multi)
------------------

Rule:
  multi-replace: X[n[i,j,k]:Y,Z,T]

Meaning:
  1) Create a sequence of X repeated n times.
  2) Replace position i with Y, position j with Z, position k with T.

Example:
  A = A
  A[5[1,3,5]:"x","y","z"]
    → x A y A z
      1 2 3 4 5

Notes:
  - You can extend the pattern: X[n[i1,i2,i3,i4]:Y1,Y2,Y3,Y4]
  - If fewer replacements than indices are given, undefined behaviour = up to the users / memes.


6. Insert
---------

Rule:
  insert: X[n+Y@i]

Meaning:
  1) Repeat X n times.
  2) Insert Y at index i, shifting later elements right.

Example:
  A = A
  A[4+"b"@2]
    Step 1: A A A A
    Step 2: A b A A A

Result:
  A b A A A

Notes:
  - You can use this to visually represent "injecting" something into a pattern.
  - Useful for "I’m fine but chaos in the middle" vibes.


7. Delete
---------

Rule:
  delete: X[n[-i]]

Meaning:
  1) Repeat X n times.
  2) Delete the element at index i.

Example:
  A = A
  A[5[-3]]
    Step 1: A A A A A
    Step 2: A A   A A  (3rd removed)

Result:
  A A A A   (4 A’s total)

Notes:
  - Deleting from repeated patterns is basically "glitching" the sequence.


8. Mix (Replace with Another Element of Same Pattern)
-----------------------------------------------------

Rule:
  mix: X[n[i→j]]

Meaning:
  1) Repeat X n times.
  2) Take the value at index j.
  3) Copy that value into index i.

Example (symbolic):
  Sequence: [a, b, c, d]
  X[4[1→3]]
    → [c, b, c, d]   (index 1 becomes what index 3 was)

In your simple repeated pattern:
  A = A
  A[5[1→3]]
    Because all are A, nothing changes (all A anyway).
  But with mixed patterns (e.g. after earlier replacements), this becomes spicy.


9. Examples Using the Rules
---------------------------

1) Basic hello-world style:

  A = hello[2]
  B = world
  A[[2]:B]

Interpretation:
  A = ["hello", "hello"]
  Replace index 2 with B = "world"
  → ["hello", "world"]


2) The "I am Kevin" construction:

  A = I
  B = am
  K = Kevin

  A[BK]

If used as:
  A[BK]  → "I am Kevin"

(Semantic rule: A[x] = "I x" where x = BK → "am Kevin")


3) Scream with one switched letter:

  A = A
  A[[A]:100[50]:"b"]

Meaning:
  100 A’s, with the 50th replaced by "b".

Result (conceptual):
  AAAAA...(49 times)...AbAAAA...(51st to 100th)


10. Optional: Mood / Tone Modifiers (Soft Rule)
-----------------------------------------------

These are not strict syntax, just a convention for vibe:

  X^sad      → same text, but you imply sad tone
  X^hype     → excited tone
  X^error    → "this is broken, I know"

Examples:
  K = Kevin
  K^chaos          → "Kevin, but full chaos mode"

  A = I
  B = am
  A[BK]^tired      → "I am Kevin" but exhausted mood


11. Reading Philosophy
----------------------

- This is NOT meant to be executed by a computer.
- It’s a visual and symbolic **shorthand** for coders who like:
    - patterns
    - indexing
    - replacement
    - nested meaning
- The goal is:
    - look cool
    - be compact
    - be intuitive if you think in arrays / strings
    - still readable as human text with a bit of nerd brain


End of v1
-----------
Feel free to mutate, fork, or shitpost new rules.
If people understand you, the syntax is valid.
If they don't, just tell them:
  "Skill issue. Update your KevinLang parser."
