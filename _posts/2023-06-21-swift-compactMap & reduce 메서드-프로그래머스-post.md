---
title: "[swift] compactMap & reduce 메서드"
date: 2023-06-21 14:51:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

하샤드 수(Lv1)

#### 프로그래머스 문제

양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 x가 나누어져야 합니다. 
- 예를 들어 18의 자릿수 합은 1+8=9이고, 18은 9로 나누어 떨어지므로 18은 하샤드 수입니다. 
자연수 x를 입력받아 x가 하샤드 수인지 아닌지 검사하는 함수, solution을 완성해주세요.


### code

```swift
import Foundation

/*String(x)를 사용하여 정수 x를 문자열로 변환합니다.
 
 compactMap 메서드를 사용하여 문자열을 순회하면서 각 문자를 정수로 변환합니다.
 변환된 숫자는 옵셔널 타입이므로 nil인 경우는 필터링됩니다.

 reduce 메서드를 사용하여 변환된 숫자들의 합을 구합니다.

 x % sumOfDigits == 0을 사용하여 x를 sumOfDigits로 나눈 나머지가 0인지를 확인합니다.
 나머지가 0이면 true를, 그렇지 않으면 false를 반환합니다.
*/

func solution(_ x: Int) -> Bool {
    let sumOfDigits = String(x).compactMap { Int(String($0)) }.reduce(0, +)
    return x % sumOfDigits == 0
}


//나의 풀이
func solution(_ x:Int) -> Bool {
    var sum = 0
    var num = x
    var ans = false
    
    while num > 0 {
        sum += num % 10
        num /= 10
    }
    
    if x % sum == 0 {
        ans = true
    }
    
    return ans
}

```


#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/12947
