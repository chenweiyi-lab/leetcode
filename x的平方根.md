
https://leetcode-cn.com/problems/sqrtx/

### 二分法
```java
class Solution {

    public int mySqrt(int x) {

        int left = 0, right = (x >> 1) + 1, result = 0;

        while(left <= right){
           int mid = (left + right) >> 1;
           if(mid != 0 && x / mid < mid) {
               right = mid - 1;
           }else{
               result = mid;
               left = mid + 1; 
           }
        }
        return result;
    }

}
```

### 牛顿迭代法
