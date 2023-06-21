---
title: "[swift] sorted(by:) 메서드"
date: 2023-06-21 14:28:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

정수 내림차순으로 배치하기(Lv.1)

#### 프로그래머스 문제

함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운 정수를 리턴해주세요.
예를들어 n이 118372면 873211을 리턴하면 됩니다.


### code

```swift

/*solution 함수는 n이라는 정수를 입력받고, 정수를 반환합니다.

String(n)을 사용하여 정수 n을 문자열로 변환합니다.

sorted(by:) 메서드를 사용하여 문자열의 각 자릿수를 큰 것부터 작은 순으로 정렬합니다.

String(sortedDigits)를 사용하여 정렬된 자릿수들로 이루어진 문자열을 생성합니다.

Int(String(sortedDigits)) ?? 0를 사용하여 문자열을 다시 정수로 변환합니다.
이때, 변환할 수 없는 경우에는 기본값으로 0을 사용합니다.

정렬된 숫자를 반환합니다.*/

import Foundation

func solution(_ n:Int64) -> Int64 {
    
    let sortedDigits = String(n).sorted(by: >)
    let sortedNumber = Int64(String(sortedDigits)) ?? 0
    
    return sortedNumber
}


```


#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/12933
