Convert-sorted-array-to-binary-search-tree
==========================================
/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    public TreeNode sortedArrayToBST(int[] num) {
        // Start typing your Java solution below
        // DO NOT write main() function
    //if(num.length==0) return null;
   return addToTree(num, 0, num.length - 1);
    }
    
    public static TreeNode addToTree(int[] num, int start, int end){
        
    if (end < start) {
    return null;
     }
     
    int mid = (end + start) / 2;
    TreeNode n = new TreeNode(num[mid]);
    n.left = addToTree(num, start, mid - 1);
    n.right = addToTree(num, mid + 1, end);
    return n;
    }
}
