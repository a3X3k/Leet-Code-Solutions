```py
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        
        """
        
        nums3 = sorted(nums1 + nums2)
        
        if len(nums3) % 2 is not 0:
            
            return nums3[len(nums3) / 2]

        else:
            
            return  (nums3[(len(nums3) - 1) / 2] + nums3[(len(nums3) + 1) / 2]) / 2.0
```
