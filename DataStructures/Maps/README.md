# Map


### Verificar si un dato fué ingresado correctamente

```c++
// pag: 123
map<string, int> countries;
	
auto [iterator, success] = countries.insert({"Colombia", 45});

cout<<success<<endl;
```

### Iterar un HashMap en C++

```c++
// pag: 123
map<string, int> countries;
	
countries.insert({"Colombia", 40});
countries.insert({"Argentina", 35});
countries.insert({"Brazil", 150});


for(auto [key, value] : countries) {
	cout<<"Key: "<<key<<"\t Value: "<<value<<endl;
}
```

# Bibliografia

[[1]](https://books.goalkicker.com/CPlusPlusBook/) "Free C++ Programming Book", Books.goalkicker.com, 2019. Available: https://books.goalkicker.com/CPlusPlusBook/.