# LEETCODE-Strings-3461
---

### 🔍 **Code summary**

The function `hasSameDigits(String s)` takes a numeric string and repeatedly reduces it by replacing each digit with `(a + b) % 10`, where `a` and `b` are consecutive digits.
This continues until only **2 digits** remain, and then it returns whether those **two final digits are equal**.

---

### 🧠 Let’s dry run with an example:

Let’s take
`s = "1234"`

So initially:

```
n = 4
sb = "1234"
```

---

### **First iteration** (while `n > 2`, i.e. 4 > 2 ✅)

Loop `i = 0 to n-2 = 2`

| i | a | b | (a+b)%10 | sb after change |
| - | - | - | -------- | --------------- |
| 0 | 1 | 2 | 3        | `3234`          |
| 1 | 2 | 3 | 5        | `3534`          |
| 2 | 3 | 4 | 7        | `3574`          |

✅ After this pass: `sb = "3574"`, then `n-- → 3`

---

### **Second iteration** (while `n > 2`, i.e. 3 > 2 ✅)

Loop `i = 0 to 1`

| i | a | b | (a+b)%10 | sb after change |
| - | - | - | -------- | --------------- |
| 0 | 3 | 5 | 8        | `8574`          |
| 1 | 5 | 7 | 2        | `8274`          |

✅ After this pass: `sb = "8274"`, then `n-- → 2`

---

### **Exit loop** (since `n = 2 ❌` condition fails)

Now compare:

```
sb.charAt(0) = '8'
sb.charAt(1) = '2'
```

So return `false`.

---

### ✅ **Final Output for s = "1234" → false**

---

### Let’s try one more quick check:

`s = "1111"`

```
n=4, sb="1111"
```

**1st round:**
(a+b)%10 always = 2 → `"2221"` → n=3
**2nd round:**
(2+2)%10 = 4, (2+2)%10 = 4 → `"4421"` → n=2
Compare '4' and '4' → ✅ true

**Result = true**

---

### 🧩 In short:

| Input  | Output                           |
| ------ | -------------------------------- |
| "1234" | false                            |
| "1111" | true                             |
| "89"   | (8==9? false) → false            |
| "505"  | (5+0→5, 0+5→5 → final 55) → true |

---
