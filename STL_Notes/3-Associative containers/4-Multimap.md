## <font color="yellow"><u>What is std::multimap?</u></font>

  
std::multimap is an associative container in the C++ Standard Template Library (STL) that stores key-value pairs, where the keys are sorted but duplicate keys are allowed. The values in a std::multimap can be of any type, but the keys must be of a type that supports a comparison operator.

std::multimap is implemented as a red-black tree, which means that search, insertion, and removal operations have logarithmic time complexity. std::multimap also supports reverse iterators, which can be used to traverse the elements in reverse order.

std::multimap is a versatile container that can be used in a variety of applications. For example, it can be used to store a dictionary of synonyms, a list of email addresses for a given contact, or a list of courses that a student is enrolled in.

<u>Here is an example of how to use std::multimap:</u>

```C++
#include <iostream>
#include <map>

int main() 
{

  std::multimap<std::string, int> my_multimap = 
  {
    {"key1", 10},
    {"key2", 20},
    {"key1", 30}
  };

  // Print the key-value pairs in the multimap.
  for (const auto& [key, value] : my_multimap) {
    std::cout << key << ": " << value << std::endl;
  }

  return 0;
}
```

Output:

```
key1: 10
key2: 20
key1: 30
```

---
## <font color="yellow"><u>std::multimap methods:</u></f>

