---
layout: post
title: C++에서 배열 또는 벡터를 함수에 넘기기
tags: [C/C++]
---

### 배열 넘기기

```cpp
void fillZero(int *arr, int size) {
    for (int i=0; i<size; i++) {
        arr[i] = 0;
    }
}

int main() {
    int arr[] = {1, 2, 3, 4 ,5};
    for (int a : arr) {
        cout << a << " ";
    }
    cout << "\n";
    int size = sizeof(arr) / sizeof(int);
    fillZero(arr, size);
    for (int a : arr) {
        cout << a << " ";
    }
    return 0;
}
```

fillZero 함수의 parameter에 int *arr 대신 int arr[]를 써도 같은 결과가 나온다. 배열이 포인터로 자동 변환되어서 함수 안에서 배열의 크기를 구할 수 없다. 그래서 배열의 크기도 인자로 같이 넘긴다. 실행 결과는 아래와 같다.

```
1 2 3 4 5 
0 0 0 0 0
```

### vector 넘기기

```cpp
void fillZero(vector<int> &v) {
    for (int i=0; i<v.size(); i++) {
        v[i] = 0;
    }
}

int main() {
    vector<int> v = {1, 2, 3, 4 ,5};
    for (int a : v) {
        cout << a << " ";
    }
    cout << "\n";
    fillZero(v);
    for (int a : v) {
        cout << a << " ";
    }
    return 0;
}
```

Vector의 경우 parameter를 reference 변수로 만들면 된다. 실행 결과는 아래와 같다.

```
1 2 3 4 5 
0 0 0 0 0
```
만약 reference 변수로 vector를 받지 않을 경우 원래 vector를 바꾸는 것이 아닌 복사본을 바꾸게 된다. 복사본을 0으로 채우고 원래 벡터는 바뀌지 않는다.
