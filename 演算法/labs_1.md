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
以下是Heap Sort的演算法步驟：

建立最大堆(Max Heap)：將未排序的數組視為一個完全二元樹，從最後一個非葉子節點開始，對每個節點進行調整，使得該節點和其子節點滿足最大堆的性質，即父節點的值大於等於子節點的值。

排序：將最大堆的根節點（即數組的第一個元素）與最後一個節點交換位置，然後將除了最後一個節點外的部分重新調整為最大堆。這樣就將最大的元素放到了最後一個位置。重複這個步驟，直到所有的節點都已經放到了正確的位置，最終得到一個有序的數組。

這是Heap Sort的基本流程，下面是一個Python實現：

python
Copy code
def heapify(arr, n, i):
    largest = i  # 將最大值初始化為父節點
    left = 2 * i + 1
    right = 2 * i + 2

    # 如果左子節點存在且大於根節點
    if left < n and arr[left] > arr[largest]:
        largest = left

    # 如果右子節點存在且大於根節點
    if right < n and arr[right] > arr[largest]:
        largest = right

    # 如果最大值不是父節點，則交換並重新調整子樹
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heap_sort(arr):
    n = len(arr)

    # 建立最大堆
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # 逐步取出最大值，並調整堆
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]  # 將最大值移動到最後
        heapify(arr, i, 0)

# 測試
arr = [12, 11, 13, 5, 6, 7]
heap_sort(arr)
print("排序後的數組：", arr)
這個演算法的時間複雜度是O(n log n)，其中n是數組的大小。

'''
Online Python Interpreter
  - [Online Python Compiler - Programiz](https://www.programiz.com/python-programming/online-compiler/)
