## Lowest common ancestor of a binary tree
### Traverse the tree using the bottom-up manner using post-order traversal, when we find q and p in the right and left subtree respectively. then we can determine that the node is the lowest common ancestor

### 1. determine the return value and parameters of the recursive function
return value is the TreeNode and parameters are the input of the function
### 2. determine termination conditions
when we find q or p or a null node
### 3. determine single-level logic 
if we find q then it will return the node to the top level, unless it could find another node equals to p, then their parent node would be the lowest common ancestor.


```
class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(root == p || root == q||root == null){
            return root;
        }
        TreeNode left = lowestCommonAncestor(root.left,p,q);
        TreeNode right = lowestCommonAncestor(root.right,p,q);
        if(right!=null && left!=null){
            return root;
        }else if(right==null && left!=null){
            return left;
        }else if(right!=null && left==null){
            return right;
        }else{
            return null;
        }
    }
}
```

