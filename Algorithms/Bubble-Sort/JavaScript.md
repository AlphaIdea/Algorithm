1. 每次比较两个相邻元素，若TA们顺序错误则交换其顺序。
2. 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。
3. 针对所有的元素重复以上的步骤，除了最后一个。
4. 重复以上步骤，直到最后一个尚未归位的数。
```javascript
function bubbleSort(arr) {
    const len = arr.length;
    for (let i = 0; i <= len; i++) {
        for (let j = 0; j <= len - i; j++) {
            if (arr[j] > arr[j + 1]) {        // 相邻元素两两对比
                [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];// 元素交换
            }
        }
    }
    return arr;
}
```