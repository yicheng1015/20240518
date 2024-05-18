# GenAI_Algorithm_lab1 ==> heap sort的各種實作
- `提問詞`:請寫出heap sort的演算法
- `提問詞`:請計算heap sort演算法的時間複雜度
- `提問詞`:請用Python寫出heap sort的演算法
- `提問詞`:請用C寫出heap sort的演算法
- `提問詞`:請用C++寫出heap sort的演算法
- `提問詞`:請用JAVA寫出heap sort的演算法
- `提問詞`:請用Rust寫出heap sort的演算法
- `提問詞`:請用go寫出heap sort的演算法
- `提問詞`:請用C#寫出heap sort的演算法
- `提問詞`:請用Javascript#寫出heap sort的演算法

  
'''
堆積排序（Heap Sort）是一種利用堆積（Heap）結構來完成排序的演算法。讓我為您簡要介紹一下堆積排序的原理和程式碼範例。

概念：
堆積排序使用最大堆積（Max Heap）或最小堆積（Min Heap）來排序。
最大堆積：父節點的值大於子節點的值。
最小堆積：父節點的值小於子節點的值。
步驟：
建立最大堆積：將待排序的陣列轉換成最大堆積。
交換根節點和最後一個節點，然後縮小堆積範圍。
重複上述步驟，直到整個陣列排序完成。
程式碼範例（JavaScript）：
JavaScript

Array.prototype.heap_sort = function() {
    const arr = this.slice(0);

    function swap(i, j) {
        const tmp = arr[i];
        arr[i] = arr[j];
        arr[j] = tmp;
    }

    function max_heapify(start, end) {
        const dad = start;
        let son = dad * 2 + 1;

        if (son >= end) return;

        if (son + 1 < end && arr[son] < arr[son + 1]) {
            son++;
        }

        if (arr[dad] < arr[son]) {
            swap(dad, son);
            max_heapify(son, end);
        }
    }

    const len = arr.length;

    for (let i = Math.floor(len / 2) - 1; i >= 0; i--) {
        max_heapify(i, len);
    }

    for (let i = len - 1; i > 0; i--) {
        swap(0, i);
        max_heapify(0, i);
    }

    return arr;
};

const inputArray = [3, 5, 3, 0, 8, 6, 1, 5, 8, 6, 2, 4, 9, 4, 7, 0, 1, 8, 9, 7, 3, 1, 2, 5, 9, 7, 4, 0, 2, 6];
const sortedArray = inputArray.heap_sort();
console.log(sortedArray);
AI 產生的代碼。請仔細檢視及使用。 深入了解常見問題集。
這段程式碼示範了如何使用堆積排序將一個陣列排序。您可以根據需要調整程式碼，例如改成其他語言的實作。
'''
