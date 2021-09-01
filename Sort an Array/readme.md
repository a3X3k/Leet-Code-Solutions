```py
class Solution(object):
    
    def sortArray(self, nums):
        
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        
        def mergeSort(start, end, nums):
            
            if end - start <= 1:

                return
            
            mid = start + (end - start) // 2
            
            mergeSort(start, mid, nums)
            mergeSort(mid, end,  nums)
            
            right = mid
            temp = []
            
            for left in range(start, mid):
                
                while right < end and nums[right] < nums[left]:
                    
                    temp.append(nums[right])
                    right += 1
                    
                temp.append(nums[left])
                
            nums[start:start+len(temp)] = temp

        mergeSort(0, len(nums), nums)
        
        return nums
```
