---
layout: post
title: C++ pointers and references
tags: [C/C++]
---

### How to use pointers in C++

```cpp
int a = 10;
int *b = &a;  // pointer variable
cout << b;  // prints address
cout << *b;  // prints value of the address
```

To initialize a pointer varaible(or just pointer), you need an address. Here the '&' sign gets the address of variable a. Now, lets try using them in functions.

```cpp
void swap(int *a, int *b) {
    int tmp = *a;
    *a = *b;
    *b = tmp;
}

int main() {
    int a = 10, b = 20;
    cout << a << " " << b;  // 10 20
    swap(&a, &b);
    cout << a << " " << b;  // 20 10
    return 0;
}
```

Here, we're passing the addresses of variables to funtion swap(), which is the equivalent of int *a = &a and int *b = &b. Pointers work exactly the same in C.


### How to use references in C++

Reference varaibles(or just references) are concepts used in C++ and not in C. They are similar to pointers.

```cpp
int a = 10;
int& b = a; // reference varable
cout << b;  // 10
```

References must be initialized when declared, and they are initialized with the name of other variables. THe '&' sign here is different from the ones used in pointers.

```cpp
void swap(int& a, int& b) {
    int tmp = a;
    a = b;
    b = tmp;
}

int main() {
    int a = 10, b = 20;
    cout << a << " " << b;  // 10 20
    swap(a, b);
    cout << a << " " << b;  // 20 10
    return 0;
}
```

Looking at how they are used in functions, you can guess they are similar to pointers. Although pointers and references differ in expression and some rules, they both 'refer' to something else and basically do the same thing.
