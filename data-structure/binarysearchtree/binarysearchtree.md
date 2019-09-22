### Binary Search Tree

---

#### 1. Binary Search
##### :  탐색의 매 단계마다 검색해야 할 리스트의 크기가 절반으로 줄어드는 탐색 방법. 반드시  데이터의  배열이  정렬  되어있어야  한다. 따라서  데이터의  삽입이나  삭제가  빈번할  경우  적합하지  않고  고정된  데이터에  대한  탐색에  적합하다.


##### 1-1 sequential search vs binary search

- sequential search 
	- simply store the keys in a linear array and search element sequentially
	- insertion : O(1)
	- searching : O(N) 
- binary search
	- insertion/deletion : O(N)
	- searching : O(logN)

##### 1-2. implementation

- binary search using recursive
```
int recursiveBinarySearch(int[] sortedArray, int start, int end, int key) {

	if (start < end) {
		int mid = start + (end - start) / 2;
		if (key < sortedArray[mid]) {
			return recursiveBinarySearch(sortedArray, start, mid, key);
		} else if (key > sortedArray[mid]) {
			recursiveBinarySearch(sortedArray, mid + 1, end, key);
		} else {
			return mid;
		}
	} 
	return -(start + 1);
}
```

- binary search using divide and conquer
```
int binarySearch(int[] inputArr, int key) {
	int start = 0;
	int end = inputArr.length - 1;
	
	while (start < end) {
		int mid = (start + end) / 2;
		if (key < inputArr[mid]) {
			end = mid - 1;
		} else if (key > inputArr[mid]) {
			start = mid + 1;
		} else {
			return mid;
		}
	} 
	return -1;
} 
```

#### 2. Binary Search Tree

-   Binary-search와  근본적으로  같은  원리. 이진탐색  트리는  비교적  빠른  시간안에  데이터의  삽입과  삭제를  끝마칠  수  있는  구조로  되어있다.
-   이진탐색  트리가  균형  트리라면 , 탐색의  시간복잡도는  당연히 O(logn)이다. 하지만  균형이  깨진다면(한쪽으로  치우치는  경우  등) O(n)이  된다.
-   따라서  이진탐색  트리에서는  **트리의 균형을 유지하는것이 가장 중요하다**.


##### 2-1. binary search tree

one of the most fundamental problems in data structure design
- there are a set of records R1, R2,..., Rn which are associated with distinct key values X1, X2,..., Xn, respectively.
- given a search key x, find the record if it occurs in the set

for every node X in the tree,
- the values of all the keys in its left subtree are smaller than the key value in X
- the values of all the keys in its right subtree are larger than the key value in X

