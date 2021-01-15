---
layout: post
title: C++에서 pair 사용하기
tags: [C/C++]
---

### pair 선언하기

```cpp
pair<int, int> a;
pair<int, char> b;
pair<int, double> c;
```

pair는 2개의 자료형을 묶어주는 자료형이다. utility 헤더 파일에 포함되어 있는 기능이다. 하지만 vector나 algorithm 헤더 파일에도 포함되어 있으므로 utility 헤더 파일을 추가 해줄 필요는 없다.

### pair 초기화 하기

```cpp
// 방법 1
a = make_pair(10, 20);

// 방법 2
b = {5, 'a'};

// 방법 3
c.first = 7;
c.second = 10.2;
```

pair를 초기화하는 방법에는 3가지가 있다. 첫번째는 make_pair 함수를 사용하는 방법이다. 두번쨰는 중괄호({ })룰 사용하는 방법이다. 세번째는 변수명.first와 변수명.second에 값을 대입해주는 방법이다. 방법 1과 방법 2는 선언과 동시에 사용할 수 있다.

### pair의 값 사용하기

```cpp
cout << a.first << " " << a.second << "\n";
cout << b.first << " " << b.second << "\n";
cout << c.first << " " << c.second << "\n";
```

pair에 저장된 값은 변수명.first 또는 변수명.second로 접근할 수 있다. first는 pair의 첫번째 값에, second는 pair의 두번째 값에 접근한다. 출력되는 결과는 아래와 같다.

```
10 20
5 a
7 10.2
```

변수명.first와 변수명.second를 짧게 만드는 방법도 있다. 아래 코드를 추가하면, pair의 값을 변수명.x와 변수명.y를 통해 접근할 수 있다. 

```cpp
#define x first
#define y second
```

pair는 가중치 방향 그래프의 인접리스트는 만들 때 사용할 수 있다. pair의 first에는 정점(vertex)을 저장하고 second에는 가중치(weight)를 저장하면 된다.
