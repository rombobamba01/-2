# AK2_HW2
## Лістинг:

### Makefile

```makefile
AK2_HW2: main.o calculator.o
	g++ -o AK2_HW2 main.o calculator.o
main.o: main.cpp 
	g++ -c main.cpp
calculator.o: calculator.cpp
	g++ -c calculator.cpp

clean: 
	rm AK2_HW2
	rm main.o
	rm calculator.o
```
### CMakeLists.txt

```cmake
cmake_minimum_required(VERSION 3.16.3)

project("AK2_HW2" VERSION 0.1.0)
 
add_library(calculator STATIC calculator.cpp)
add_executable("${PROJECT_NAME}" main.cpp)
target_link_libraries("${PROJECT_NAME}" calculator)
```

### main.cpp

```cpp
#include "calculator.h"
#include "iostream"
int main ()
{
	Calculator calculator;
	std::cout << calculator.Sub(22, 15) << std::endl;
	return 0;
}
```

### calculator.cpp

```cpp
#include "calculator.h"

int Calculator::Add (double a, double b)
{
	return a + b;
}

int Calculator::Sub (double a, double b)
{
	return Add (a, -b);
}
```

### calculator.h

```cpp
#ifndef CALCULATOR_H
#define CALCULATOR_H

class Calculator
{
	public:
		int Add (double, double);
		int Sub (double, double);
};

#endif//CALCULATOR_H
```
## Висновок

В данній лабораторній роботі я ознайомився та використав **CMake** та **Ninja**.

