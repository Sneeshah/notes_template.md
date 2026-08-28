# Challenge Name

**Category:** binary exploitation
**Difficulty:** Easy / Medium / Hard  
**Progress:** In Progress /  solved

---

## Description

**Files:** `binary`, `libc.so.6`  

---

## Analysis + Info Dump

#### file + checksec command
```
Arch:     ELF 32-bit LSB executable, Intel i386
RELRO:    Partial RELRO
Stack:    No canary found
NX:       NX enabled
PIE:      No PIE
RPATH:    No RPATH
RUNPATH:  No RUNPATH
SYMBOLS:  77 (not stripped)
FORTIFY:  No (0 fortified / 2 fortifiable)
```

#### Info Dump
```
Inputting lots of chars kills the program
fgets writes 128 bytes of data to buf, but buf is only 32 bytes of size
```

### Vulnerability
- Buffer Overflow
- Heap Overflow
- Format String
- Use After Free
- Other: ___

### Stack Layout
```
┌──────────────────┐
│  buf[0..31]      │  +0
├──────────────────┤
│  padding         │  +32
├──────────────────┤
│  saved EBX       │  +36
├──────────────────┤
│  saved EBP       │  +40
├──────────────────┤
│  return address  │  +44
└──────────────────┘
```
return adress -> push ebp -> push ebx -> sub 0x24 (36<sub>10</sub>)
padding = 0x24 - 0x20 = 0x04 

---

## Solution


### Step 1:

```
What happened to get to the exploit
```
### Step 2 — Exploit
```
command that gets the flag
```

### Step 3 — Capturing the flag

```

```


<!--
---
## Exploit

```python

```
-->

---

## Learnings

- Example learning
