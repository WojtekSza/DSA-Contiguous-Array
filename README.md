# DSA-Contiguous-Array
Given a binary array nums, return the maximum length of a contiguous subarray with an equal number of 0 and 1.
```
Input: nums = [0,1,0]
Output: 2
Explanation: [0, 1] (or [1, 0]) is a longest contiguous subarray with equal number of 0 and 1.
```
```
class Solution:
    def findMaxLength(self, nums: List[int]) -> int:
        ans=curr=0 
        m={0:-1} 
        for i,j in enumerate(nums): #Time cost of itertaion loop O(n)
            curr+=2*j-1 #O(1)
            if curr in m:  #O(1)
                ans=max(ans,i-m[curr]) #O(1)
            else:  #O(1)
                m[curr]=i #O(1)
        return ans #Space cost O(1)
'''
Total time cost O(n)
Total space cost O(1)
'''
```
