# Funciones y Call Back


### CallBack en C++

```c++
// pag: 126
template <class F>
void foo(int a, int b, F func) {
    func(a + b, a - b, a * b, a / b);
}

int main() {
    
    foo(20, 10, [](int add, int sub, int mul, int div) {
        cout<<add<<" "<<sub<<" "<<mul<<" "<<div<<endl;
    });
    
    return 0;
}
```
### Insertar elementos en un vector por referencia - Template 

```c++
// pag: 127-128
template<typename Incrementable, typename OutputIterator>
void generate_sequence(Incrementable from, Incrementable to, OutputIterator output) {
    for (Incrementable k = from; k != to; ++k) {
        *output++ = k;
    }
}

int main() {
    
    vector<int> digits;
    generate_sequence(0, 10, std::back_inserter(digits));
    
    for(auto digit: digits) {
        cout<<digit<<endl;
    }
    
    return 0;
}
```

### Puntero a una función (Parte 1)

```c++
// Pag: 147
typedef int FN(int, int);

int add(int x, int y) {
    return x + y;
}

int main() {
    
    FN *fn;
    
    fn = &add;
    cout<<fn(10, 20)<<endl;
    
    FN *sub = [](int x, int y) -> int {
        return x - y;
    };
    
    fn = sub;
    
    cout<<sub(20, 10)<<endl;
    
    return 0;
}
```

### Puntero a una función (Parte 2)

```c++
// Pag: 147
int add(int x, int y) {
    return x + y;
}

int main() {
    
    int (*FN)(int, int) = &add;
    
    cout<<(*FN)(10, 30)<<endl;
    
    int (*Func)(int, int) = [](int x, int y) -> int {
        return x - y;
    };
    
    cout<<(*Func)(30, 10)<<endl;
    
    return 0;
}
```

# Bibliografia

[[1]](https://books.goalkicker.com/CPlusPlusBook/) "Free C++ Programming Book", Books.goalkicker.com, 2019. Available: https://books.goalkicker.com/CPlusPlusBook/.