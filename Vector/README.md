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
        vector<int> v = {1, 2, 3, 4};
        v.push_back(7);
        v.push_back(11);
    
        cout << "v = {";
        for(int n : v){ cout << n << ", "; }
        cout << "}" << endl;
    }
    
Output:

    v = {1, 2, 3, 4, 7, 11, }
    
