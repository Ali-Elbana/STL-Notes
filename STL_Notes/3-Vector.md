## <font color="yellow"><u>What is std::vector?</u></f>

std::vector is a sequence container that encapsulates dynamic size arrays in C++.It is defined in the <\vector> header file as a class template, with a template type parameter that defines the type of the elements. For example, std::vector<\int> declares a std::vector whose elements are of type int.

std::vector provides various functionalities to manipulate its elements, such as inserting, erasing, resizing, swapping, accessing, iterating, etc. It also supports random access to its elements using indexes or pointers.

Unlike static arrays, std::vector can grow and shrink dynamically as needed, with its storage being handled automatically by the container. However, this also means that std::vector may consume more memory and perform worse than static arrays in some cases, especially when inserting or removing elements at positions other than the end.

std::vector is one of the most commonly used containers in C++ because it is easy to use and offers great flexibility and performance for most scenarios. 

![[stdvector specs.png]]

<u>Here is an example of how to use std::array in C++:</u>

```C++
#include <vector>

int main() 
{

  std::vector<int> my_vector = {1, 2, 3};

  // Print the first element of the vector.
  std::cout << my_vector.front() << std::endl;

  // Add an element to the end of the vector.
  my_vector.push_back(4);

  // Iterate over the vector and print each element.
  for (auto it = my_vector.begin(); it != my_vector.end(); ++it) {
    std::cout << *it << std::endl;
  }

  return 0;
}
```

Output:

```txt
1
1
2
3
4
```

---
## <font color="yellow"><u>std::vector methods:</u></f>

|Method|Functionality|Example|
|---|---|---|
|`push_back()`|Adds an element to the end of the vector.|`std::vector<int> vec;`<br>`vec.push_back(1);`|
|`pop_back()`|Removes the last element from the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`vec.pop_back();`|
|`at()`|Accesses the element at a specified index, with bounds checking.|`std::vector<int> vec = {1, 2, 3};`<br>`int value = vec.at(1); // value = 2`|
|`operator[]`|Accesses the element at a specified index, without bounds checking.|`std::vector<int> vec = {1, 2, 3};`<br>`int value = vec[1]; // value = 2`|
|`front()`|Accesses the first element of the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`int value = vec.front(); // value = 1`|
|`back()`|Accesses the last element of the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`int value = vec.back(); // value = 3`|
|`data()`|Returns a pointer to the underlying array.|`std::vector<int> vec = {1, 2, 3};`<br>`int* ptr = vec.data();`|
|`begin()`|Returns an iterator pointing to the first element of the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`auto it = vec.begin();`|
|`end()`|Returns an iterator pointing one past the last element of the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`auto it = vec.end();`|
|`size()`|Returns the number of elements in the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`int count = vec.size(); // count = 3`|
|`empty()`|Checks if the vector is empty.|`std::vector<int> vec;`<br>`bool isEmpty = vec.empty(); // isEmpty = true`|
|`clear()`|Removes all elements from the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`vec.clear();`|
|`insert()`|Inserts elements at a specified position in the vector.|`std::vector<int> vec = {1, 2, 3};`<br>`vec.insert(vec.begin() + 1, 4);`|
|`erase()`|Removes elements from the vector at a specified position or range.|`std::vector<int> vec = {1, 2, 3};`<br>`vec.erase(vec.begin() + 1);`|
|`resize()`|Resizes the vector to a specified number of elements.|`std::vector<int> vec = {1, 2, 3};`<br>`vec.resize(5);`|
|`reserve`|Requests that the vector capacity be at least enough to contain a specified number of elements without reallocation.|`std::vector<int> vec;`<b|

---


