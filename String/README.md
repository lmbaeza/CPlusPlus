# String en C++

### Split

```c++
// Pag: 250
auto split(string str, string separator) {
	vector<std::string> tokens;
	
	for ( auto i = strtok(&str[0], separator.data());
		  i != NULL;
		  i = strtok(NULL, separator.data())	) {
		
		tokens.push_back(i);
	}
	
	return tokens;
}

int main() {
	std::string str{ "The---*---quick---*---brown---*---fox" };
	
	auto tokens = split(str, "---");
	
	for(auto i: tokens) {
		cout<<i<<endl;
	}
	return 0;
}
```

### Sub String

```c++
// Pag:  252

string hello {"Hello World"};
	
cout<<hello.substr(0, 4)<<endl;
// Hell
```

### Replace String

```c++
string hello {"Hello World"};
string name {"Luis"};

hello.replace(6,6+name.size(), name);
// Hello Luis

hello.replace(hello.begin()+6, hello.end(), name);
// Hello Luis
```
### To String

`std::to_string` y `std::to_wstring`

```c++
// Pag: 257
int number = 100;
	
string str = to_string(number);
wstring wstr = to_wstring(number);

cout<<str<<endl;
// 100
cout<<wstr.data()<<endl;
// 0x7ffd7d1131a0
```

### Number to String (Parte 2)

```c++
// Pag: 257
#include <sstream>
#include <string>
using namespace std;

string toString(int number) {
	ostringstream ss;
	ss<<number;
	return ss.str();
}

string toString(double number) {
	ostringstream ss;
	ss<<number;
	return ss.str();
}

int main() {
	int numberInt = 1000;
	string intStr = toString(numberInt);

	double numberDouble = 3.14159;
	string doubleStr = toString(numberDouble);

	cout<<intStr<<" "<<doubleStr<<endl;
	return 0;
}
```

### To String <template> (Parte 3)
```c++
template<class T>
string toString(const T& x) {
	ostringstream ss;
	ss << x;
	return ss.str();
}

int main() {
	
	int number = 100;
	
	string str = toString<int>(number);
	
	cout<<str<<endl;
	
	return 0;
}
```

### Accediendo al caracter de un string

`.at()` Permite controlar excepciones

```c++
string foo {"Bar"};
char c = ' ';
try {
	c = foo.at(9);
} catch(out_of_range e) {
	cout<<"Error: Index fuera de Rango"<<endl;
}
cout<<c<<endl;
```

`string::operator[]` No permite controlar excepciones


```c++
string foo {"Bar"};
char c = foo[9]; // Aborted (core dumped)
cout<<c<<endl;
```

### Verificar si un string en prefijo de otro

```c++
bool isPrefix(string str, string prefix) {
	
	auto ans = mismatch(
		prefix.begin(), prefix.end(),
		str.begin(), str.end()
	);
		
	return prefix.size() <= str.size() && (ans.first == prefix.end());
}

bool isPrefix(string str, string prefix) {
	return prefix == str.substr(0, prefix.size());
}

int main() {
	
	string prefix {"Foo"};
	string str {"FooBar"};
	
	bool ans = isPrefix(str, prefix);
		
	cout<<ans<<endl;
	
	return 0;
}
```

### Iterar un String

```c++
string hello = "Hello World";
	
for(auto i: hello) {
	cout<<i<<endl;
}

for(size_t i = 0; i < hello.size(); ++i){
	cout<<hello[i]<<endl;
}
```

### String to Number (Parte 1)

```c++
int num1       = stoi(ten); // 32 Bits
long num2      = stol(ten); // 64 Bits
long long num3 = stoll(ten); // 64 Bits

float num4       = stof(ten); // 32 Bits
double num5      = stod(ten); // 64 Bits
long double num6 = stold(ten); // 128 Bits
```

### String to Number (Parte 2)

```c++
string ten = "10";
string ten_octal = "12";
string ten_hex = "0xA";

int num1 = stoi(ten, 0, 2); // Returns 2
int num2 = stoi(ten_octal, 0, 8); // Returns 10
long num3 = stol(ten_hex, 0, 16); // Returns 10
long num4 = stol(ten_hex); // Returns 0
long num5 = stol(ten_hex, 0, 0); // Returns 10 as it detects the leading 0x

```

### Encontrar una secuencia en un string

```c++
// Pag: 262

std::string str = "Curiosity killed the cat";
auto it = str.find("cat");

if (it != std::string::npos){
	std::cout << "Found at position: " << it << '\n';
} else {
	std::cout << "Not found!\n";
}
```