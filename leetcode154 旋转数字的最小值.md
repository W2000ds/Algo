## LT58最后一个单词的长度

```java
class Solution {
    public int lengthOfLastWord(String s) {
        char[] str= s.toCharArray();
        int n = str.length-1;
        int count=0;
        while(str[n]==' ')
            n--;
        
        while(n>=0&&str[n]!=' '){
            n--;
            count++;
        }
        return count;
    }
}
```

```java
class Solution {
    public int lengthOfLastWord(String s) {
        s = s.trim();
        return s.length() - s.lastIndexOf(" ") - 1;
    }
}
```



## LT154旋转数组的最小数字

```java
class Solution {
    public int minArray(int[] numbers) {
        int low=0;
        int high = numbers.length-1;
        while(low<high){//不能等于，high--可能变成-1
            int mid= low+((high-low)/2);
            if(numbers[mid]<numbers[high])
                high=mid;
            else if(numbers[mid]>numbers[high])
                low=mid+1;
            else
                high--;
        }
        return numbers[high];
    }
}
```

参考leetcode官方题解