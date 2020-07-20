
```java
//https://leetcode-cn.com/problems/zigzag-conversion/

class Solution {
    public String convert(String s, int numRows) {
        if(numRows == 1 ) return s;
        int rows = 2 * (numRows - 1), length = s.length(), tmpRows = rows;
        int i = 0, sit = 1, index = 0;
        char [] nc = new char[length];
        while(sit <= numRows){
            if(i < length ){
                nc[index ++] = s.charAt(i);
                if(rows != tmpRows){
                    tmpRows = rows - tmpRows;
                }
                i = i + Math.abs(tmpRows);
            }else{
                tmpRows = rows - 2 *  (numRows - sit - 1);
                i = sit ++;
            }
        }
        return new String(nc);
    }
}
```
