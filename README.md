# graphs
no of islands
https://leetcode.com/problems/number-of-islands/submissions/

>>java code
class Solution {
    public int numIslands(char[][] grid) {
        int count=0;
        for (int i=0; i<grid.length; i++){
            for (int j=0; j<grid[0].length; j++){
                if (grid[i][j]=='1'){
                    count++;
                    DFS(grid,i,j);
                }
            }
        }
        return count;
    }
    
public static void DFS (char [][] grid, int x, int y){
        if (x<0 || x>=grid.length || y<0 || y>=grid[0].length || grid[x][y]=='0') return;
        grid[x][y]='0';
        DFS(grid,x+1,y);
        DFS(grid,x-1,y);
        DFS(grid,x,y+1);
        DFS(grid,x,y-1);
    }
}

flood fill
https://leetcode.com/problems/flood-fill/submissions/

>> java code
class Solution {
    public int[][] floodFill(int[][] image, int sr, int sc, int newColor) {
        int x=image[sr][sc];
        if(x==newColor)
            return image;
        image[sr][sc]=newColor;
        if(sr>0 && image[sr-1][sc]==x)
			floodFill(image, sr-1, sc, newColor);
        if(sr<image.length-1 && image[sr+1][sc]==x)
			floodFill(image, sr+1, sc, newColor);
        if(sc>0 && image[sr][sc-1]==x)
			floodFill(image, sr, sc-1, newColor);
        if(sc<image[0].length-1 && image[sr][sc+1]==x)
			floodFill(image, sr, sc+1, newColor);
        return image;
    }
}
