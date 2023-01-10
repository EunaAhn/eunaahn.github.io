---
title: "[C++] 배열 중복 요소 제거"
date: 2023-01-05 12:09:28 +0900
categories: c++
tags : c++
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

#### set를 이용하여 vector의 중복 요소 제거

set를 이용하여 vector의 중복 요소를 제거할 수 있다. 
vector의 모든 요소를 set에 저장하고, 다시 set를 vector로 변경하면 중복 요소를 제거할 수 있습니다.

문자열 my_string이 매개변수로 주어집니다. my_string에서 중복된 문자를 제거하고 하나의 문자만 남긴 문자열을 return하도록 solution 함수를 완성해주세요.

```c++
#include <string>
#include <vector>
#include <unordered_set>
using namespace std;

string solution(string my_string) {
    string answer = "";
    
    unordered_set<char> us;
    
    for(const auto v : my_string)
    {
        if(us.count(v) == 0) // us 라는 set 안에 v가 존재하지 않으면 중복된 것이 아니므로 answer에 추가한다.
        {
            answer.push_back(v);
            us.insert(v);
        }
    }
    return answer;
}

```

unordered_set의 생성자에 vector.begin(), vector.end()를 전달하면 vector의 모든 요소가 set에 추가됩니다. 반대로 vector의 생성자에 begin과 end를 전달하면 set의 모든 요소가 vector에 추가됩니다.

```c++
#include <iostream>
#include <unordered_set>
#include <vector>

int main() {
    std::vector<int> int_vec = {1, 2, 5, 3, 2, 5, 9, 7};

    // remove duplicates
    std::unordered_set<int> int_set(int_vec.begin(), int_vec.end());

    // set to vector
    std::vector<char> new_vec(int_set.begin(), int_set.end());

    for (const int &i: new_vec) {
        std::cout << i << ' '; //7 9 3 5 2 1
    }

    return 0;
}

```

 

#### 참고 링크

- https://codechacha.com/ko/cpp-remove-duplicates-in-array/
