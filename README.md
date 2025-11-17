# Kevin Coder Text Language - v1
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
A[[A]:100[50]:"b"]
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

## 11. Philosophy

This language is:

- not executable  
- not strict  
- not designed for compilers  

It is a **texting dialect** built for coders who communicate using symbolic shorthand.

---

## Version

**Kevin Coder Text Language â€” v1**
