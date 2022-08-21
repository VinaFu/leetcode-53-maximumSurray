# leetcode-53-maximumSurray

1) class Solution:动态

        class Solution:
            def maxSubArray(self, nums: List[int]) -> int:
                maxSub = nums[0]
                curSum = 0
                for n in nums:
                    if curSum < 0:
                        curSum = 0
                    curSum += n
                    # adding up, till current sum is greater than 0.
                    maxSub = max(curSum, maxSub)
                return maxSub
        
            
2) 暴力/还是有动态在里面

        def maxSubArray(nums):
            tmp = nums[0]
            maxSum = tmp
            n = len(nums)
            for i in range(1,n):
                    # 当当前序列加上此时的元素的值大于tmp的值，说明最大序列和可能出现在后续序列中，记录此时的最大值
                if tmp + nums[i]>nums[i]:
                    maxSum = max(maxSum, tmp+nums[i])
                    tmp = tmp + nums[i]
                else:
                    #当tmp(当前和)小于下一个元素时，当前最长序列到此为止。以该元素为起点继续找最大子序列,
                    # 并记录此时的最大值
                    max_ = max(maxSum, tmp, tmp+nums[i], nums[i])
                    tmp = nums[i]

            return maxSum
        nums = [1,2,3,4]
        print(maxSubArray(nums))
        
        
  3) 暴力：
  
          def maxSubArray(nums):
            maxSum = nums[0]
            n = len(nums)
            for i in range(n):
                if nums[i]>maxSum:
                    maxSum = nums[i]
                for j in range(i+1, n):
                    subMax = sum(nums[i:j+1])
                    if subMax > maxSum:
                        maxSum = subMax

            return maxSum





 
    
