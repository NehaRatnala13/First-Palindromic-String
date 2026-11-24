# 2108. First Palindromic String

**Difficulty:** Easy  
**Topics:** Array, Two Pointers, String  
**Link:** [LeetCode Problem 2108](https://leetcode.com/problems/find-first-palindromic-string-in-the-array/)

---

## Problem Description

You receive a list of strings named `words`. Return the earliest string in the list that forms a palindrome, or `""` if none matches.

A palindrome reads identically from left to right and right to left.

---

## Examples

### Example 1
```text
Input: words = ["abc","car","ada","racecar","cool"]
Output: "ada"
```
**Note:** Both `"ada"` and `"racecar"` are valid palindromes, so `"ada"` wins because it appears earlier.

### Example 2
```text
Input: words = ["notapalindrome","racecar"]
Output: "racecar"
```
**Note:** Only `"racecar"` reads the same backward.

### Example 3
```text
Input: words = ["def","ghi"]
Output: ""
```
**Note:** None of the entries are palindromes, resulting in an empty output.

---

## Constraints

- `1 <= words.length <= 100`
- `1 <= words[i].length <= 100`
- Every `words[i]` contains lowercase English letters exclusively.

---

## Approach: Two Pointers

1. Loop over each string inside `words` from start to finish.
2. Place two pointers at opposite ends of the active word (`left = 0`, `right = len - 1`).
3. Move both pointers inward while their characters match.
4. If the pointers cross without a mismatch, return that word right away.
5. Return `""` after checking the entire list if no palindrome exists.

### Complexity Analysis

- **Time Complexity:** \(O(N \times M)\), where N represents the total word count and M is the longest string length.
- **Space Complexity:** O(1), since pointer comparisons require no extra memory allocation.

---

## Solution (Python)

```python
class Solution:
    def firstPalindrome(self, words: list[str]) -> str:
        for item in words:
            if item == item[::-1]:
                return item
        return ""
```
