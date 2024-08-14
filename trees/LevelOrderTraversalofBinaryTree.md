Level Order Traversal of Binary Tree
Solved 
Given a binary tree root, return the level order traversal of it as a nested list, where each sublist contains the values of nodes at a particular level in the tree, from left to right

Input: root = [1,2,3,4,5,6,7]

Output: [[1],[2,3],[4,5,6,7]]


# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        if not root:
            return []
        res=[]
        q=deque([root])
        minires=[]
        while q:
            minires = []
            for i in range(len(q)):
                blob=q.popleft()
                minires.append(blob.val)
                if blob.left:
                    q.append(blob.left)     
                if blob.right:
                    q.append(blob.right)
            res.append(minires)
        return res
                


# here we us ethe BFS using the deque where we add to the right and pop from the left and for getting answer inthe level wise we use the for loop until that level we add to minires ad append and to res.
