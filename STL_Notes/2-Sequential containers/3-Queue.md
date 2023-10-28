## <font color="yellow"><u>What is std::queue?</u></f>

std::queue is a container adaptor class in C++ that provides the functionality of a queue, which is a first-in, first-out (FIFO) data structure. It means that the elements are inserted at the back of the queue and removed from the front of the queue. std::queue can use different underlying containers to store the elements, such as std::deque, std::list, or std::vector. The default container is std::deque. To use std::queue, you need to include the <\queue> header file.

<u>Here is an example of how to use std::queue:</u>

```c++
#include <iostream>
#include <queue>

int main()
{
    // create an empty queue of integers
    std::queue<int> q;

    // push some elements into the queue
    q.push(10);
    q.push(20);
    q.push(30);

    // print the size of the queue
    std::cout << "The size of the queue is " << q.size() << "\n";

    // print the front and back elements of the queue
    std::cout << "The front element is " << q.front() << "\n";
    std::cout << "The back element is " << q.back() << "\n";

    // pop some elements from the queue
    q.pop();
    q.pop();

    // print the size of the queue after popping
    std::cout << "The size of the queue after popping is " << q.size() << "\n";

    // check if the queue is empty
    if (q.empty())
        std::cout << "The queue is empty\n";
    else
        std::cout << "The queue is not empty\n";

    return 0;
}
```

The output of this program is:

```
The size of the queue is 3
The front element is 10
The back element is 30
The size of the queue after popping is 1
The queue is not empty
```

---
## <font color="yellow"><u>std::queue methods:</u></f>

|Method|Description|
|---|---|
|`push(value)`|Adds the `value` to the back of the queue.|
|`pop()`|Removes the element at the front of the queue.|
|`front()`|Returns a reference to the element at the front of the queue.|
|`back()`|Returns a reference to the element at the back of the queue.|
|`empty()`|Checks if the queue is empty.|
|`size()`|Returns the number of elements in the queue.|

---
