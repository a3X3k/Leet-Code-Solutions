```py
# Definition for singly-linked list.

class ListNode(object):
    
     def __init__(self, val = 0, next = None):
            
        self.val = val
        self.next = next

# Definition for a binary tree node.

class TreeNode(object):
    
    def __init__(self, val = 0, left = None, right = None):
        
        self.val = val
        self.left = left
        self.right = right

class Solution(object):
    
    head = None
    
    def sortedListToBST(self, head):
        """
        :type head: ListNode
        :rtype: TreeNode
        """
        
        self.head = head
        temp = head
        size = 0
        
        while temp:
            
            temp = temp.next
            size += 1
        
        return self.sort_list(0, size)
    
    
    def sort_list(self, start, end):
        
        if start == end:
            
            return 
        
        mid = start + ( end - start ) / 2
        
        left = self.sort_list(start, mid)
        
        temp = TreeNode(self.head.val)
        
        temp.left = left
        
        self.head = self.head.next
        
        temp.right = self.sort_list(mid + 1, end)
        
        return temp
```
