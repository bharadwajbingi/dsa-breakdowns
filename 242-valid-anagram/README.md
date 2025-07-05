### 🔁 242. Valid Anagram

📘 [Leetcode Link](https://leetcode.com/problems/valid-anagram/)

### 🧩 Real-Life Analogy: Messy Fridge Labels

You labeled two identical-looking jars: “Choco Mix” and “Mix Choco”.  
You want to check if both jars have the same ingredients in any order.

### 🎯 Goal

Check if both strings contain the same characters with the same frequency.

### ✅ Solution Overview

1. Count characters in the first string
2. Subtract counts using second string
3. If any count goes negative → return False
4. If all match → return True

### 💡 Key Concepts

- Hash Map or Array Counting
- Frequency Matching

### 🧠 Code Solutions

#### 🐍 Python

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False

        count = [0] * 26
        for cs, ct in zip(s, t):
            count[ord(cs) - ord('a')] += 1
            count[ord(ct) - ord('a')] -= 1

        return all(c == 0 for c in count)
```

#### ☕ Java

```java
class Solution {
    public boolean isAnagram(String s, String t) {
        if (s.length() != t.length()) return false;

        int[] count = new int[26];
        for (int i = 0; i < s.length(); i++) {
            count[s.charAt(i) - 'a']++;
            count[t.charAt(i) - 'a']--;
        }

        for (int c : count)
            if (c != 0) return false;

        return true;
    }
}
```

---

Happy coding! 🚀
