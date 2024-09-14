---
title: Advanced C++
category: coding
---

# STLs:

## vector:

to be continued

## set: 

```C++
std::set <data_type> set_name;
```

initialization:

```C++
set<int> val; // defining an empty set
set<int> val = {6, 10, 5, 1}; // defining a set with values
```

add, delete, in:

```C++
val.insert(1);
val.
val.erase(1);
```

## unordered_map:

```C++
unordered_map<string, int> umap;
  
  // inserting values by using [] operator
  umap["GeeksforGeeks"] = 10;
  umap["Practice"] = 20;
  umap["Contribute"] = 30;
  
  // Traversing an unordered map
  for (auto x : umap)
    cout << x.first << " " << 
            x.second << endl;
```

output:

```
Contribute 30
Practice 20
GeeksforGeeks 10
```



# C++ Lambda Expression

e.g.

```c++
sort(words.begin(), words.end(), [](string& w1, string& w2){return w1.size()<w2.size();});
```

note: for sort(), you should include \<algorithm\>

# String：

## substring:

it's like python string index, but two parameters are start position and length.

```C++
string s = "iiyokoiyo";
string s1 = s.substr(1, 4);//1 is start position and 4 is length
cout<<s1<<endl;
```

output: iyok

or you can also:

```C++
string s2 = s.substr(1);
```

it will index from position 1 to the end.



# const

```C++
int main(){
    const int i1 = 114514;
    const int i2 = 1919;
    int i3 = 810;

    const int* ptr = &i1;//can change ptr itself (which means the memory address), but can't change the object it points to
    cout<<ptr<<" "<<*ptr<<endl;//0x2a9e1ffdfc 114514
    ptr = &i2;
    cout<<ptr<<" "<<*ptr<<endl;//0x2a9e1ffdf8 1919

    int* const ptr2 = &i3;//can't change ptr itself (memory address), but can change the object it points to
    cout<<ptr2<<" "<<*ptr2<<endl;//0x2a9e1ffdf4 810
    *ptr2 += 1;
    cout<<ptr2<<" "<<*ptr2<<endl;//0x2a9e1ffdf4 811
}
```

# virtual

in C++, if you want to override a function in derived clas, you should use virtual in parent class!!!!!

```C++
class Mother{
    public:
    Mother(){cout<<"create mother class"<<endl;}
    virtual void myprint(){cout<<"mother class print"<<endl;}
};

class Daughter: public Mother{
    public:
    Daughter(){cout<<"create daughter class"<<endl;}
    void myprint(){cout<<"daughter class print"<<endl;}
};

int main(){
    Mother m;
    m.myprint();
    Daughter d;
    d.myprint();//if delete the myprint() function in daughter, it will print "mother class print"
}
```

if there is no "virtual" in Mother class, it will be an error.



```C++
#include <iostream>
#include <cmath>
#include <cstdio>
#include <string>
#include <vector>
#include <algorithm>
#include <unordered_map>
#include <deque>
#include <limits.h> 

using namespace std;

// There are n cities connected by m flights.
// Each flight starts from city u and arrives at v with a price w.
// Now given all the cities and flights, together with starting
// city src and 
// the destination dst, your task is to find the
// cheapest price from src to dst with up to k stops.
// If there is no such route, output -1.

// Input:
// n = 3, edges = [[0,1,100],[1,2,100],[0,2,500]]
// src = 0, dst = 2, k = 1
// Output: 200
// 10000
int flightPrice(vector<vector<int>> edges, int src, int dst, int k)
{
    int ans = 2147483647; // INT_MAX
    unordered_map<int, vector<vector<int>>> myedges;//src: [[price, ]]
    for (auto e: edges)
    {
        auto found = myedges.find(e[0]);
        if (found != myedges.end()){
            *found.insert(vector<int>{e[1], e[2]});
        }
        else {
            *found = vector<int>(1, vector<int>{e[1], e[2]})
        }
    }
    deque<vector<int>> myque;
    myque.push_back(vector<int>{src, 0, 0});//two zeros for stops and price
    while (myque.size())
    {
        vector<int> searching = myque.front();
        myque.pop_front()
        if (searching[1] >= k) continue;
        for (auto e: myedges[searching[0]])
        {
            myque.push_back(vector<int{e[0], searching[1]+1, e[2]+searching[2]})
        }
    }
    
}


int main() {
    

    return 0;
}
```

