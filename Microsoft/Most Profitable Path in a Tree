class Solution {
    static int [] par;
    static int result; 
    static int mostProfitablePath(int[][] edges, int bob, int[] amount) {
        par = new int [amount.length];
        List<List<Integer>> adj = new ArrayList<>();
        result = (int)(-1e9);
        for(int i = 0; i < amount.length; i++) adj.add(new ArrayList<>());
        for(int []edge: edges){
            adj.get(edge[0]).add(edge[1]);
            adj.get(edge[1]).add(edge[0]);
        }
        setPar(0, adj, -1, par);
        Map<Integer, Integer> bobDist = new HashMap<>();
        int cur = bob, cnt = 0;
        while(cur != par[cur]){
            bobDist.put(cur, cnt++);
            cur = par[cur];
        }
        getResult(0, adj, bobDist, 0, amount, -1, amount[0]);
        return result;
    }

    static void getResult(int node, List<List<Integer>> adj, Map<Integer, Integer> bobDist,
                         int dist, int[] amount, int p, int income) {
        int ans = amount[node];
        boolean flag = true;
        for(int child : adj.get(node)){
            if(child != p){
                if(bobDist.containsKey(child) && dist+1 == bobDist.get(child))
                    getResult(child, adj, bobDist, dist+1, amount, node, amount[child]/2 + income);
                else if(bobDist.get(child) == null || dist + 1 < bobDist.get(child))
                    getResult(child, adj, bobDist, dist+1, amount, node, amount[child] + income);
                else getResult(child, adj, bobDist, dist+1, amount, node, income);
                flag = false;
            }
        }
        if(flag){
            //leaf node.
            result = Math.max(result, income);
        }
    }

    static void setPar(int cur, List<List<Integer>> adj, int p, int [] par){
        for(int child : adj.get(cur)){
            if(child != p){
                par[child] = cur;
                setPar(child, adj, cur, par);
            }
        }
    }
}
