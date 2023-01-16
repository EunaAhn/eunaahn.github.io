---
title: "[C++] 타입의 문자열을 숫자로 바꾸는 함수들과 sort 알고리즘 사용법"
date: 2023-01-16 23:09:28 +0900
categories: c++
tags : c++
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

타입의 문자열을 숫자로 바꾸는 함수들과 sort 알고리즘 사용법

#### C++에서 string 타입의 문자열을 숫자로 바꾸는 함수들의 이름

- stoi = string to int
- stof = string to float
- stol = string to long
- stod = string to double

- 함수원형1 : int stoi(const string& str, size_t* idx =0, int base = 10);
- 함수원형2 : float stof(const string& str, size_t* idx = 0);

- 첫번째 인자 : const string& str: 변경할 문자열이 들어가게 된다.
- 두번째 인자 : size_t* idx = 0: 두번째는 포인터 타입이다. 맨 첫번째 부터 숫자가 아닌 부분까지 해서 그부분의 포인터를 걸러준다. 두번째 인자는 사용하지 않겠다 하면 nullptr을 넣으면 된다.
- 세번째 인자 : int base = 10 (정수형에만 존재) base 는 진수를 뜻하는 것이다. default가 10으로 되어있으면 이것은 10진수가 기본이라는 뜻이다.

#### 정수를 문자열로 바꾸는 법
- to_string 함수 사용

#### Sort 알고리즘

ostringstream은 string을 조립하거나, 특정 수치를 문자열로 변환하기 위해 사용한다. 
ostringstream은 문자열을 붙이는 것 외에도 int나 double형과 같은 수치값을 간단하게 string으로 바꿀 수 있다.

```c++
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
    vector<int> v = {3,2,6,5,8,1,9,7,4};
    sort(v.begin(), v.end(), greater<>()); //내림차순
    sort(v.begin(), v.end()); //오름차순 1,2,3...
    for(auto& i : v)
        cout << i << " ";
        
    return 0;
}

```

#### 참고 링크

- https://blockdmask.tistory.com/333
- https://itguava.tistory.com/67
