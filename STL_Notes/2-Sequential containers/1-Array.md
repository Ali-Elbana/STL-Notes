## <font color="yellow"><u>What is std::array?</u></f>

[std::array in C++ is a container class that encapsulates a fixed-size array of elements of the same type](https://en.cppreference.com/w/cpp/container/array)[1](https://en.cppreference.com/w/cpp/container/array). [Unlike a C-style array, it does not decay to a pointer automatically, and it knows its own size](https://www.geeksforgeeks.org/stdarray-in-cpp/)[2](https://www.geeksforgeeks.org/stdarray-in-cpp/). [It also provides some benefits of a standard container, such as supporting assignment, iterators, algorithms, etc](https://stackoverflow.com/questions/4424579/stdvector-versus-stdarray-in-c)[3](https://stackoverflow.com/questions/4424579/stdvector-versus-stdarray-in-c).

Some of the advantages of using std::array over a C-style array are:

- It is safer and more convenient to use, as it prevents buffer overflow and out-of-bounds errors.
- It can be copied and assigned easily, as it has an implicitly-defined copy constructor and copy assignment operator.
- It can be passed to functions by value or by reference, without losing the size information.
- It can be used with STL algorithms and iterators, as it has begin() and end() member functions that return random access iterators.

Some of the disadvantages of using std::array over a C-style array are:

- It requires the size to be known at compile time, as it is a template parameter. This limits its flexibility and dynamicity.
- It may consume more memory than a C-style array, as it stores the size information as well as the elements.
- It may incur some performance overhead due to the additional checks and operations that it performs.

<u>Here is an example of how to use std::array in C++:</u>

```cpp
#include <iostream>
#include <array>

int main()
{
    // declare and initialize an array of 5 integers
    std::array<int, 5> arr = {1, 2, 3, 4, 5};

    // access elements using [] operator
    std::cout << "The first element is " << arr[0] << "\n";
    std::cout << "The last element is " << arr[4] << "\n";

    // access elements using at() member function
    std::cout << "The second element is " << arr.at(1) << "\n";
    std::cout << "The fourth element is " << arr.at(3) << "\n";

    // modify elements using [] operator
    arr[0] = 10;
    arr[4] = 50;

    // modify elements using at() member function
    arr.at(1) = 20;
    arr.at(3) = 40;

    // print the size of the array
    std::cout << "The size of the array is " << arr.size() << "\n";

    // iterate over the array using range-based for loop
    std::cout << "The elements of the array are: ";
    for (int x : arr)
        std::cout << x << " ";
    std::cout << "\n";

    return 0;
}
```

Output:

```
The first element is 1
The last element is 5
The second element is 2
The fourth element is 4
The size of the array is 5
The elements of the array are: 10 20 30 40 50 
```

---
## <font color="yellow"><u>Using std::array as an input for a function and a return from it:</u></f>


```c++
#include <iostream>
#include <array>

using namespace std ;

array<int, 5> array_plusOne( array<int, 5> & arr )
{
    for( int i = 0; i < arr.size(); i++ )
    {
        arr[i] += 1 ;
    }
    
    return arr ;
}

int main() 
{
    
    array<int, 5> arr ;
    array<int, 5> arr2 ;
    
    int i {0} ;
    
    for( int i = 0; i < arr.size(); i++ )
    {
        arr[i] = i ;
    }
    
    for( int x : arr )
    {
        cout << x << ' ' ;
    }
    
    arr2 = array_plusOne( arr ) ;
    
    cout<<endl ;
    
    for( int x : arr2 )
    {
        cout << x << ' ' ;
    }
    
    return 0;
}

```

Output:

```txt
0 1 2 3 4 
1 2 3 4 5 
```

---
## <font color="yellow"><u>std::array methods:</u></f>

|Method|Functionality|Example|
|---|---|---|
|`at()`|Returns a reference to the element at the specified index.|`int x = my_array.at(1); // x == 2`|
|`front()`|Returns a reference to the first element in the array.|`int y = my_array.front(); // y == 1`|
|`back()`|Returns a reference to the last element in the array.|`int z = my_array.back(); // z == 3`|
|`data()`|Returns a pointer to the first element in the array.|`int* p = my_array.data();`|
|`size()`|Returns the size of the array.|`int size = my_array.size(); // size == 3`|
|`empty()`|Returns `true` if the array is empty, `false` otherwise.|`bool is_empty = my_array.empty(); // is_empty == false`|
|`fill()`|Fills the array with the specified value.|`my_array.fill(0); // All elements of my_array will now be 0`|
|`swap()`|Swaps the contents of the given array with the contents of the current array.|`std::array<int, 3> other_array = {4, 5, 6}; my_array.swap(other_array); // my_array will now contain the elements of other_array and vice versa.`|
|`begin()`|Returns an iterator to the beginning of the array.|`std::array<int, 3>::iterator it = my_array.begin();`|
|`end()`|Returns an iterator to the end of the array.|`std::array<int, 3>::iterator end = my_array.end();`|

---
