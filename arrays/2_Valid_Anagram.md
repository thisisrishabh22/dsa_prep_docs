# LeetCode Problem 242: Valid Anagram

### Problem Statement:

Given two strings `s` and `t`, return `true` if `t` is an anagram of s, and `false` otherwise.

An <b>Anagram</b> is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

Example 1:
```
Input: s = "anagram", t = "nagaram"
Output: true
```
Example 2:
```
Input: s = "rat", t = "car"
Output: false
```

### Difficulty: `EASY`

### Solution:

There are total 3 solutions to this problem:
1. Sorting & Checking

To Be Added Soon.

#

### Solution 1: Char Array Sort & Checking

#### Approach:

The idea is to sort the strings and compare them. If they are equal, they are anagrams. If not, they are not anagrams. We can convert the strings to char arrays and sort them.

#### Algorithm:

1. Convert the strings to char arrays.
2. Sort the char arrays.
3. Compare the char arrays.
4. Return the result.

#### Code:

```java
class Solution {
  public boolean isAnagram(String s, String t) {
    char string1[] = s.toCharArray();
    char string2[] = t.toCharArray();

    Arrays.sort(string1);
    Arrays.sort(string2);

    return Arrays.equals(string1, string2);
  }
}

```

#### Performance Analysis:

Runtime: `3 ms`, faster than `90.79%` of Java online submissions for Contains Duplicate.

Memory Usage: `43.3 MB`, less than `62.47%` of Java online submissions for Contains Duplicate.

#

### Time Complexity:
1. Sorting & Checking: `o(nlogn)`

### Space Complexity:
1. Sorting & Checking: `o(n)`

### Recommended Solution:

To Be Added Soon.

### Related Links:
1. [Problem on LeetCode](https://leetcode.com/problems/valid-anagram/)
2. [Sorting Array in Java](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)
3. [Convert String to Char Array in Java](https://www.geeksforgeeks.org/convert-a-string-to-character-array-in-java/)

### Similar Questions:
1. [Group Anagrams](https://leetcode.com/problems/group-anagrams/)
2. [Palindrome Permutation](https://leetcode.com/problems/palindrome-permutation/)
3. [Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)

#

### Author:
#### [Rishabh Singh](https://geeekgod.in)

[GitHub Profile](https://github.com/thisisrishabh22/)

[LeetCode Profile](https://leetcode.com/geeekgod/)
