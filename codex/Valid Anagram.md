# Valid Anagram

## Problem:

Write a Swift function that takes two strings and returns `true` if one is an anagram of the other (they contain the same characters in any order), and `false` otherwise.

## Solution

```swift
func isAnagram(_ s1: String, _ s2: String) -> Bool {
    if s1.count != s2.count { return false }

    var charCount = [Character: Int]()

    for char in s1 {
        charCount[char, default: 0] += 1
    }

    for char in s2 {
        if let count = charCount[char] {
            if count == 1 {
                charCount.removeValue(forKey: char)
            } else {
                charCount[char] = count - 1
            }
        } else {
            return false
        }
    }

    return charCount.isEmpty
}

## Explanation:
- Check if the strings have equal length; if not, return false immediately.
- Count characters in the first string.
- Subtract character counts using the second string.
= If all counts balance out, return true.

## Complexity:
- Time: O(n), where n is the length of the strings.
- Space: O(1) or O(k), k = number of unique characters (bounded by alphabet size)
```
