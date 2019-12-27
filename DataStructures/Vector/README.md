# Vectores


### Crear matriz de -1

```c++
typedef uint32_t ui32;
typedef uint64_t ui64;
typedef int32_t i32;
typedef int64_t i64;

int main() {
    ui32 rowN=3, colN=7;
    vector<vector<i32>> matrix (rowN, vector<i32>(colN, -1));

    for(auto row: matrix) {
        for(auto col: row) {
            cout<<col<<" ";
        }
        cout<<endl;
    }
    // row=3, col=7
    // -1 -1 -1 -1 -1 -1 -1 
    // -1 -1 -1 -1 -1 -1 -1 
    // -1 -1 -1 -1 -1 -1 -1
    return 0;
}
```

### Iterar un Vector

```c++
typedef int32_t i32;
vector<i32> arr (10, -1);	
for(auto &data: arr) {
    cout<<data<<endl;
}
```

### Iterar un Array c++

```c++
int numbers[] = {1, 2, 3, 4, 5};

for(int num: numbers) {
    cout<<num<<endl;
}
```

### Iterar una Estructura

```c++
struct Rango {
    int arr[3];
    const int* begin() const {return &arr[0];}
    const int* end() const {return &arr[3];}
    int* begin() {return &arr[0];}
    int* end() {return &arr[3];}
};

int main() {
    Rango rango {{1, 2, 3}};

    for(auto value : rango) {
        cout<<value<<endl;
    }
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

# Bibliografia

[[1]](https://books.goalkicker.com/CPlusPlusBook/) "Free C++ Programming Book", Books.goalkicker.com, 2019. Available: https://books.goalkicker.com/CPlusPlusBook/.