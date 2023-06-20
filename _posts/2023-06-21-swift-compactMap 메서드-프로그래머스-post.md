---
title: "[swift] compactMap 메서드"
date: 2023-06-21 01:01:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

자연수 뒤집어 배열로 만들기

#### 프로그래머스 문제

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요. 예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.

- 제한 조건
n은 10,000,000,000이하인 자연수입니다.


### code

```swift
import Foundation

func solution(_ n:Int64) -> [Int] {
    return  "\(n)".compactMap { $0.hexDigitValue }.reversed()
}

/*"\(n)"을 사용하여 n을 문자열로 변환합니다. 이를 통해 자연수 n의 각 자릿수를 문자열로 분리할 수 있습니다.

compactMap 메서드를 사용하여 문자열을 순회하면서 각 문자를 hexDigitValue 속성을 통해 16진수 숫자로 변환합니다. hexDigitValue는 문자가 16진수 숫자인 경우 해당 숫자를 반환하고, 그렇지 않은 경우 nil을 반환합니다.

compactMap의 결과로 생성된 배열은 reversed 메서드를 사용하여 역순으로 뒤집습니다.*/

//나의 풀이

func solution(_ n:Int64) -> [Int] {
    var num  = n
    var result: [Int] = []

    if n == 0 {
        result.append(0)
    }

    while num > 0 {
        let digit = num % 10
        result.append(Int(digit))
        num /= 10
    }
    return result
}


```


#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/12932
