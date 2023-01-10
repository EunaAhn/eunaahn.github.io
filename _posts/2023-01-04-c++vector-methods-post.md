---
title: "[C++] 벡터(vector)와 메소드들(push_back, front, back, begin, end)"
date: 2023-01-04 12:09:28 +0900
categories: c++
tags : c++
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

#### push_back

 새로운 원소를 추가할 때는 push_back(값); 메소드를 활용

```c++
    vector <int> a(2); //0으로 초기화된 vcetor 2개 생성

    a[1] = 1;    //1번요소 1로 변경;
    //a[2] = 2;    //2번요소는 없으므로 에러
    a.push_back(2);    //2번요소 값을 생성하고 2로 초기화
```

#### size() 

벡터의 요소의 개수를 반환한다.

```c++
  //a 전체 출력 
    for (int i = 0; i < a.size(); ++i)
    {
        cout << a[i] << " ";
    }
```

#### swap(vector객체)

두 벡터의 내용을 교환(교체)한다.
```c++
a.swap(b);
```

#### front, back, begin, end

- front() - 벡터의 첫 번째 요소를 반환한다.
- back() - 벡터의 마지막 요소를 반환한다.
- begin() - 벡터의 첫 번째 요소를 가리킨다.
- end() - 벡터의 마지막 요소를 가리킨다.

Iterator 을 통한 원소 접근 

- 범위 기반 반복문을 통해 벡터 v 원소를 출력하기
- iterator 를 통해 v.begin() 부터 v.end() 까지 원소 출력하기 

```c++
for (auto iter = v.begin(); iter < v.end() ; iter++ ) {
    cout << *iter << endl;
}
```


#### 크기(사이즈) 함수

- v.size()   : 현재 벡터 v의 원소 갯수(크기)를 리턴합니다. 
- v.capacity() : 할당된 벡터의 원소 갯수(크기)를 리턴합니다. 

- v.resize(n) , v.resize(n,10)
  - v.resize(n) : 벡터를 원래 크기에서 N 크기로 변경합니다.

- v.resize(n,10) : 벡터를 크기 N으로 변경하며 데이터를 10으로 초기화합니다. 

- v.empty() 
벡터 v가 비어있는 지 확인합니다. 현재 비어있는 경우 True 를 반환하고 비어있지 않을 경우 False를 리턴합니다. 
 

#### 참고 링크

https://swblossom.tistory.com/26
https://life-with-coding.tistory.com/411
