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
2. HashMap
3. HashTable (Array of Frequency)

At first I executed the following problem with Sorting & Checking initially but there are 2 more ways to solve the problem. I have added the solutions in the same order as above.

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

### Solution 2: HashMap

#### Approach:

The idea is to store the frequency of each character in `s` and `t` in a HashMap. Default values of each character are `0` if character is found in `s` it is stored in HashMap and incrementing the frequency, if character is found in `t` it is stored in HashMap and decrementing the frequency. Later we can check if all frequencies are `0` or not. If `0` i.e. it's a valid Anagram.

#### Algorithm:

1. Make sure both strings `s` & `t` are of same length
2. Iterate through the String
3. For every character in `s` increment frequency or store default frequency `0`
4. For every character in `t` decrement frequency or store default frequency `0`
5. Iterate through HashMap
6. Make sure all frequencies are `0`, if all frequencies are `0` then it's a valid Anagram

#### Code:

```java
class Solution {
  public boolean isAnagram(String s, String t) {

    if(s.length() != t.length()) return false;

    HashMap<Character, Integer>map = new HashMap();

    for(int i=0; i<s.length(); i++){
      map.put(s.charAt(i), map.getOrDefault(s.charAt(i), 0) + 1);
      map.put(t.charAt(i), map.getOrDefault(t.charAt(i), 0) - 1);
    }


    for(int value: map.values()){
      if(value != 0) return false;
    }

    return true;
  }
}
```

#### Performance Analysis:

Runtime: `24 ms`, faster than `9.36%` of Java online submissions for Contains Duplicate.

Memory Usage: `41.8 MB`, less than `97.95%` of Java online submissions for Contains Duplicate.

#

### Solution 3: HashTable (Array of Frequency)

#### Approach:

The idea is to store the frequency of each character in `s` and `t` in a Hash Table i.e. Array of Frequencies. Default values of each character are `0` if character is found in `s` it is stored in Array and incrementing the frequency, if character is found in `t` it is stored in Array and decrementing the frequency. Later we can check if all frequencies are `0` or not. If `0` i.e. it's a valid Anagram.

#### Algorithm:

1. Make sure both strings `s` & `t` are of same length
2. Create empty array of length 26 i.e. are Hash Table
3. Iterate through the String
4. For every character in `s` increment frequency or store default frequency `0`
5. For every character in `t` decrement frequency or store default frequency `0`
6. Iterate through Frequency Array i.e. Hash Table
7. Make sure all frequencies are `0`, if all frequencies are `0` then it's a valid Anagram

#### Code:

```java
class Solution {
  public boolean isAnagram(String s, String t) {
   if(s.length() != t.length()) return false;

    int[] freq = new int[26];
    for(int i=0; i<s.length(); i++){
      freq[s.charAt(i) - 'a']++;
      freq[t.charAt(i) - 'a']--;
    }

    for(int i=0; i<26; i++){
      if(freq[i] != 0){
        return false;
      }
    }

    return true;
  }
}
```

#### Performance Analysis:

Runtime: `5 ms`, faster than `54.71%` of Java online submissions for Contains Duplicate.

Memory Usage: `41.3 MB`, less than `99.81%` of Java online submissions for Contains Duplicate.

#

### Time Complexity:
1. Sorting & Checking: `o(nlogn)`
2. HashMap: `o(n)`
3. Hash Table: `o(n)`

### Space Complexity:
1. Sorting & Checking: `o(n)`
2. HashMap: `o(n)`
3. Hash Table: `o(1)`

### Recommended Solution:

Hash Table

### Related Links:
1. [Problem on LeetCode](https://leetcode.com/problems/valid-anagram/)
2. [Sorting Array in Java](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)
3. [Convert String to Char Array in Java](https://www.geeksforgeeks.org/convert-a-string-to-character-array-in-java/)
4. [Hash Map in Java](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)

### Similar Questions:
1. [Group Anagrams](https://leetcode.com/problems/group-anagrams/)
2. [Palindrome Permutation](https://leetcode.com/problems/palindrome-permutation/)
3. [Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)

#

### Author:
#### [Rishabh Singh](https://geeekgod.in)

[GitHub Profile](https://github.com/thisisrishabh22/)

[LeetCode Profile](https://leetcode.com/geeekgod/)
