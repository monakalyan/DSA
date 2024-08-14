Depth of Binary Tree
Solved 
Given the root of a binary tree, return its depth.

The depth of a binary tree is defined as the number of nodes along the longest path from the root node down to the farthest leaf node



class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:

        def dfs(blob):
            if not blob:
                return 0
            l=dfs(blob.left)
            r=dfs(blob.right)
            return max(l,r)+1
        return dfs(root)



.
