```py
class ListNode(object):
    
    def __init__(self, x):
        
        self.val = x
        self.next = None


class Solution(object):
    
    def mergeKLists(self, lists):

        if not lists:

            return None
    
    
        def mergeTwoLists(l1, l2):
        
            """
            :type l1: ListNode
            :type l2: ListNode
            :rtype: ListNode
            """
        
            temp = main = ListNode(0)
        
            while l1 and l2:
            
                if l1.val < l2.val:
                
                    temp.next = l1
                    l1 = l1.next
            
                else:
                
                    temp.next = l2
                    l2 = l2.next
            
                temp = temp.next
        
            temp.next = l1 or l2
        
            return main.next
        
            
        start, end = 0, len(lists) - 1
                
        while end > 0:

            lists[start] = mergeTwoLists(lists[start], lists[end])
            
            start += 1
            end -= 1
            
            if start >= end:
                
                start = 0
        
        return lists[0] 
```
