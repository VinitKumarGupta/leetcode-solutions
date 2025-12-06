# Problem:

**Longest Substring Without Repeating Characters**

* **Pattern:** Sliding Window
* **Difficulty:** Medium

## Intuition

The key idea here is to find a window in the string where **no characters repeat**.
Instead of checking every possible substring (which becomes slow), we maintain a dynamic window and adjust its boundaries whenever we encounter a duplicate.
This ensures we only scan each character once.

## Approach

* Use a **HashSet** to store the characters currently inside the sliding window.
* Maintain two pointers:

    * `left` → start of the window
    * `right` → end of the window

* Expand the window by moving `right` forward as long as characters are unique.
* If a duplicate is found, **shrink the window** from the left until the duplicate is removed, removing characters from the set one by one.
* Update the maximum window length after every valid expansion.
* Since both pointers only move forward, the entire algorithm runs efficiently in linear time.

## Complexity

* **Time Complexity:** `O(n)`
  Each character is added and removed from the set at most once.
* **Space Complexity:** `O(n)`
  In the worst case (all characters unique), the HashSet holds `n` characters.

## Notes

* This problem taught me the *sliding window* approach.
* How shrinking the window is as important as expanding it.
* Even though there are two loops, the answer is still `O(n)` because both pointers move forward only.
* A hashmap-based version also exists (jumping the left pointer directly), but the HashSet version is more intuitive and a better starting point.