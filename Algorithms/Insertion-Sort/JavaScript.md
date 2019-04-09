1. 将待排序序列第一个元素看做一个有序序列，把第二个元素到最后一个元素当成是未排序序列。
2. 从头到尾依次扫描未排序序列，将扫描到的每个元素插入有序序列的适当位置。
```javascript
function insertionSort(arr) {
    if (arr.length <= 1) {
        return arr;
    }
    for (let i = 1; i < arr.length; i++) {
        const key = arr[i];

        let j = i - 1;
        // 若 arr [i] 前有大于 arr [i] 的值，向后移位，腾出空间，直到一个 <=arr [i] 的值
        for (; j >= 0; j--) {
            if (arr[j] > key) {
                arr[j + 1] = arr[j];
            }
            else {
                break;
            }
        }
        arr[j + 1] = key;
    }
    return arr;
}
```

