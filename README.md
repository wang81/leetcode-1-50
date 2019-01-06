# leetcode-1-50
1. Two Sum
method 1:
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        aux_nums = sorted(nums)
        ls = len(nums)
        found = False
        i = 0
        j = ls - 1
        while i < j and not found:
            temp = aux_nums[i] + aux_nums[j]
            if temp == target:
                found = True
            elif temp < target:
                i += 1
            else:
                j -= 1
        return [nums.index(aux_nums[i]), ls- 1- nums[::-1].index(aux_nums[j])      
method 2:
class Solution:
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        if len(nums) <= 1:
            return False
        buff_dict = {}
        for i in range(len(nums)):
            if nums[i] in buff_dict:
                return [buff_dict[nums[i]], i]
            else:
                buff_dict[target - nums[i]] = i

