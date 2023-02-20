class Solution {
    public int findIntegers(int n) {
        int countOnes = helper(n);
        return n - countOnes + 1;
    } 
    public int helper(int n){
        int[] dp = new int[33];
        dp[0] = 0;
        dp[1] = 0;
        for(int i=2;i<33;i++){
            dp[i] = dp[i-1] + dp[i-2] + (int)Math.pow(2,i-2); 
        }
        double pow = Math.log(n)/Math.log(2);
        if(pow == (int)pow){
           return dp[(int)pow];
        }

        pow = Math.floor(pow);
        int res = dp[(int) pow];
        
        int lowestNo = (int)Math.pow(2,pow);
        
        int remains = n - lowestNo;
        
        if(remains >= lowestNo/2){
           res+= dp[(int)pow - 1] + (remains - lowestNo/2 + 1);
        }
        else res+=helper(remains);
        return res;
    }  
}
