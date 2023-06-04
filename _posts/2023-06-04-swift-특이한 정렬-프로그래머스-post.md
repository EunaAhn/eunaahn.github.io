---
title: "[swift] 특이한 정렬"
date: 2023-06-04 19:30:28 +0900
categories: swift
tags : swift
header:
  teaser: /assets/blog2.png
  image: # /assets/mozilla_logo.png 
toc: true  
toc_sticky: true 

---

특이한 정렬

#### 프로그래머스 문제

정수 n을 기준으로 n과 가까운 수부터 정렬하려고 합니다. 이때 n으로부터의 거리가 같다면 더 큰 수를 앞에 오도록 배치합니다. 정수가 담긴 배열 numlist와 정수 n이 주어질 때 numlist의 원소를 n으로부터 가까운 순서대로 정렬한 배열을 return하도록 solution 함수를 완성해주세요.


### code

주어진 numlist는 [1, 2, 3, 4, 5, 6]이며, n은 4입니다.

numlist의 각 원소를 n으로부터의 거리와 원소 값에 따라 비교하여 정렬해야 합니다.

n으로부터의 거리를 계산합니다. 각 원소와 n의 차이의 절댓값을 구합니다.

- 원소 1의 거리: abs(1 - 4) = 3
- 원소 2의 거리: abs(2 - 4) = 2
- 원소 3의 거리: abs(3 - 4) = 1
- 원소 4의 거리: abs(4 - 4) = 0
- 원소 5의 거리: abs(5 - 4) = 1
- 원소 6의 거리: abs(6 - 4) = 2

- 거리와 원소 값을 기준으로 정렬합니다. 거리가 작은 수부터 정렬하며, 거리가 같을 경우 더 큰 수가 앞에 오도록 정렬합니다.

정렬 결과: [4, 3, 5, 2, 6, 1]


```swift
import Foundation

func solution(_ numlist:[Int], _ n:Int) -> [Int] {
    let list = numlist.sorted {
        if abs($0 - n) == abs($1 - n){
            return $0 > $1
        }
        return abs($0 - n) < abs($1 - n)
    }
    return list
}
```
return abs($0 - n) < abs($1 - n)는 클로저 내부의 비교식입니다. 이 비교식은 sorted 함수에 전달되어 배열의 원소를 정렬하는 데 사용됩니다.

- 해당 비교식은 두 개의 원소 $0와 $1을 비교하여 정렬 순서를 결정합니다. 이 비교식은 다음과 같은 의미를 가집니다:

- abs($0 - n) < abs($1 - n): $0과 $1의 n으로부터의 거리를 비교합니다.

- 만약 abs($0 - n)의 값이 abs($1 - n)의 값보다 작다면, 즉 $0이 n에 더 가깝다면, true를 반환합니다.

- 이 경우 true가 반환되면, sorted 함수는 $0를 $1보다 앞에 위치시킵니다.

- 그렇지 않은 경우, 즉 abs($0 - n)의 값이 abs($1 - n)의 값보다 크거나 같다면, false를 반환합니다.

- 이 경우 false가 반환되면, sorted 함수는 $0와 $1의 순서를 유지합니다.

- 따라서, return abs($0 - n) < abs($1 - n)는 n으로부터의 거리가 작은 순서로 정렬하는 비교식을 나타냅니다.

#### 참고 링크

- https://school.programmers.co.kr/learn/courses/30/lessons/120880
