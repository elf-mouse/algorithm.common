__Q: 判断一个单词是否是回文？__

> 回文是指把相同的词汇或句子，在下文中调换位置或颠倒过来，产生首尾回环的情趣，叫做回文，也叫回环。比如 _mamam_ _redivider_ .

很多人拿到这样的题目非常容易想到用`for`将字符串颠倒字母顺序然后匹配就行了。其实重要的考察的就是对于`reverse`的实现。其实我们可以利用现成的函数，将字符串转换成数组，这个思路很重要，我们可以拥有更多的自由度去进行字符串的一些操作。

```js
function checkPalindrom(str) {
  return str == str.split('').reverse().join('');
}
```

__Q: 统计一个字符串出现最多的字母__

给出一段英文连续的英文字符窜，找出重复出现次数最多的字母

```
输入 ： afjghdfraaaasdenas
输出 ： a
```

前面出现过去重的算法，这里需要是统计重复次数。

```js
function findMaxDuplicateChar(str) {
  if (str.length == 1) {
    return str;
  }
  let charObj = {};
  for (let i = 0, len = str.length; i < len; i++) {
    if (!charObj[str.charAt(i)]) {
      charObj[str.charAt(i)] = 1;
    } else {
      charObj[str.charAt(i)] += 1;
    }
  }
  let maxChar = '',
      maxValue = 1;
  for (let k in charObj) {
    if (charObj[k] >= maxValue) {
      maxChar = k;
      maxValue = charObj[k];
    }
  }
  return maxChar;
}
```

__Q: 随机生成指定长度的字符串__

实现一个算法，随机生成指制定长度的字符窜。

```
比如给定长度8
输出 4ldkfg9j
```

```js
function randomString(n) {
  let str = 'abcdefghijklmnopqrstuvwxyz9876543210';
  let tmp = '',
      i = 0,
      l = str.length;
  for (i = 0; i < n; i++) {
    tmp += str.charAt(Math.floor(Math.random() * l));
  }
  return tmp;
}
```
