# 🪞 125. Valid Palindrome

<a href="https://leetcode.com/problems/valid-palindrome/" target="_blank" rel="noopener noreferrer">Leetcode Link</a>
---

### 🧩 Real-Life Analogy: Mirror Sentence Check

You're trying to read a messy sentence in a mirror.  
Ignore punctuation, symbols, and spacing — just focus on the letters and numbers.  
**Example:** `"A man, a plan, a canal: Panama"` → ✅ Valid palindrome

---

### 🎯 Goal

Check if the cleaned-up version of the string is the same when read backward.

---

### ✅ Solution Overview

1. Use two pointers: one at the beginning, one at the end
2. Skip non-alphanumeric characters
3. Compare characters in a case-insensitive way
4. If mismatch occurs → return false
5. If pointers meet without mismatch → return true

---

### 💡 Key Concepts

- Two Pointers
- String Cleanup (alphanumeric + lowercase)
- Case-insensitive Comparison

---

### 🧠 Code Solutions

#### 🐍 Python

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        left, right = 0, len(s) - 1

        while left < right:
            while left < right and not s[left].isalnum():
                left += 1
            while left < right and not s[right].isalnum():
                right -= 1

            if s[left].lower() != s[right].lower():
                return False

            left += 1
            right -= 1

        return True
```

#### ☕ Java

```java
class Solution {
    public boolean isPalindrome(String s) {
        int left = 0, right = s.length() - 1;

        while (left < right) {
            while (left < right && !Character.isLetterOrDigit(s.charAt(left))) left++;
            while (left < right && !Character.isLetterOrDigit(s.charAt(right))) right--;

            if (Character.toLowerCase(s.charAt(left)) != Character.toLowerCase(s.charAt(right)))
                return false;

            left++;
            right--;
        }

        return true;
    }
}

```

#### 🧠 C++

```cpp
class Solution {
public:
    bool isPalindrome(string s) {
        int left = 0, right = s.size() - 1;

        while (left < right) {
            while (left < right && !isalnum(s[left])) left++;
            while (left < right && !isalnum(s[right])) right--;

            if (tolower(s[left]) != tolower(s[right])) return false;

            left++;
            right--;
        }

        return true;
    }
};

```

#### 🌐 JavaScript

```javascript
var isPalindrome = function (s) {
  let left = 0,
    right = s.length - 1;

  while (left < right) {
    while (left < right && !isAlphaNum(s[left])) left++;
    while (left < right && !isAlphaNum(s[right])) right--;

    if (s[left].toLowerCase() !== s[right].toLowerCase()) return false;

    left++;
    right--;
  }

  return true;

  function isAlphaNum(ch) {
    return /^[a-z0-9]$/i.test(ch);
  }
};
```

### 🧩 Step-by-Step Breakdown

Let’s walk through the input:  
📥 `s = "A man, a plan, a canal: Panama"`

- **Initial Pointers:**  
  - `left = 0` → `'A'`  
  - `right = s.length - 1` → `'a'`  

- **Skip non-alphanumeric characters:**  
  - Ignore commas, spaces, colons, etc.  
  - Move `left` and `right` inward until both point to valid characters  

- **Compare characters:**  
  - `'A'` vs `'a'` → lowercase comparison → ✅ Match  
  - If they match, continue; else return `false`  

- **Repeat until pointers cross:**  
  - Keep skipping and comparing  

- **All checks pass:**  
  - No mismatches found → `return true` ✅


### 🏁 Output

✅ true — the cleaned string is a valid palindrome

---
