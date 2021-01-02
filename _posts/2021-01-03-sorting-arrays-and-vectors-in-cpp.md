---
layout: post
title: C++에서 배열/벡터 정렬하기
tags: [C/C++]
---

### 배열 정렬하기

```cpp
int arr[] = {3, 1, 5, 4, 2};
int n = sizeof(arr) / sizeof(int);

sort(arr, arr+n);  // 오름차순 정렬

for (int a : arr) {
    cout << a << " ";
}
cout << "\n";

sort(arr, arr+n, greater<int>());  // 내림차순 정렬

for (int a : arr) {
    cout << a << " ";
}
```

sort 함수를 쓰기 위해서 algorithm 헤더 파일을 추가해야 한다.
인자로는 배열의 시작 주소와 배열의 마지막 + 1 주소를 넘겨줘야 한다.
내림차순 정렬을 할 때, greater<자료형>()을 사용하기 위해서는 functional 헤더 파일을 추가해야 한다.
실행 결과는 아래와 같다.

```
1 2 3 4 5
5 4 3 2 1
```

### 벡터 정렬하기

```cpp
vector<int> v = {3, 1, 5, 4, 2};

sort(v.begin(), v.end())  // 오름차순 정렬

for (int a : v) {
    cout << a << " ";
}
cout << "\n";

sort(v.begin(), v.end(), greater<int>());  // 내림차순 정렬

for (int a : v) {
    cout << a << " ";
}
```

begin() 함수는 벡터의 시작 주소를 구한다. end() 함수는 벡터의 마지막 + 1 주소를 구한다.
배열과 마찬가지로 sort와 greater<자료형>()을 사용하므로 필요한 헤더 파일은 같다.
물론 벡터를 사용하기 위해서는 vector 헤더 파일을 추가해야 한다.
실행 결과는 아래와 같다.

```
1 2 3 4 5
5 4 3 2 1
```
