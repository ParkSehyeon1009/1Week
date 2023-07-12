# 01장 C++ 첫걸음
**OOP**(Object-Oriented Programming) **언어**
  - 해결해야 할 문제를 언어의 절차적 접근 방식에 억지로 끼워 맞추지 않고, 언어 자체를 해결해야 할 문제에 맞추는 언어
  - 즉 해결해야 할 문제의 특성에 맞게 데이터형 자체를 설계한다.
  - 재활용이 가능한 소스 코드를 쉽게 작성할 수 있음
  - 정보를 은닉할 수 있기 때문에 비인가된 접근으로부터 데이터를 안전하게 보호할수 있음
  - 다형성(Polymorphism)을 이용하여 이름이 같은 연산자와 함수를 여러번 정의할 수 있기 때문에 상황에 따라 적당한 연산자나<br> 함수를 프로그램이 스스로 선택하게 할 수 있다.
  - 상속(inheritance)을 이용하여 하나의 클래스로부터 새로운 클래스를 유도하는 등 절차적 프로그래밍과는 완전히 다른 접근 방식을 취한다.

**Class**
  - C++ 에서 OOP와 같은 목적으로 설계되는 새로운 데이터형
  - 객체를 나타내는 데이터 부분과 그 데이터를 대상으로 수행할 수 있는 동작 부분으로 정의
  - 객체(Object) 는 클래스에 의해 만들어지는 특정한 데이터 구조

**이식성**
  - 첫 번째 장애 요인 : 특정 하드웨어에 종속적인 프로그램은 이식성을 갖지 못함
  - 두 번째 장애 요인 : 언어 간의 상의성

**프로그래밍 절차**
1. 소스 코드 : 텍스트 에디터를 사용하여 프로그램을 작성한 파일
2. 컴파일러
3. 목적 코드 : 소스 코드를 컴퓨터 내부에서 사용하는 기계어로 번역된 파일
4. 링크 (시동 코드, 라이브러리 코드)
5. 실행코드 : 사용자가 만든 목적 코드와 라이브러리 함수에 해당하는 목적 코드, 그리고 실행할 수 있는 프로그램을 만드는데 필요한<br> 시동코드를 함께 링크해서 최종적으로 만들어지는 파일

# 02장 C++ 시작하기
**출력**
```cpp
#include <iostream> //선행처리 지시자
void main()
{
  std::cout << "Hello World"; // 출력문
  std::cout << endl;  // 줄바꿈
}
```
위에 사용되었던 endl 같은 특별한 표기들을 **조정자** 라고 부른다.
줄바꿈 같은 경우 아래와 같이 개행 문제 **\n** 을 사용하여 endl 의 역할을 대신할수 있다.
```cpp
std::cout << "Hello World\n";
```
만약 std:: 접두어를 붙이지 않고 사용하고 싶다면 아래의 코드를 사용하면 된다.
```cpp
using namespace std;
```
변수를 출력하고 싶을때는 아래와 같이 코드를 작성하면 된다.
```cpp
cout << 변수명;
```
**변수 선언**
```cpp
int test = 1;
OR
int test;
```
저장될 데이터형을 지정후 변수명을 지정한다. 변수를 선언할때 값을 지정해도 되지만 후에 **대입 구문** 을 통해 값을 지정해도 상관없다.<br>
단 값이 지정되지 않은 변수를 사용할 경우 에러가 뜰수 있음으로 주의해야 한다.

**입력**<br>
값을 입력받고 그 값을 변수에 저장하고 싶다면 아래의 코드를 사용하면 된다.
```cpp
cin >> 변수명
```
**함수**
  - C++ 프로그램을 구성하는 모듈
  - OOP의 정의에 필수적인 사항
  - C++ 에는 두가지의 함수 유형이 있다. (리턴값이 있는 함수, 없는 함수)

**리턴값이 있는 함수**<br>
리턴값이 있는 함수는 변수에 대입할 수 있는 값을 만들어 낸다.<br>
예시로 제곱근을 리턴하는 sqrt 함수를 사용해 보겠다.
```cpp
x = sqrt(6);
```
위와 같이 작성했을시 sqrt 함수를 호출하고 sqrt 함수는 6의 제곱근을 리턴해준다.<br>
그리고 리턴받은 값을 x에 대입한다.
<br>
<br>
리턴값이 있는 함수 호출 구조는 아래와 같다.
1. 함수 호출
2. 함수 코드 실행
3. 호출 함수에 값을 리턴
<br>

