# Problem: Valid Parentheses

**Description:**  
Given a string containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['`, and `']'`, determine if the input string is valid.

An input string is valid if:

- Open brackets are closed by the same type of brackets.
- Open brackets are closed in the correct order.

**Example:**  
Input: `"()[]{}"`  
Output: `true`

Input: `"(]"`  
Output: `false`

---

### How to solve it?

Use a **stack**:

- Push open brackets onto the stack.
- For every closing bracket, check if it matches the last open bracket on the stack.
- If it doesn’t match or the stack is empty when trying to pop, it’s invalid.

---

### Swift code:

```swift
func isValid(_ s: String) -> Bool {
    var stack = [Character]()
    let pairs: [Character: Character] = [")": "(", "}": "{", "]": "["]

    for char in s {
        if pairs.values.contains(char) {
            // It's an opening bracket
            stack.append(char)
        } else if let last = stack.last, pairs[char] == last {
            // Closing bracket matches last opening bracket
            stack.removeLast()
        } else {
            // No match or stack empty when expecting match
            return false
        }
    }
    return stack.isEmpty
}
```


## Complexity:
- Time Complexity: O(n), where n is the length of the string. We iterate through the string once, and stack operations (push/pop) take O(1) time.
- Space Complexity: O(n) in the worst case when all characters are opening brackets and are stored on the stack.