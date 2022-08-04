# leetcode-53-maximumSurray

1) class Solution:

        def maxSubArray(self, nums: List[int]) -> int:
            n = len(nums)
            maxSum = nums[0]
            minSum = sum = 0
            for i in range(n):
                sum += nums[i]
                maxSum = max(maxSum, sum - minSum)
                minSum = min(minSum, sum)

            return maxSum
            
2) dp?
 
    
