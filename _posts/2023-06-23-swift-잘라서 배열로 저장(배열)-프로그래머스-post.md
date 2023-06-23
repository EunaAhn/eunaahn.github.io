---
title: "[swift] 잘라서 배열로 저장(배열)"
date: 2023-06-23 15:26:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

문제 1) 잘라서 배열로 저장하기

#### 프로그래머스 문제

문자열 my_str과 n이 매개변수로 주어질 때, my_str을 길이 n씩 잘라서 저장한 배열을 return하도록 solution 함수를 완성해주세요.

### code

```swift

 
/*stride(from:to:by:) 함수를 사용하여 0부터 문자열 my_str의 길이까지 n만큼씩 증가하면서 반복합니다. 이를 통해 문자열을 일정 길이로 잘라낼 수 있습니다.
 
 startIndex를 정의하여 현재 잘릴 부분의 시작 인덱스를 가져옵니다.

 endIndex를 정의하여 현재 잘릴 부분의 끝 인덱스를 가져옵니다.
 offsetBy에 n을 더한 값을 제한 범위로 지정하여 문자열의 범위를 초과하지 않도록 합니다.
 만약 이동한 인덱스가 my_str의 유효한 범위를 벗어난다면 nil을 반환합니다.
 이 경우 ?? 연산자를 사용하여 nil 대신 my_str.endIndex를 반환하도록 지정하였습니다.

 substring을 정의하여 잘린 부분을 문자열로 변환합니다.*/

import Foundation

func solution(_ my_str:String, _ n:Int) -> [String] {
    var result: [String] = []
    
    for i in stride(from: 0, to: my_str.count, by: n) {
        let startIndex = my_str.index(my_str.startIndex, offsetBy: i)
        let endIndex = my_str.index(startIndex, offsetBy: n, limitedBy: my_str.endIndex) ?? my_str.endIndex
        let substring = String(my_str[startIndex..<endIndex])
        result.append(substring)
    }
    
    return result
}


```


#### 참고 링크

- https://school.programmers.co.kr/tryouts/85905/challenges?language=swift
