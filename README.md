# Kevin Coder Text Language - v2
A compact, expressive texting language for coders who think in brackets, arrays, recursion, and chaos.  
This is **not** a programming language.  
This is a **human-readable conlang** that uses code-like syntax to express meaning, mood, and patterns.

---

## 0. Base Concepts

- **X, Y, Z, T** tokens or sequences (`"A"`, `"hello"`, lists, etc.)
- **n, i, j, k** integers  
- **Indexing starts at 1**  
- **Sequences** ordered lists of tokens  

---

## 1. Assignment

```
NAME = VALUE
```

Examples:

```
A = A
B = hello
K = Kevin
```

---

## 2. Concatenation

```
AB
BK
A[BK]
```

Tokens written next to each other form sequences.

---

## 3. Repeat

```
X[n]
```

Creates `n` repetitions of `X`.

Examples:

```
A[3]         AAA
hello[2]     hello hello
```

---

## 4. Replace (Single)

```
X[n[i]:Y]
```

1. Repeat X `n` times  
2. Replace index `i` with `Y`

Example:

```
A = A
A[5[3]:"b"]    A A b A A
```

---

## 5. Replace (Multi)

When using multi-replace, any index not explicitly replaced retains the original value ```X```.

```
X[n[i,j,k]:Y,Z,T]
```

Example:

```
A = A
A[5[1,3,5]:"x","y","z"]
 x A y A z
```

---

## 6. Insert

```
X[n+Y@i]
```

Example:

```
A = A
A[4+"b"@2]
 A b A A A
```

---

## 7. Delete

```
X[n[-i]]
```

Example:

```
A = A
A[5[-3]]
 A A A A
```

---

## 8. Mix

```
X[n[ij]]
```

Example:

```
[a,b,c,d][4[13]]
 c b c d
```

---

## 9. Practical Examples

### Hello World
```
A = hello[2]
B = world
A[[2]:B]
 hello world
```

### I am Kevin
```
A = I
B = am
K = Kevin
A[BK]
 I am Kevin
```

### Screaming with a Glitch
```
A = A
A[100[50]:"b"]
 AAA...A b A...AAA
```

---

## 10. Optional Tone Modifiers

```
X^tired
X^excited
X^error
K^chaos
```
---

## 11. For loop

If A has length < i, it automatically expands to length i.

```
for[i] {
 
}
```
or 
```
for[n[i]] {

}
```

### examle

```
H = Hello

for[i] {
 L = H[i]
 out[L]
}

   ["H", "e", "l", "l", "o"]
```
or
```
A = A

for[5[i]] {
 out[A]
}

   ["A", "A", "A", "A", "A"]
```

---

## 12. IF statements
this is where it gets weird...

```
if[i=x] {

}
```

### example

New elements are filled with A’s base value (the value A was originally assigned).

```
A = A

for[5[i]] {
   if[i=3] {
      A[[i]:"b"]
   }
   out[A]
}

["A", "A", "b", "A", "A"]
```

---

## 13. Philosophy

This language is:

- not executable  
- not strict  
- not designed for compilers  

It is a **texting dialect** built for coders who communicate using symbolic shorthand.

---

## 14. do what you want as long as it's understandable

basically there's no rules...

this language is built for texting and python like syntax.

you can combine everything to create something.

also you can use normal python like 

## 14. Do what you want (as long as it's understandable)

KevinLang is meant for **texting**, thinking out loud, and being a bit chaotic.
It’s not a rigid “compiler language” – it’s closer to a mix of:

- human-readable notes  
- Python-like logic  
- and cursed constructs that still make sense

### Core idea

- The **rules above** (assignments, lists, loops, if, etc.) are the *core* of KevinLang.  
- On top of that, you’re allowed to:
  - invent small shortcuts,
  - add extra brackets,
  - write half-code, half-text,
  - as long as a human (and future you) can understand what it’s supposed to do.

If a line can be **reasonably interpreted** as:
- valid KevinLang, or  
- “this obviously means: do X in KevinLang”  

…then it’s allowed.

### Mixing with normal Python

You can also just write real Python when you want to be more precise or show how something would run:

```py
# real Python example
A = ["A"] * 5
for i in range(5):
    if i == 2:
        A[i] = "b"
print(A)  # ["A", "A", "b", "A", "A"]
```

You can use Python to:
- explain how KevinLang idea works,
- prototype behaviour,
- or give a "this is what the interpreter would roughly do" version.

KevinLang is just vibes next to Python.
---

## BugLang
if nobody understands it, not even you after sleep...
you've went to **BugLang** terretory, not **KevinLang**

---

## Version

**Kevin Coder Text Language v2**
