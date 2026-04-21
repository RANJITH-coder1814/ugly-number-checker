# 263. Ugly Number

## 🧠 Problem

An **ugly number** is a positive integer whose prime factors are limited to **2, 3, and 5**.

Given an integer `n`, return `true` if `n` is an ugly number.

---

## 💡 Approach

* If `n <= 0`, return `false`
* Keep dividing `n` by:

  * 2 (if divisible)
  * 3 (if divisible)
  * 5 (if divisible)
* If after removing all these factors, `n == 1`, then it is an ugly number

---

## ⚙️ Algorithm

1. Check if `n <= 0`
2. While `n > 1`:

   * Divide by 2, 3, or 5 if possible
   * Otherwise break
3. Return `n == 1`

---

## ⏱ Complexity

* **Time Complexity:** `O(log n)`
* **Space Complexity:** `O(1)`

---

## ✅ Example

```
Input: n = 6
Output: true
Explanation: 6 = 2 × 3
```

---

## 🚀 Code (C++)

```cpp
class Solution {
public:
    bool isUgly(int n) {
        if (n <= 0) return false;

        while (n > 1) {
            if (n % 2 == 0) n /= 2;
            else if (n % 3 == 0) n /= 3;
            else if (n % 5 == 0) n /= 5;
            else break;
        }

        return n == 1;
    }
};
```
