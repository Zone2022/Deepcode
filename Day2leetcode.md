# Days2leetcode
## 88. 合并两个有序数组
将nums1中元素与nums2中元素一一比较后通过条件判断按num2中大小顺序放入num1中，然后遍历一次nums1，把顺序调正。
```Java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        while(n>0&&m>0){

            if(nums1[m-1]>nums2[n-1]){
                nums1[n+m-1]=nums1[m-1];
                m--;
            }else{
                nums1[n+m-1]=nums2[n-1];

                n--;
            }
        }
        for(int i=0;i<n;i++){

            nums1[i]=nums2[i];
        }
    }

}
```