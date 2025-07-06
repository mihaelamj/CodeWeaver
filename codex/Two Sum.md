# Two Sum

## Problem:

Given an array of integers and a target number, find the indices of two numbers that add up to the target.

## Example:

Input: [2, 7, 11, 15], target: 9
Output: [0, 1] because 2 + 7 = 9

## Solution

```swift
import Foundation

/*
Input: [2, 7, 11, 15], target: 9
Output: [0, 1] because 2 + 7 = 9
*/

func twoSum(numbers: [Int], target: Int) -> [Int] {
  var seen = [Int: Int]()

  for (index, number) in numbers.enumerated() {
    let complement = target - number
    // If the complement is already seen, return indices
    if let complementIndex = seen[complement] {
      return [complementIndex, index]
    }
    // Otherwise, save the current number and its index
    seen[number] = index
  }
  // No pair found
  return []
}
```

## Complexity:
- Time Complexity: O(n), where n is the length of the array. The array is traversed once, and dictionary lookups are on average O(1).
- Space Complexity: O(n) in the worst case if no two numbers sum up to the target, requiring storage of all elements in the dictionary.