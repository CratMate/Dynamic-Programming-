# Dynamic-Programming-
import java.util.*;
public class Hello {
    public static int max(int a,int b)
    {
        return a>b?a:b;
    }
    public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		String s1="AGGTAB";
		String s2="GXTXAYB";
		int m=s1.length()+1;
		int n=s2.length()+1;
		int LCS[][]=new int[m][n];
	    for(int i=1;i<m;i++)
	    {
	        for(int j=1;j<n;j++)
	        {
	            if(s1.charAt(i-1)==s2.charAt(j-1))
	            {
	                LCS[i][j]=LCS[i-1][j-1]+1;//if equal prev diagonal+1
	            }
	            else{
	                LCS[i][j]=max(LCS[i-1][j],LCS[i][j-1]);//max of top and left
	            }
	        }
	    }
        System.out.print("Longest Common Subsequence = "+LCS[m-1][n-1]);
	}
}
