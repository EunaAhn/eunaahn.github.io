---
title: "[swift] reduce 메서드"
date: 2023-06-20 19:30:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

평균 구하기

#### 프로그래머스 문제

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.

제한사항
arr은 길이 1 이상, 100 이하인 배열입니다.
arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.



### code

```swift
import Foundation

func solution(_ arr:[Int]) -> Double {
    let sum = arr.reduce(0, +)
    let count = arr.count
    let answer = Double(sum) / Double(count)
    return answer
}

```
let sum = arr.reduce(0, +)은 배열 arr의 모든 요소를 더하여 합을 계산하는 부분

reduce는 배열의 모든 요소를 결합하여 단일 값으로 줄이는 메서드입니다.

reduce 메서드는 두 개의 매개변수를 가지며, 첫 번째 매개변수는 초기값이고 두 번째 매개변수는 클로저입니다.

reduce(0, +)에서 첫 번째 매개변수인 0은 초기값으로 설정됩니다. 초기값은 더하기 연산을 시작하기 전에 사용되는 값입니다.

두 번째 매개변수인 +는 더하기 연산자입니다. 이것은 클로저로서 각 요소를 더하는 연산을 수행합니다.

reduce(0, +)는 배열 arr의 요소들을 처음부터 끝까지 반복하면서 초기값인 0과 각 요소를 더합니다.

예를 들어, arr이 [1, 2, 3, 4, 5]라면 reduce(0, +)는 다음과 같은 과정을 거칩니다:
- 초기값인 0에 첫 번째 요소인 1을 더합니다. 결과는 1입니다.
- 그 다음으로, 1에 두 번째 요소인 2를 더합니다. 결과는 3입니다.
- 이 과정을 계속 반복하여 모든 요소를 더합니다.

최종적으로, reduce(0, +)는 배열 arr의 모든 요소를 더한 총합을 반환합니다. 이 값은 sum 변수에 할당됩니다.

즉, let sum = arr.reduce(0, +)는 배열 arr의 모든 요소를 더하여 그 합을 sum 변수에 저장하는 코드입니다.

