’‘’java
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
'''
