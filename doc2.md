给你一个字符串数组，请你将 字母异位词 组合在一起。可以按任意顺序返回结果列表。
字母异位词 是由重新排列源单词的字母得到的一个新单词，所有源单词中的字母通常恰好只用一次。

```
let strs = ["eat", "tea", "tan", "ate", "nat", "bat"]
var groupAnagrams = function(strs) {
const map = new Map();
for (let str of strs) {
let array = Array.from(str);
array.sort();
let key = array.toString();
let list = map.get(key) ? map.get(key) : new Array();
list.push(str);
map.set(key, list);
}
return Array.from(map.values());
};

```
