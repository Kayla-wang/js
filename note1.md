## 哈希

##### 给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 target  的那 两个 整数，并返回它们的数组下标。/
```let  nums = [2,7,11,15], target = 9
const twoSum = function(nums, target) {
// 这里我用对象来模拟 map 的能力
const diffs = {}
// 缓存数组长度
const len = nums.length
// 遍历数组
for(let i=0;i<len;i++) {
// 判断当前值对应的 target 差值是否存在（是否已遍历过）
if(diffs[target-nums[i]]!==undefined) {
// 若有对应差值，那么答案get！
return [diffs[target - nums[i]], i]
}
// 若没有对应差值，则记录当前值
diffs[nums[i]]=i
}
};
