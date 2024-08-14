Input: root = [1,2,3,4,5,6,7]

Output: [1,3,2,7,6,5,4]


class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:

        def dfs(bloob):
            temp=bloob.left
            bloob.left=bloob.right
            bloob.right=temp
        def going(root):
            if not root:
                return
            dfs(root)
            l=root.left
            r=root.right
            going(l)
            going(r)
        going(root)
        return root


# just like reversing the linked list 
