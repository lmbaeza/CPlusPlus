# Pair & Tuple

### Retornar multiples variables <Tuple>

```c++
// pag: 122
auto foo(int x, int y) {
    return make_tuple(x+y, x-y, x*y, x/y, x, y);
}

int main() {
    auto [add, sub, mul, div, x, y] = foo(20, 10);

    cout<<add<<" "<<sub<<" "<<mul<<" "<<" "<<div<<endl;

    cout<<x<<" "<<y<<" "<<endl;
    return 0;
}
```

### Retornando una estructura

```c++
// pag: 125

struct foo_return_type {
    int add;
    int sub;
    int mul;
    int div;
};

foo_return_type foo(int a, int b) {
    return {a + b, a - b, a * b, a / b};
}

int main() {
    auto [add, sub, mul, div] = foo(20, 10);
    
    cout<<add<<" "<<sub<<" "<<mul<<" "<<div<<endl;
    
    return 0;
}
```

# Bibliografia

[[1]](https://books.goalkicker.com/CPlusPlusBook/) "Free C++ Programming Book", Books.goalkicker.com, 2019. Available: https://books.goalkicker.com/CPlusPlusBook/.