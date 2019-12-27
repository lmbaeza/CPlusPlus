# Input & Output


### De Entero a Hexadecimal y de Hexadecimal a Entero

```c++
// pag: 71
#include <sstream>
using namespace std;

// std::setbase(16) = std::hex
// std::setbase(10) = std::dec
// std::setbase(8)  = std::oct

string toHex(int number) {
    ostringstream ss;
    // Igual
    // ss<<std::setbase(16)<<number;
    // que
    ss<<std::hex<<number;
    return ss.str();
}
int hexToInt(string hexStr) {
    int number;
    std::istringstream(hexStr) >> std::hex >> number;
    return number;
}
int main() {

    int number = 0x3E8;
    string hexStr = toHex(number);

    // Hexadecimal
    cout<<hexStr<<endl;

    // Decimal
    cout<<hexToInt(hexStr)<<endl;

    return 0;
}
```

### Precision de numeros Reales

```c++
// pag: 72
#include <cmath>
#include <limits>

typedef std::numeric_limits<long double> ld;

int main() {

    long double PI = acos(-1);

    cout<<setprecision(ld::digits+1)<<PI<<endl;
    // Maxima precision
    // 3.141592653589793115997963468544185161590576171875

    cout<<setprecision(5+1)<<PI<<endl;
    // Precision de 5
    // 3.14159

    return 0;
}
```

### Input Hexadecimal a Entero

```c++
// pag: 72
#include <sstream>
using namespace std;

istringstream in("F 0xA");
int n1, n2;

in>>setbase(16)>>n1>>n2;

cout<<n1<<" "<<n2<<endl;
//    15       10
```

# Bibliografia

[[1]](https://books.goalkicker.com/CPlusPlusBook/) "Free C++ Programming Book", Books.goalkicker.com, 2019. Available: https://books.goalkicker.com/CPlusPlusBook/.