**함수 원형**
```cpp
double sqrt(double) //함수 원형
```
위와 같은 코드를 함수 원형 이라고 한다.<br>
함수 원형은 함수를 정확히 서술하고 있는것이다.
<br>! 함수 원형과 함수 정의를 혼동하면 안된다.
<br>**함수 원형** : 함수의 인터페이스만 알려줌
<br>**함수 정의** : 그 함수가 수행할 작업을 위한 실제 코드

**사용자 정의 함수**
<br>
사용자 정의 함수 : 사용자가 필요한 기능을 직접 정의하여 사용하는 함수<br>
사용 방법은 아래와 같다
```cpp
void sample(int n)
{
  std::cout << n << "이 입력되었습니다.\n";
}
```
main 함수에서 sample(3) 을 호출하면 아래와 같은 실행 결과가 나온다.
```
3이 입력되었습니다.
```
위와 같이 리턴값이 없는 사용자 정의 함수를 만들수도 있지만<br>
아래와 같이 리턴값이 있는 사용자 정의 함수 또한 만들수 있다.
```cpp
int return_sample(int n)
{
  return n * 4;
}
```
main 함수에서 return_sample(3) 을 호출하면 아래와 같은 실행 결과가 나온다
```
12
```
# 03장 데이터처리
OOP의 진수는 사용자가 **데이터형을 스스로 설계하고 확장 할 수 있다**는 데에 있다.<br>
사용자 자신의 데이터형을 설계한다는 것은 표현하고자 하는 **데이터에 가장 적합한 형태**로<br> 사용자가 데이터형을 **직접 설계할 수 있다**는 것을 뜻한다.<br>
이번 장에서는 데이터형의 기본형에 대해서만 알아볼것이다.<br><br>
**간단한 변수**<br>
컴퓨터에 정보를 저장하기 위해서는 아래와 같은 세 가지를 알아야 한다.
1. 어디에 저장되는가?
2. 어떤 값이 저장되는가?
3. 어떤 종류의 정보인가?

**변수 이름**<br>
C++ 에서 변수 이름을 지을 때에는 다음과 같은 규칙을 따라야 한다.
1. 변수 이름에는 영문자, 숫자, 밑줄, 문자만을 사용할 수 있다.
2. 숫자를 변수 이름의 첫 문자로 사용할 수 없다.
3. 변수 이름에서 대문자와 소문자는 구별된다.
4. C++의 키워드는 변수 이름으로 사용할 수 없다.
5. 두 개의 밑줄 문자로 시작하는 이름이나, 밑줄 문자와 대문자로 시작하는 이름은<br> 그것을 사용하는 컴파일러와 리소스가 사용하기로 예약되어 있다.<br>하나의 밑줄 문자로 시작하는 이름은 그것을 사용하는 컴파일러와 리소스가 전역 실별자로 사용하기로 예약되어 있다.
6. 변수 이름의 길이는 제한이 없으며 변수 이름에 쓰인 모든 문자는 유효하다.<br> 그러나 어떤 플랫폼은 고유의 길이 제한이 있다.
<br>
다섯 번째 규칙은 __time_stop 또는 _Dount와 같은 이름을 사용해도 컴파일러 에러가 발생하지 않는다.<br>
단 정의되지 않은 이상한 동작을 일으킨다. 이때문에 앞의 네 가지 규칙과 성격이 조금 다르다.<br>
에러가 발생하지 않는 이유는 이름은 적합하지만 컴파일러가 사용하기로 예약되어 있기 때문이다.<br>

**정수형**<br>
C++의 여러 정수형들은 서로 다른 크기의 메모리를 사용한다. <br>메모리 블록이 클수록 나타낼수 있는 정수 값의 범위가 크다.
<br>signed 데이터형은 양수값과 음수값을 모두 나타낼수 있으나, unsigned 데이터형은 양수값만 나타낼수 있다.<br>
정수를 저장하는 데 사용되는 메모리의 크기를 폭 이라고 한다. 메모리 크기가 클수록 폭이 넓다.<br>

**short,int,long,long long 정수형**<br>
컴퓨터의 메모리는 Bit라는 단위로 이루어진다.<br>
각 정수형은 정수를 저장하는 데 사용하는 Bit 수가 다르다.<br>
정수형의 표준은 아래와 같다.
  - short형은 최소한 16비트를 가진다.
  - int형은 최소한 short만큼은 크다.
  - long형은 최소한 32비트를 가지며 최소한 int 만큼은 크다.
  - long long형은 최소한 64비트를 가지며 최소한 long 만큼은 크다.


# 04장 복합 데이터형

# 05장 루프와 과계 표현식
