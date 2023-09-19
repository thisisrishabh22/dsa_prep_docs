# LeetCode Problem 217: Contains Duplicate

### Problem Statement:

Given an integer array `nums`, return `true` if any value appears at least twice in the array, and return `false` if every element is distinct.

Example 1:
```
Input: nums = [1,2,3,1]
Output: true
```
Example 2:
```
Input: nums = [1,2,3,4]
Output: false
```
Example 3:
```
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```

### Difficulty: `EASY`

### Solution:

There are total 3 solutions to this problem:
1. Sorting & Checking
2. Hash Map
3. Hash Set

At first I executed the following problem with Hash Map initially but there are 2 more ways to solve the problem. I have added the solutions in the same order as above.

#

### Solution 1: Sorting & Checking

#### Approach:

If there are any duplicates, they will be one after the other after sorting the array. So, we can sort the array and check if the adjacent elements are equal or not.

#### Algorithm:

1. Sort the array.
2. Iterate through the array and check if the adjacent elements are equal or not.
3. If they are equal, return `true`.
4. If the loop ends, return `false`.

#### Code:

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Arrays.sort(nums);
        for(int i = 0; i < nums.length - 1; i++) {
            if(nums[i] == nums[i + 1]) {
                return true;
            }
        }
        return false;
    }
}
```

#### Performance Analysis:

Runtime: `18 ms`, faster than `35.81%` of Java online submissions for Contains Duplicate.

Memory Usage: `58.3 MB`, less than `6.45%` of Java online submissions for Contains Duplicate.

#

### Solution 2: Hash Map

#### Approach:

We can use a hash map to store the elements of the array. If the element is already present in the hash map, we can return `true`. If the loop ends, we can return `false`.

#### Algorithm:

1. Create a hash map.
2. Iterate through the array.
3. If the element is already present in the hash map, return `true`.
4. If the loop ends, return `false`.

#### Code:

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Map<Integer, Integer> map = new HashMap<>();
        for(int i = 0; i < nums.length; i++) {
            if(map.containsKey(nums[i])) {
                return true;
            }
            map.put(nums[i], i);
        }
        return false;
    }
}
```

#### Performance Analysis:

Runtime: `12 ms`, faster than `49.95%` of Java online submissions for Contains Duplicate.

Memory Usage: `56.2 MB`, less than `39.64%` of Java online submissions for Contains Duplicate.

#

### Solution 3: Hash Set

#### Approach:

We can use a hash set to store the elements of the array. If the element is already present in the hash set, we can return `true`. If the loop ends, we can return `false`.

#### Algorithm:

1. Create a hash set.
2. Iterate through the array.
3. If the element is already present in the hash set, return `true`.
4. If the loop ends, return `false`.

#### Code:

```java
class Solution {
    public boolean containsDuplicate(int[] nums) {
        Set<Integer> set = new HashSet<>();
        for(int i = 0; i < nums.length; i++) {
            if(set.contains(nums[i])) {
                return true;
            }
            set.add(nums[i]);
        }
        return false;
    }
}
```

#### Performance Analysis:

Runtime: `10 ms`, faster than `85.69%` of Java online submissions for Contains Duplicate.

Memory Usage: `54.4 MB`, less than `97.14%` of Java online submissions for Contains Duplicate.

#

### Time Complexity:
`o(n)` for all the solutions

### Space Complexity:
`o(n)` for all the solutions

### Recommended Solution:

Hash Set

### Related Links:
1. [Problem on LeetCode](https://leetcode.com/problems/contains-duplicate/)
2. [Hash Map in Java](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)
3. [Hash Set in Java](https://www.geeksforgeeks.org/hashset-in-java/)
4. [Sorting Array in Java](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)

### Similar Questions:
1. [Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)
2. [Contains Duplicate III](https://leetcode.com/problems/contains-duplicate-iii/)
3. [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

#

### Author:
#### [Rishabh Singh](https://geeekgod.in)

[GitHub Profile](https://github.com/thisisrishabh22/)

[LeetCode Profile](https://leetcode.com/geeekgod/)
