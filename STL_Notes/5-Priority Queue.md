## <font color="yellow"><u>What is std::priority_queue?</u></f>

std::priority_queue is a container adaptor class in C++ that provides the functionality of a priority queue, which is a data structure that always keeps the largest (by default) element at the top. It means that the elements are inserted into the priority queue according to a comparison function (or a functor) that determines their order, and the top element can be inspected or removed at any time. std::priority_queue can use different underlying containers to store the elements, such as std::vector, std::deque, or std::list. [The default container is std::vector](https://en.cppreference.com/w/cpp/container/priority_queue)[1](https://en.cppreference.com/w/cpp/container/priority_queue).

To use std::priority_queue, you need to include the <\queue> header file. You can then declare a priority queue object with the syntax:

```c++
std::priority_queue<T, Container, Compare> q;
```

where T is the type of the elements, Container is the type of the underlying container, and Compare is the type of the comparison function. If you omit the Container parameter, it will use std::vector<\T> by default. If you omit the Compare parameter, it will use std::less<\T> by default, which means that the largest element will be at the top.

<u>Here is an example of how to use std::priority_queue:</u>

```c++
#include <iostream>
#include <queue>

int main()
{
    // create an empty priority queue of integers
    std::priority_queue<int> q;

    // push some elements into the priority queue
    q.push(10);
    q.push(20);
    q.push(30);

    // print the size of the priority queue
    std::cout << "The size of the priority queue is " << q.size() << "\n";

    // print the top element of the priority queue
    std::cout << "The top element is " << q.top() << "\n";

    // pop some elements from the priority queue
    q.pop();
    q.pop();

    // print the size of the priority queue after popping
    std::cout << "The size of the priority queue after popping is " << q.size() << "\n";

    // check if the priority queue is empty
    if (q.empty())
        std::cout << "The priority queue is empty\n";
    else
        std::cout << "The priority queue is not empty\n";

    return 0;
}
```

The output of this program is:

```
The size of the priority queue is 3
The top element is 30
The size of the priority queue after popping is 1
The priority queue is not empty
```

---
## <font color="yellow"><u>std::priority_queue methods:</u></f>


|Method|Description|
|---|---|
|`push(value)`|Adds the `value` to the priority queue.|
|`pop()`|Removes the element with the highest priority from the queue.|
|`top()`|Returns a reference to the element with the highest priority.|
|`empty()`|Checks if the priority queue is empty.|
|`size()`|Returns the number of elements in the priority queue.|

---

