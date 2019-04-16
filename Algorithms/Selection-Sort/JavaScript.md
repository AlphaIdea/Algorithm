1. 首先在未排序序列中找到最小（大）元素，和排序序列的第一位交换
2. 再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾
3. 以此类推，直到所有元素均排序完毕。
```javascript
function selectionSort(arr) {
    if (!Array.isArray(arr) || arr.length < 2) {
        return arr;
    }

    for (let i = 0, len = arr.length; i < len; i++) {
        // 寻找 [i, n) 中的最小值
        let min = i;
        for (let j = i + 1; j < len; j++) {
            if (arr[j] < arr[min]) {
                min = j;
            }
        }
        [arr[i], arr[min]] = [arr[min], arr[i]];
    }
    return arr;
}
```