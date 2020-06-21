# 删除排序数组中的重复项

### 要求：  
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。  
不要使用额外的数组空间，你必须在 原地 修改输入数组 并在使用 O(1) 额外空间的条件下完成。

### 说明：
为什么返回数值是整数，但输出的答案是数组呢?  
请注意，输入数组是以「引用」方式传递的，这意味着在函数里修改输入数组对于调用者是可见的。  


**代码**：
```java
public int removeDuplicates(int[] nums) {
        if(nums.length == 0) return 0;
        int i = 0;
        for(int j = 1; j < nums.length; j++){
            if(nums[j] != nums[i]){
                i++;
                nums[i] = nums[j];
            }
        }
        return i + 1;
    }
}
```
**方法**：双指针法算法  

数组完成排序后，我们可以放置两个指针i和j，其中i是慢指针，而j是快指针。只要 nums[i] = nums[j]，我们就增加j以跳过重复项；  
当我们遇到nums[j]≠nums[i]时，跳过重复项的运行已经结束，因此我们必须把它（nums[j]）的值复制nums[i+1]；  
然后递增i，接着我们将再次重复相同的过程，直到j到达数组的末尾为止。
  
**复杂度分析**：  
时间复杂度：O(n)，假设数组的长度是n，那么i和j分别最多遍历n步。  
空间复杂度：O(1)。  

[题目地址](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)
