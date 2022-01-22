# Day6leetcode
---

### 202. 快乐数

**编写一个算法来判断一个数 n 是不是快乐数。
「快乐数」定义为：对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和。
然后重复这个过程直到这个数变为1，也可能是无限循环 但始终变不到1。
如果 可以变为1，那么这个数就是快乐数。
如果 n 是快乐数就返回 true ；不是，则返回 false 。**

```Java
class Solution {
    public boolean isHappy(int n) {
        Set<Integer> set= new HashSet<Integer>();
        while(n!=1){
            int sum = 0;
            int temp = n;
            while(temp!=0){
                int currentPosition = temp % 10;
                sum = sum + currentPosition * currentPosition;
                temp = temp /10;
            }
            n = sum;
            if(!set.contains(n)) set.add(n);
            else return false;
        }
        if(n==1){
            return true;
        }
        return false;
    }
}
```
思路：
先用HashSet类记录sum，随后判断sum是否为1，如果sum出现为1,则为快乐数，返回true；否则进入循环，返回false；
使用contain方法判断判断sum是否出现

---

### 349. 两个数组的交集
**给定两个数组，编写一个函数来计算它们的交集。**
```Java
class Solution {
     public int[] intersection(int[] nums1, int[] nums2) {
        HashSet<Integer> hashSet1 = new HashSet<>();
        HashSet<Integer> hashSet2 = new HashSet<>();
        for (int i : nums1) {
            hashSet1.add(i);
        }
        for (int i : nums2) {
            hashSet2.add(i);
        }
        HashSet<Integer> intersection  = new HashSet<>();
        for (Integer integer : hashSet1) {
            if (hashSet2.contains(integer)){
                intersection .add(integer);
            }
        }
    
        int index = 0;
        int[] list = new int[intersection .size()];
        for (Integer integer : intersection ) {
            list[index++] = integer;
        }
        return list;
     }
}
```
思路：将两个数组的值分别放入hashset中，然后创建hashset交集。再对其中一个表进行遍历,并判断里面的元素是否有包含另一个hashset的元素，如果包含，则将包含的元素添加到新的交集hahsset中。最后将交集hashset的值转到新的int数组index里。

---

### 796. 旋转字符串

**给定两个字符串, A和B。
A的旋转操作就是将A最左边的字符移动到最右边。例如, 若A = 'abcde'，在移动一次之后结果就是'bcdea'。如果在若干次旋转操作之后，A能变成B，那么返回True。**

```Java
class Solution
public boolean rotateString(String s, String goal) {
        int lenS = s.length(), lenG = goal.length();
        if(lenG != lenS){
            return false;
        }
        String doubleS = s + s;
        if(doubleS.contains(goal)){
            return true;
        }
        return false;
    }
}
```

思路：先判断比较AB长度，若否则直接返回false；随后令s+s，相当于把A的最左边的字符全部移动到了右边的并集 看它是否包含B。