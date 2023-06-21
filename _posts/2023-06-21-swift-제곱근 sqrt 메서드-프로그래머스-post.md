---
title: "[swift] sqrt 제곱근 메서드"
date: 2023-06-21 13:58:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

정수 제곱근 판별(Lv1)

#### 프로그래머스 문제

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.


### code

```swift

//import Foundation은 Foundation 프레임워크를 임포트하는 구문입니다. 
해당 코드에서는 제곱근을 계산하기 위해 Foundation 프레임워크의 sqrt 함수를 사용하고 있습니다.

//solution 함수는 양의 정수 n을 입력받고, 정수를 반환합니다.

//sqrt 함수를 사용하여 n의 제곱근을 계산하고, 정수로 변환하여 sqrtN에 할당합니다.

import Foundation

func solution(_ n:Int64) -> Int64 {
    
    var x = Int(sqrt(Double(n)))
    var ans = 0
    
    // 정수 x의 제곱이라면: (x+1)*(x+1)
    if n == x * x {
        ans = Int((x+1)*(x+1))
    }
    
    // 정수 x의 제곱이 아니라면: -1
    else {
        ans = -1
    }

    return Int64(ans)
}


```


#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/12934
