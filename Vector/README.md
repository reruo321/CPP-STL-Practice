# Vector
**Vector** (std::vector) is a sequence container that encapsulates dynamic size arrays.

## Header
    #include <iostream>
    #include <vector>

## Functions
### push_back()
Adds an element to the end.

    #include <iostream>
    #include <vector>
    
    using namespace std;
    
    int main(){
        vector<int> vec = {1, 2, 3, 4};
        vec.push_back(7);
        vec.push_back(11);
    
        cout << "vec = {";
        for(int n : vec){ cout << n << ", "; }
        cout << "}" << endl;
    }
    
Output:

    vec = {1, 2, 3, 4, 7, 11, }
    
### emplace_back()
Adds an element to the end. While push_back() takes an object to insert, emplace_back() just takes parameters for the object's constructor, and creates the object directly into the vector. It has higher performance than push_back() since it passes temporary object.

    public SomeObject(const String &str, const int num){...}   // SomeObject's Constructor
    ...
    vector<SomeObject> objVec;
    objVec.emplace_back("Hello", 123);

### front()
All sequence containers vector, list, and deque has front() and back() to show the first and the last elements.

    vec.front();

### back()

    vec.back();

### resize()
It resizes the vector. If it becomes bigger than before, it fills the empty spaces with argument.

    vector<int> vec(3, 1);   // 1 1 1
    vec.resize(5, 2);   // 1 1 1 2 2

### swap()
This is the function that all containers in C++ provide. It swaps the elements of two containers.

    v1.swap(v2);

### clear()
Clears all contents of the vector, and makes it size to 0.

    vec.clear();

### shrink_to_fit()
Capacity (Allocated memory) of the vector is alive even if you make its size 0 by calling resize() or clear(). Programmers had used swap() to remove it.

    vector<int>().swap(vec);   // This swaps the vector to empty one.

Since C++11, the compiler provides them shrink_to_fit().

    vec.shrink_to_fit();
    
However, it is a costly non-binding function to waste too much CPU time when it copies a lot of elements. You would only use it when really necessary.
