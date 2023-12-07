## Two Sum - Python Solution

The Two Sum problem asks us to find two numbers in an array that add up to a target value. Here is an efficient solution in Python:

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        Returns the indices of two numbers in an array that add up to the target value.
        :param nums: List[int] - The input array of numbers.
        :param target: int - The target value.
        :return: List[int] - The indices of the two numbers that add up to the target.
        """
        num_map = {}

        for i, num in enumerate(nums):
            complement = target - num
            if complement in num_map:
                return [num_map[complement], i]
            num_map[num] = i

        return []
```

The twoSum method of the Solution class takes in a list of integers nums and a target value target.<br>
It creates an empty dictionary num_map to store the numbers encountered so far, using the numbers as keys and their indices as values.

The method then iterates through the nums list using the enumerate function to access both the index and the value of each element in the list. <br>
For each number, it calculates the complement by subtracting the current number from the target value. <br>
If the complement is found in the dictionary (complement in num_map), it means we have found a pair of numbers that add up to the target.<br>
We return the indices stored in the dictionary along with the current index.

If the complement is not found in the dictionary, the current number and its index are added to the dictionary.

If no pair of numbers is found that adds up to the target, an empty list is returned.

This algorithm has a time complexity of O(n), where n is the size of the input list nums. By using a dictionary, we traverse the list only once, performing constant-time lookups to find the complement. <br>
This allows us to solve the problem efficiently even for large input sizes.
