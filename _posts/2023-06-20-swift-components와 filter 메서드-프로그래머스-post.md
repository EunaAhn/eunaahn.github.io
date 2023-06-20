---
title: "[swift] components와 filter 메서드"
date: 2023-06-20 20:56:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

문자열 내 p와 y의 개수

#### 프로그래머스 문제

대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

- 제한사항
- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있습니다.


### code

- string.components(separatedBy: "p")는 string 문자열을 "p"를 구분자로 사용하여 분리한 배열을 생성합니다. 이때 "p"를 구분자로 사용하여 문자열을 나누므로 "p"를 포함하지 않은 부분 문자열들이 배열의 요소로 포함됩니다.

- string.components(separatedBy: "y")는 string 문자열을 "y"를 구분자로 사용하여 분리한 배열을 생성합니다.

- count를 사용하여 'p'로 분리된 요소들의 개수와 'y'로 분리된 요소들의 개수를 비교합니다.

- 분리된 요소들의 개수가 서로 같으면 true를, 다르면 false를 반환합니다.


```swift
import Foundation

func solution(_ s: String) -> Bool {
    let string = s.lowercased()
    return string.components(separatedBy: "p").count == string.components(separatedBy: "y").count
}

//나의 풀이
func solution(_ s:String) -> Bool
{
    var ans:Bool = false
    let lowercased = s.lowercased() //소문자로 모두 변경
    let pCount = lowercased.filter{ $0 == "p" }.count
    let yCount = lowercased.filter{ $0 == "y" }.count

    if pCount == yCount {
        ans = true          //'p'의 개수 == 'y'의 개수 : True
    } else if pCount != yCount {
        ans = false         //'p'의 개수 != 'y'의 개수 : False
    } else if pCount == 0 && yCount == 0 {
        ans = true          //'p'의 개수 == 0 && 'y'의 개수 == 0 : True
    }

    return ans
}

```


#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/12916
