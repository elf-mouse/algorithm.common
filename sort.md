__Q: 排序算法__

如果抽到算法题目的话，应该大多都是比较开放的题目，不限定算法的实现，但是一定要求掌握其中的几种，所以冒泡排序，这种较为基础并且便于理解记忆的算法一定需要熟记于心。冒泡排序算法就是依次比较大小，小的的大的进行位置上的交换。

```js
function bubbleSort(arr) {
  for (let i = 0, l = arr.length; i < l-1; i++) {
    for (let j = i+1; j < l; j++) {
      if (arr[i]>arr[j]) {
        let tem = arr[i];
        arr[i] = arr[j];
        arr[j] = tem;
      }
    }
  }
  return arr;
}
```

除了冒泡排序外，其实还有很多诸如插入排序，快速排序，希尔排序等。每一种排序算法都有各自的特点。全部掌握也不需要，但是心底一定要熟悉几种算法。

比如快速排序，其效率很高。算法参考某个元素值，将小于它的值，放到左数组中，大于它的值的元素就放到右数组中，然后递归进行上一次左右数组的操作，返回合并的数组就是已经排好顺序的数组了。

```js
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  let leftArr = [];
  let rightArr = [];
  let q = arr[0];
  for(let i = 1, l = arr.length; i<l; i++) {
    if (arr[i]>q) {
      rightArr.push(arr[i]);
    } else {
      leftArr.push(arr[i]);
    }
  }

  return [].concat(quickSort(leftArr), [q], quickSort(rightArr));
}
```

> 通过动画演示算法的实现 - [HTML5 Canvas Demo: Sorting Algorithms](http://math.hws.edu/eck/jsdemo/sortlab.html)
