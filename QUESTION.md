# Two Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

## Example


Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]

Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]


## Constraints

- 2 <= nums.length <= 10^4
- -10^9 <= nums[i] <= 10^9
- -10^9 <= target <= 10^9
- Only one valid answer exists.

## Efficiency
- The naive approach would be to use a nested loop to calculate the sum of every pair of numbers in the array. This would result in a time complexity of O(n^2).
- However, we can optimize the solution to have a time complexity of less than O(n^2).
- One approach is to use a hashmap to store the difference between the target and each element of the array as the key, and the index as the value.
- We can iterate through the array, and for each element num, check if the hashmap contains num. If it does, we have found the pair and can return their indices.
- If the hashmap does not contain num, we add num as the key and its index as the value to the hashmap.
- This approach has a time complexity of O(n) since we only iterate through the array once to check the hashmap and update it.
- The space complexity is O(n) as we need to store the hashmap.

## Python Implementation
python
def twoSum(nums: List[int], target: int) -> List[int]:
    num_map = {}

    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i

    return []


## JavaScript Implementation
javascript
const twoSum = (nums, target) => {
  const numMap = {};

  for (let i = 0; i < nums.length; i++) {
    const num = nums[i];
    const complement = target - num;

    if (complement in numMap) {
      return [numMap[complement], i];
    }

    numMap[num] = i;
  }

  return [];
};


## Follow-up
- The algorithm described above already achieves the desired time complexity of less than O(n^2).
- There is no further optimization possible without changing the basic approach.
- Therefore, this solution is considered efficient for the given problem.
