
# Leetcode

## 1.两数之和
在两个数组中做一次遍历后，判断输入元素是否相加可得到target，是则返回结果。
```Java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        int n = nums.length;
        for (int i = 0; i < n; ++i) {

            for (int j = i + 1; j < n; ++j) {

                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }

            }
       
        }
        
        
        return new int[0];
    }
}
```

## 20.有效括号
还没学懂栈，今天搞定
```Java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int n = nums.length;
        for (int i = 0; i < n; ++i) {
            for (int j = i + 1; j < n; ++j) {
                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }
            }
       
        }
        
        
        return new int[0];
    }
}
```

## 709.转换小写字母

遍历字符串，通过ASCLL码判断字符是否为大写，并+32使其改为小写
```Java
class Solution {
	public String toLowerCase(String s) {

		char[] chars = s.toCharArray();

		for (int i = 0; i < chars.length; i++) {
            
			char c = chars[i];
			if (c >= 'A' && c <= 'Z') {
				chars[i] = (char) (c + 32);
			}
		}
		return new String(chars);
	}
}
```