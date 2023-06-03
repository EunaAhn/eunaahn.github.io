---
title: "[swift] 유한소수 판별하기"
date: 2023-01-16 23:09:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

유한소수 판별하기

#### 프로그래머스 문제

소수점 아래 숫자가 계속되지 않고 유한개인 소수를 유한소수라고 합니다. 분수를 소수로 고칠 때 유한소수로 나타낼 수 있는 분수인지 판별하려고 합니다. 유한소수가 되기 위한 분수의 조건은 다음과 같습니다.

기약분수로 나타내었을 때, 분모의 소인수가 2와 5만 존재해야 합니다.
두 정수 a와 b가 매개변수로 주어질 때, a/b가 유한소수이면 1을, 무한소수라면 2를 return하도록 solution 함수를 완성해주세요.

#### 정수를 문자열로 바꾸는 법
- to_string 함수 사용

```swift
import Foundation

public func solution(_ a: Int, _ b: Int) -> Int {
    // a와 b의 최대공약수를 구합니다.
    let gcdValue = gcd(a, b)
    // a와 b를 최대공약수로 나누어 기약분수로 만듭니다.
    let a_g = a / gcdValue
    let b_g = b / gcdValue
    
    // 분모의 소인수가 2와 5로만 이루어진 경우 1을 반환합니다.
    if hasOnlyTwoAndFive(asDenominator: b_g) {
        return 1
    } else {
        return 2
    }
}

// 최대공약수를 계산하는 함수입니다.
func gcd(_ a: Int, _ b: Int) -> Int {
    var x = a
    var y = b

    while y != 0 {
        let temp = y
        y = x % y
        x = temp
    }

    return x
}

// 분모의 소인수를 확인하기 위해 hasOnlyTwoAndFive(asDenominator:) 함수
func hasOnlyTwoAndFive(asDenominator n: Int) -> Bool {
    var number = n
    
    while number % 2 == 0 {
        number /= 2
    }
    
    while number % 5 == 0 {
        number /= 5
    }
    
    return number == 1
}

```

#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/120878