|Method|Functionality|Example|
|---|---|---|
|`multimap::multimap()`|Constructs a multimap object, optionally with a comparison function, an allocator, or a range of elements|`std::multimap<std::string, int> m1; // default constructor`<br>`std::multimap<std::string, int> m2(m1); // copy constructor`<br>`std::multimap<std::string, int> m3(std::greater<>()); // constructor with comparison function`<br>`std::multimap<std::string, int> m4({{"one", 1}, {"two", 2}, {"two", 3}}); // constructor with initializer list`|
|`multimap::~multimap()`|Destroys the multimap object and frees the allocated memory|`m1.~multimap(); // destructor`|
|`multimap::operator=`|Assigns a new value to the multimap object, replacing its current content|`m1 = m2; // copy assignment`<br>`m1 = {{"three", 3}, {"four", 4}}; // move assignment`|
|`multimap::get_allocator()`|Returns a copy of the allocator object associated with the multimap|`auto alloc = m1.get_allocator(); // alloc is of type std::allocator<std::pair<const std::string, int>>`|
|`multimap::at()`|Returns a reference to the mapped value of the element with a given key. Throws an exception if the key is not found. (C++17)|`std::cout << m1.at("one"); // prints 1`<br>`m1.at("two") = 4; // modifies the value of one of the occurrences of "two" to 4`|
|`multimap::operator[]`|Returns a reference to the mapped value of the element with a given key, inserting it if it does not exist. (C++17)|`std::cout << m1["one"]; // prints 1`<br>`m1["three"] = 5; // inserts {"three", 5} into the multimap`|
|`multimap::begin()`|Returns an iterator to the first element in the multimap|`auto it = m1.begin(); // it points to the first element in the multimap`|
|`multimap::end()`|Returns an iterator to the past-the-end element in the multimap|`auto it = m1.end(); // it points to the position after the last element in the multimap`|
|`multimap::rbegin()`|Returns a reverse iterator to the last element in the multimap|`auto rit = m1.rbegin(); // rit points to the last element in the multimap`|
|`multimap::rend()`|Returns a reverse iterator to the element before the first element in the multimap|`auto rit = m1.rend(); // rit points to the position before the first element in the multimap`|
|`multimap::cbegin()`|Returns a const iterator to the first element in the multimap (C++11)|`auto cit = m1.cbegin(); // cit points to the first element in the multimap and cannot modify it`|
|`multimap::cend()`|Returns a const iterator to the past-the-end element in the multimap (C++11)|`auto cit = m1.cend(); // cit points to the position after the last element in the multimap and cannot modify it`|
|`multimap::crbegin()`|Returns a const reverse iterator to the last element in the multimap (C++11)|`auto crit = m1.crbegin(); // crit points to the last element in the multimap and cannot modify it`|
|`multimap::crend()`|Returns a const reverse iterator to the element before the first element in the multimap (C++11)|`auto crit = m1.crend(); // crit points to the position before the first element in the multimap and cannot modify it`|
|`multimap::empty()`|Checks whether the multimap is empty or not|`std::cout << std::boolalpha << m1.empty(); // prints false if m1 has elements, true otherwise`|
|`multimap::size()`|Returns the number of elements in the multimap|`std::cout << m1.size(); // prints how many elements are in m1`|
|`multimap::max_size()`|Returns the maximum number of elements that can be held by the multimap according to its allocator type and system limitations|`std::cout << m1.max_size(); // prints a very large number that represents an upper bound on how many elements can be stored in m1`|
|`multimap::clear()`|Removes all elements from the multimap, leaving it with size zero|`m1.clear(); // clears all elements from m1`|
|`multimap::insert()`|Inserts an element or a range of elements into the multimap, preserving its sorted order and allowing multiple entries with the same key|`m1.insert(std::make_pair("five", 5)); // inserts {"five", 5} into the multimap`<br>`m1.insert(m2.begin(), m2.end()); // inserts all elements from m2 into m1`|
|`multimap::emplace()`|Constructs and inserts an element into the multimap, preserving its sorted order and allowing multiple entries with the same key (C++11)|`m1.emplace("six", 6); // constructs and inserts {"six", 6} into the multimap`|
|`multimap::emplace_hint()`|Constructs and inserts an element into the multimap with a hint on the insertion position, preserving its sorted order and allowing multiple entries with the same key (C++11)|`auto it = m1.find("five"); // it points to one of the occurrences of {"five", 5}`<br>`m1.emplace_hint(it, "seven", 7); // constructs and inserts {"seven", 7} into the multimap using it as a hint`|
|`multimap::erase()`|Erases an element or a range of elements from the multimap by key or by iterator|`m1.erase("one"); // erases all the elements with key "one" from the multimap`<br>`m1.erase(m1.begin(), m1.end()); // erases all elements from the multimap`|
|`multimap::swap()`|Exchanges the contents of two multimaps of the same type|`m1.swap(m2); // swaps the contents of m1 and m2`|
|`multimap::extract()`|Removes an element from the multimap and returns it as a node handle, which can be used to transfer ownership of the element (C++17)|`auto nh = m1.extract("one"); // nh is a node handle that contains {"one", 1}`<br>`m2.insert(std::move(nh)); // transfers ownership of {"one", 1} to m2`|
|`multimap::merge()`|Transfers elements from another map or multimap into the multimap, preserving its sorted order and allowing multiple entries with the same key (C++17)|`m1.merge(m2); // transfers all elements from m2 to m1`|
|`multimap::find()`|Searches for an element in the multimap by key and returns an iterator to it if found, or to end() if not found|`auto it = m1.find("two"); // it points to one of the occurrences of "two" if found, or to end() if not found`|
|`multimap::count()`|Returns the number of elements in the multimap with a given key|`std::cout << m1.count("two"); // prints how many elements have key "two" in m1`|
|`multimap::lower_bound()`|Returns an iterator to the first element in the multimap that is not less than a given key|`auto it = m1.lower_bound("three"); // it points to one of the occurrences of "three" or to end() if no such element exists`|
|`multimap::upper_bound()`|Returns an iterator to the first element in the multimap that is greater than a given key|`auto it = m1.upper_bound("three"); // it points to one of the occurrences of "four" or to end() if no such element exists`|
|`multimap::equal_range()`|Returns a pair of iterators to the range of elements in the multimap that are equivalent to a given key|`auto p = m1.equal_range("three"); // p is a pair of iterators that point to one of the occurrences of "three" and one of the occurrences of "four", or both point to end() if no such element exists`|
|`multimap::key_comp()`|Returns the comparison function used to order the keys in the multimap|`auto comp = m1.key_comp(); // comp is a function object that compares two keys using std::less by default`|
|`multimap::value_comp()`|Returns the comparison function used to order the key-value pairs in the multimap|`auto comp = m1.value_comp(); // comp is a function object that compares two key-value pairs by comparing their keys using std::less by default`|

---

