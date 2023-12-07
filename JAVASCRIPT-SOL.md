## Two Sum - JavaScript Solution

The Two Sum problem asks us to find two numbers in an array that add up to a target value. Here is an efficient solution in JavaScript that utilizes a Hash Map:

javascript
/**
 * Returns the indices of two numbers in an array that add up to the target value.
 * @param {number[]} nums - The input array of numbers.
 * @param {number} target - The target value.
 * @return {number[]} - The indices of the two numbers that add up to the target.
 */
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


The twoSum function takes in an array of numbers nums and a target value target.<br> 
It creates an empty Hash Map numMap to store the numbers encountered so far, using the numbers as keys and their indices as values.

The function then iterates through the nums array using a for loop.<br>
For each number, it calculates the complement by subtracting the current number from the target value. <br>
If the complement is found in the Hash Map (complement in numMap), it means we have found a pair of numbers that add up to the target.<br>
We return the indices stored in the Hash Map along with the current index.

If the complement is not found in the Hash Map, the current number and its index are added to the Hash Map.

If no pair of numbers is found that adds up to the target, an empty array is returned.

This algorithm has a time complexity of O(n), where n is the size of the input array nums.<br>
By using a Hash Map, we traverse the array only once, performing constant-time lookups to find the complement. <br>
This allows us to solve the problem efficiently even for large input sizes.
