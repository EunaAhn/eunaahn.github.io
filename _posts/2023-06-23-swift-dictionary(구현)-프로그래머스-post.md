---
title: "[swift] dictionary(구현)"
date: 2023-06-23 14:45:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

연습) 가위 바위 보

#### 프로그래머스 문제

가위는 2 바위는 0 보는 5로 표현합니다. 가위 바위 보를 내는 순서대로 나타낸 문자열 rsp가 매개변수로 주어질 때, rsp에 저장된 가위 바위 보를 모두 이기는 경우를 순서대로 나타낸 문자열을 return하도록 solution 함수를 완성해보세요.

- 제한사항
- rsp와 길이가 같은 문자열을 return 합니다.
- rsp는 숫자 0, 2, 5로 이루어져 있습니다.

### code

```swift

 
 winCases라는 딕셔너리를 정의합니다. 이 딕셔너리는 가위, 바위, 보를
 이길 수 있는 경우를 정의합니다.
 
 result라는 빈 문자열을 선언하여 이기는 경우를 순서대로 저장할 변수를 생성합니다.
 반복문을 사용하여 문자열 rsp를 순회합니다.
 */

import Foundation

func solution(_ rsp:String) -> String {
    let winCases: [Character: Character] = ["2": "0", "0": "5", "5":"2"]
    var result: String = ""
    
    for i in rsp{
        if let winmove = winCases[i]{
            result.append(winmove)
        }
    }
    
    return result
}

```


#### 참고 링크

- https://school.programmers.co.kr/tryouts/85898/challenges
