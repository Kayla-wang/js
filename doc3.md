给定一个未排序的整数数组 nums ，找出数字连续的最长序列（不要求序列元素在原数组中连续）的长度。
请你设计并实现时间复杂度为 O(n) 的算法解决此问题。
输入：nums = [100,4,200,1,3,2]
输出：4
解释：最长数字连续序列是 [1, 2, 3, 4]。它的长度为 4。

```
let nums = [0,3,7,2,5,8,4,6,0,1]
var longestConsecutive = function(nums) {
    if (nums.length === 0 || !Array.isArray(nums)) return 0;
    nums.sort((a,b) => a-b);
    let max = -Infinity;
    let times = 1;
    for (let j = 1; j < nums.length; j++) {
        if (nums[j] === nums[j-1] + 1) {
            times++;
        } else if(nums[j] === nums[j-1]) {
            continue;
        } else {
            max = Math.max(max, times);
            times = 1;
        }
    }
    return Math.max(times, max);
};
```
