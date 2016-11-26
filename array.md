__Q: 去掉一组整型数组重复的值__

```
比如输入: [1,13,24,11,11,14,1,2]
输出: [1,13,24,11,14,2]
需要去掉重复的11 和 1 这两个元素。
```

这道问题出现在诸多的前端面试题中，主要考察个人对`Object`的使用，利用`key`来进行筛选。

```js
/**
 * unique an array
 **/
function unique(arr) {
  let hashTable = {};
  let data = [];
  for (let i = 0, l = arr.length; i < l; i++) {
    if (!hashTable[arr[i]]) {
      hashTable[arr[i]] = true;
      data.push(arr[i]);
    }
  }
  return data;
}
```

__Q: 找出下列正数组的最大差__

```
输入 [10,5,11,7,8,9]
输出 6
```

这是通过一道题目去测试对于基本的数组的最大值的查找，很明显我们知道，最大差值肯定是一个数组中最大值与最小值的差。

```js
function getMaxProfit(arr) {
  var minPrice = arr[0];
  var maxProfit = 0;

  for (var i = 0, len = arr.length; i < len; i++) {
    var currentPrice = arr[i];
    minPrice = Math.min(minPrice, currentPrice);
    var potentialProfit = currentPrice - minPrice;
    maxProfit = Math.max(maxProfit, potentialProfit);
  }

  return maxProfit;
}
```
