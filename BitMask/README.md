# Bit Mask

### Swap con bitmask

```c++
void swap(int &a, int &b) {
    if(a != b) {
        a ^= b;
        b ^= a;
        a ^= b;
    }
}
int main() {
    int a = 75;
    int b = 83;
    swap(a, b);	
    cout<<"a="<<a<<" "<<"b="<<b<<endl;
    //a=83 b=75
    return 0;
}
```

### Verificar si es potencia de 2

```c++
int n = 8;
bool power_of_2 = n && !(n & (n - 1))
```

### Cambiar el n-th bit a x

```c++
int number = 10;
// si x=0 cambia el n-th bit a 0
// si x=1 cambia el n-th bit a 1
// 1 1 0 0 0 1 0 1 0
// ^ ^ ^ ^ ^ ^ ^ ^ ^
// 8 7 6 5 4 3 2 1 0 <= Index
int n = 2, x = 1;
number ^= (-x ^ number) & (1LL << n);
```

### Asignar el numero de bits a una variable

**Nota:** `n` no puede exceder el numero de bits del tipo de dato _Ej:_ `n <= 32` si el tipo de dato es `int`
```c++
struct Binary {
    unsigned int number : 1; // Variable con capacidad de 2^n = (0, ..., n)
    // En este caso n=1
};

int main() {
    Binary x {1};
    cout<<x.number<<endl;
    return 0;
}
```

# Bibliografia

[[1]](https://books.goalkicker.com/CPlusPlusBook/) "Free C++ Programming Book", Books.goalkicker.com, 2019. Available: https://books.goalkicker.com/CPlusPlusBook/.