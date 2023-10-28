## <font color="yellow"><u>What is std::stack?</u></f>

std::stack is a container adaptor class in C++ that provides the functionality of a stack, which is a last-in, first-out (LIFO) data structure. It means that the elements are inserted and removed from the same end of the container, known as the top of the stack. The class template acts as a wrapper to the underlying container, which can be any standard container class or some other specifically designed container class. The underlying container must support the following operations: empty(), size(), back(), push_back(), and pop_back(). The standard container classes std::vector, std::deque, and std::list satisfy these requirements. [By default, if no container class is specified for a particular stack class instantiation, the standard container std::deque is used](https://en.cppreference.com/w/cpp/container/stack)[1](https://en.cppreference.com/w/cpp/container/stack).

<u>Here is an example of how to use std::stack:</u>

```c++
#include <iostream>
#include <stack>

int main()
{
    // create an empty stack of integers
    std::stack<int> s;

    // push some elements into the stack
    s.push(10);
    s.push(20);
    s.push(30);

    // print the size of the stack
    std::cout << "The size of the stack is " << s.size() << "\n";

    // print the top element of the stack
    std::cout << "The top element is " << s.top() << "\n";

    // pop some elements from the stack
    s.pop();
    s.pop();

    // print the size of the stack after popping
    std::cout << "The size of the stack after popping is " << s.size() << "\n";

    // check if the stack is empty
    if (s.empty())
        std::cout << "The stack is empty\n";
    else
        std::cout << "The stack is not empty\n";

    return 0;
}
```

The output of this program is:

```
The size of the stack is 3
The top element is 30
The size of the stack after popping is 1
The stack is not empty
```

---
## <font color="yellow"><u>std::stack methods:</u></f>

|Method|Description|
|---|---|
|`push_back(value)`|Adds the `value` to the back of the deque.|
|`push_front(value)`|Adds the `value` to the front of the deque.|
|`pop_back()`|Removes the element at the back of the deque.|
|`pop_front()`|Removes the element at the front of the deque.|
|`front()`|Returns a reference to the element at the front of the deque.|
|`back()`|Returns a reference to the element at the back of the deque.|
|`at(index)`|Returns a reference to the element at the specified index.|
|`empty()`|Checks if the deque is empty.|
|`size()`|Returns the number of elements in the deque.|
|`clear()`|Removes all elements from the deque.|

---

