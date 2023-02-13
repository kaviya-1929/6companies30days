class Solution {
    public int[][] matrixBlockSum(int[][] mat, int k) {
        int m = mat.length;
        int n = mat[0].length;
        int[][] res = new int[m][n];

        for (int i = 0; i < m; i++) {
            for(int j = 1; j < n; j++) {
                mat[i][j] += mat[i][j - 1];
            }
        }

        for (int j = 0; j < n; j++) {
            for(int i = 1; i < m; i++) {
                mat[i][j] += mat[i - 1][j];
            }
        }

        for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                res[i][j] = getSum(mat, i, j, k);
            }
        }

        return res;
    }
    private int getSum(int[][] mat, int i, int j, int k) {
        int m = mat.length;
        int n = mat[0].length;
        int endRow = Math.min(m - 1, i + k);
        int endCol = Math.min(n - 1, j + k);

        int sum = mat[endRow][endCol];
        int n1 = (j - k - 1 >= 0) ? mat[endRow][j - k - 1] : 0;
        int n2 = (i - k - 1 >= 0) ? mat[i - k - 1][endCol] : 0;
        int n3 = (j - k - 1 >= 0 && i - k - 1 >= 0) ? mat[i - k - 1][j - k - 1] : 0;

        return sum - n1 - n2 + n3;
    }
}
