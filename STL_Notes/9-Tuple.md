## <font color="yellow"><u>What is std::tuple?</u></f>

`std::tuple` is a template class in the C++ Standard Library that allows you to store a fixed-size collection of elements of different types as a single entity. It provides a convenient way to group multiple values together and use them as a single unit.

The `std::tuple` template is defined in the `<tuple>` header and has the following syntax:

```cpp
template <class... Types>
class tuple;
```

The `std::tuple` template takes a variable number of template parameters (`Types`) representing the types of the elements in the tuple. The number and types of the elements in a tuple are fixed at compile-time.

Here's an example of using `std::tuple`:

```cpp
#include <iostream>
#include <tuple>

int main()
{
    std::tuple<int, double, std::string> myTuple(10, 3.14, "Hello");
    
    std::cout << "First value: " << std::get<0>(myTuple) << std::endl;
    std::cout << "Second value: " << std::get<1>(myTuple) << std::endl;
    std::cout << "Third value: " << std::get<2>(myTuple) << std::endl;
    
    return 0;
}
```

Output:
```
First value: 10
Second value: 3.14
Third value: Hello
```

In this example, we create a `std::tuple` named `myTuple` with an integer (`int`), a double (`double`), and a string (`std::string`) as the elements. We initialize the tuple with the values 10, 3.14, and "Hello", respectively.

We can access the values of the tuple using the `std::get` function and providing the index of the element as the template argument. In this case, we print the values to the console.

`std::tuple` provides various other functionalities, such as tuple comparison, tuple assignment, tuple concatenation, and accessing tuple elements as references. It is commonly used in scenarios where you need to group multiple values together, such as returning multiple values from a function, storing heterogeneous data in a container, or implementing advanced data structures.

Note that starting from C++17, structured bindings can also be used with tuples to conveniently access the individual elements without using `std::get`.

---
## <font color="yellow"><u>std::tuple methods:</u></f>

|Method|Functionality|Example|
|---|---|---|
|`make_tuple`|Creates a `std::tuple` from given values|`std::tuple<int, double, std::string> myTuple = std::make_tuple(10, 3.14, "Hello");`|
|`tie`|Creates a tuple of references to the tuple's elements|`int value1; double value2; std::string value3; std::tie(value1, value2, value3) = myTuple;`|
|`get`|Accesses the elements of the tuple through compile-time indexing|`int value1 = std::get<0>(myTuple);`|
|`tuple_size`|Provides the number of elements in the tuple|`std::size_t size = std::tuple_size<decltype(myTuple)>::value;`|
|`tuple_element`|Provides the type of the element at a specific index|`using ElementType = std::tuple_element<1, decltype(myTuple)>::type;`|
|`tuple_cat`|Concatenates multiple tuples into a single tuple|`std::tuple<int, double> tuple1(10, 3.14); std::tuple<std::string> tuple2("Hello"); std::tuple<int, double, std::string> concatenatedTuple = std::tuple_cat(tuple1, tuple2);`|
|`operator==`|Checks if two tuples are equal|`bool isEqual = myTuple1 == myTuple2;`|
|`operator!=`|Checks if two tuples are not equal|`bool isNotEqual = myTuple1 != myTuple2;`|
|`operator<`|Compares two tuples lexicographically|`bool isLess = myTuple1 < myTuple2;`|
|`operator>`|Compares two tuples lexicographically|`bool isGreater = myTuple1 > myTuple2;`|
|`operator<<` (stream)|Outputs the tuple to a stream|`std::cout << myTuple;`|

---

