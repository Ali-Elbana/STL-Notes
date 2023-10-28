## <font color="yellow"><u>What is std::pair?</u></f>

`std::pair` is a template class in the C++ Standard Library that allows you to store a pair of values as a single entity. It provides a convenient way to group two values together and use them as a single unit.

The `std::pair` template is defined in the `<utility>` header and has the following syntax:

```cpp
template <class T1, class T2>
struct pair
{
    T1 first;
    T2 second;
};
```

The `std::pair` template takes two template parameters: `T1` and `T2`, which represent the types of the first and second values in the pair, respectively. The `first` and `second` member variables are public and can be accessed directly.

Here's an example of using `std::pair`:

```cpp
#include <iostream>
#include <utility>

int main()
{
    std::pair<int, double> myPair(10, 3.14);
    
    std::cout << "First value: " << myPair.first << std::endl;
    std::cout << "Second value: " << myPair.second << std::endl;
    
    return 0;
}
```

Output:
```
First value: 10
Second value: 3.14
```

In this example, we create a `std::pair` named `myPair` with an integer (`int`) as the first value and a double (`double`) as the second value. We initialize the pair with the values 10 and 3.14, respectively.

We can access the values of the pair using the `first` and `second` member variables. In this case, we print the values to the console.

`std::pair` is commonly used in various scenarios where you need to group two values together, such as returning multiple values from a function, storing key-value pairs in associative containers like `std::map`, or implementing custom data structures.

---
## <font color="yellow"><u>std::pair methods:</u></f>

|Method|Functionality|Example|
|---|---|---|
|`make_pair`|Creates a `std::pair` from two values|`std::pair<int, std::string> myPair = std::make_pair(10, "A");`|
|`first`|Accesses the first value in the pair|`int value1 = myPair.first;`|
|`second`|Accesses the second value in the pair|`std::string value2 = myPair.second;`|
|`operator==`|Checks if two pairs are equal|`bool isEqual = myPair1 == myPair2;`|
|`operator!=`|Checks if two pairs are not equal|`bool isNotEqual = myPair1 != myPair2;`|
|`operator<`|Compares two pairs lexicographically|`bool isLess = myPair1 < myPair2;`|
|`operator>`|Compares two pairs lexicographically|`bool isGreater = myPair1 > myPair2;`|
|`operator<<` (stream)|Outputs the pair to a stream|`std::cout << myPair;`|
|`swap`|Swaps the contents of two pairs|`std::swap(myPair1, myPair2);`|
|`make_tuple`|Creates a `std::tuple` from a pair|`std::tuple<int, std::string> myTuple = std::make_tuple(myPair);`|
|`tie`|Creates a tuple of references to the pair's elements|`int& ref1; std::string& ref2; std::tie(ref1, ref2) = myPair;`|
|`get`|Accesses the elements of the pair through compile-time indexing|`int value1 = std::get<0>(myPair);`|
|`piecewise_construct`|Constructs a pair from two tuples|`std::pair<int, std::string> myPair = std::make_pair(std::piecewise_construct, std::forward_as_tuple(10), std::forward_as_tuple("A"));`|

---

