# LeetCode Problem 1: Two Sum

### Problem Statement:

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

Example 1:
```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```
Example 2:
```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```
Example 3:
```
Input: nums = [3,3], target = 6
Output: [0,1]
```

### Difficulty: `EASY`

### Solution:

There are total 3 solutions to this problem:
1. Brute Force (2 Nested Loops)
2. HashMap (2 Loops) i.e. Two Pass
3. HashMap (1 Loop) i.e. One Pass

At first I executed the following problem with Brute Force initially but there are 2 more ways to solve the problem. I have added the solutions in the same order as above.

#

### Solution 1: Brute Force (2 Nested Loops)

#### Approach:

The brute force approach is simple. Loop through the array and check every possible pair. Return the indices if the pair is found. If no pair is found, return `[-1, -1]`.

#### Algorithm:

1. Loop through the array from `i = 0` to `n-1`.
2. For every index `i`, loop through the array from `j = i+1` to `n-1`.
3. Check if `nums[i] + nums[j] == target`. If so, return the positions.
4. If no pair is found, return `[-1, -1]`.


#### Code:

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int size = nums.length;
        int[] result = {-1, -1};

        for(int i = 0; i < size - 1; i++){
          for(int j= i + 1; j < size; j++){
            if(nums[i]+nums[j] == target){
              result[0] = i;
              result[1] = j;
              break;
            }
          }
        }

        return result;
    }
}
```

#### Performance Analysis:

Runtime: `35 ms`, faster than `51.81%` of Java online submissions for Two Sum.

Memory Usage: `44 MB`, less than `18.35%` of Java online submissions for Two Sum.

#

### Solution 2: HashMap (2 Loops) i.e. Two Pass

#### Approach:

The idea is to iterate through the array and store the value as key and its index in the HashMap. After storing the elements in the HashMap, iterate through the array again and check if `target - nums[i]` is present in the HashMap or not. If present, return the indices. If not present, return `[-1, -1]`.

#### Algorithm:

1. Create an empty HashMap.
2. Loop through the array.
3. For every element, store the value as key and its index as value in the HashMap.
4. Loop through the array again.
5. For every element, check if `target - nums[i]` is present in the HashMap or not.
6. If present, return the indices.
7. If not present, return `[-1, -1]`.


#### Code:

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();

        for(int i=0; i<nums.length; i++){
            map.put(nums[i], i);
        }

        for(int i=0; i<nums.length; i++){
            int complement = target - nums[i];
            if(map.containsKey(complement) && map.get(complement) != i){
              return new int[] {i, map.get(complement)};
            }
        }

        return new int[] {-1, -1};
    }
}
```

#### Performance Analysis:

Runtime: `3 ms`, faster than `67.69%` of Java online submissions for Two Sum.

Memory Usage: `43.5 MB`, less than `84.69%` of Java online submissions for Two Sum.

#

### Solution 3: HashMap (1 Loop) i.e. One Pass

#### Approach:

The idea is to iterate through the array and for every element `nums[i]`, check if `target - nums[i]` is present in the HashMap or not. If present, return the indices. If not present, store `nums[i]` in the HashMap. If no pair is found, return `[-1, -1]`.

#### Algorithm:

1. Create an empty HashMap.
2. Loop through the array.
3. For every element, check if `target - nums[i]` is present in the HashMap or not.
4. If present, return the indices.
5. If not present, store `nums[i]` in the HashMap.
6. If no pair is found, return `[-1, -1]`.

#### Code:

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        int size = nums.length;
        int[] result = {-1, -1};

        for(int i=0; i<size; i++){
            int complement = target - nums[i];
            if(map.containsKey(complement) && map.get(complement) != i){
                result[0] = i;
                result[1] = map.get(complement);
                break;
            }
            map.put(nums[i], i);
        }

        return result;
    }
}
```

#### Performance Analysis:

Runtime: `1 ms`, faster than `99.37%` of Java online submissions for Two Sum.

Memory Usage: `43.6 MB`, less than `72.93%` of Java online submissions for Two Sum.

#

### Time Complexity:
1. Brute Force: `o(n^2)`
2. HashMap (2 Loops): `o(n)`
3. HashMap (1 Loop): `o(n)`

### Space Complexity:
1. Brute Force: `o(1)`
2. HashMap (2 Loops): `o(n)`
3. HashMap (1 Loop): `o(n)`

### Recommended Solution:

Hash Table

### Related Links:
1. [Problem on LeetCode](https://leetcode.com/problems/two-sum/)
2. [Hash Map in Java](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)

### Similar Questions:
1. [3Sum](https://leetcode.com/problems/3sum/)
2. [4Sum](https://leetcode.com/problems/4sum/)
3. [Two Sum II - Input array is sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

#

### Author:
#### [Rishabh Singh](https://geeekgod.in)

[GitHub Profile](https://github.com/thisisrishabh22/)

[LeetCode Profile](https://leetcode.com/geeekgod/)
