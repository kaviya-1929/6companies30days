
class Solution {

    public static int numOfNodes(TreeNode node){

        if(node == null){
            return 0;
        }

        return numOfNodes(node.left) + numOfNodes(node.right) + 1;

    }

    public static int getSum(TreeNode node){

        if(node == null){
            return 0;
        }

        return getSum(node.left) + getSum(node.right) + node.val;

    }

    public static void helper(TreeNode node){

        if(node == null){
            return;
        }

        int sum = getSum(node.left) + getSum(node.right) + node.val;
        int n = numOfNodes(node.left) + numOfNodes(node.right) + 1;

        if(n!=0 && (node.val == (sum/n))){
            ans++;
        }

        helper(node.left);
        helper(node.right);

    }

    public static int ans;

    public int averageOfSubtree(TreeNode root) {

        ans = 0;
        
        helper(root);

        return ans;

    }

}
