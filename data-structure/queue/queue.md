### Queue
##### : a list that insertion is done at one end, whereas deletion is performed at the other end

---

#### 1. Abstract data type

 - enqueue(X) : inserts element  X at the end of the list
 - dequeue(): deletes the element at the start of the list
 - front(head) : index of the removal of existing element takes place
 - rear(tail) : index of an element entered most recently

![](images/queue_operation.png)

#### 2. Implementations

- by Array
	- linear queue
	- circular queue
- by Linked-list

#### 3. Use cases
 - job scheduling : in the operating system which does not use priorities, jobs are processed in the order they enter the system
 - Breath-First Search
---

### Priority Queue

---

 - 컴퓨터에서는  우선순위의  개념이  필요할  때가  종종  있다.
-   **우선순위가**  **높은**  **데이터가**  **먼저**  **큐에서**  **나가는**  **원칙**
-   적절한  우선순위만  준다면  스택이나  큐로도  충분히  만들  수  있다.
-   배열,연결리스트  등으로  구현  가능하지만 **heap이 가장 효율적인 자료구조이다.**