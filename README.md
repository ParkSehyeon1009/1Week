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
사용자 자신의 데이터형을 설계한다는 것은 표현하고자 하는 **데이터에 가장 적합한 형태**로<br> 사용자가 데이터형을 **직접 설계할 수 있다**는 것을 뜻한다.<br><br>
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
<br>

**sizeof 와 climits**<br>
sizeof : 자료형 또는 변수의 크기를 byte 단위로 반환하는 연산자
climits : 데이터형의 한계값을 나타내기 위한 기호 상수들이 정의되어 있는 헤더<br>
| 기호상수 | 의미 |
| :--: | :-- |
| CHAR_BIT | char형의 비트 수 |
| CHAR_MAX | char형의 최대값 |
| CHAR_MIN | char형의 최소값 |
| SCHAR_MAX | signed char형의 최대값 |
| SCHAR_MIN | signed char형의 최소값 |
| UCHAR_MAX | unsigned char형의 최대값 |
| SHRT_MAX | short형의 최대값 |
| SHRT_MIN | short형의 최소값 |
| USHRT_MAX | unsigned short형의 최대값 |
| INT_MAX | int형의 최대값 |
| INT_MIN | int형의 최소값 |
| UINT_MAX | unsigned int형의 최대값 |
| LONG_MAX | long형의 최대값 |
| LONG_MIN | long형의 최소값 |
| ULONG_MAX | unsigned long형의 최대값 |
| LLONG_MAX | long long형의 최대값 |
| LLONG_MIN | long long형의 최소값 |
| ULLONG_MAX | unsigned long long형의 최대값 |

**unsigned**<br>
  - unsigned 형은 음수값 표현을  포기함으로 자료형이 표현할수 있는 양수값의 범위를 늘린것<br>
**char 형**<br>
  - 문자와 숫자를 저장하기 위한 자료형
  - ASCII 같은 문자세트로 문자 또한 나타낼수 있음

**bool 형**<br>
  - 변수가 참이나 거짓 중 어느 한 가지 값만 가질 수 있음
  - 0이 아닌 값은 참, 0인 값을 거짓 으로 해석

**const 제한자**<br>
  - 변수를 상수화 시키는 제한자
  - 사용법은 아래와 같다
```cpp
const 자료형 변수명 = 값;
```
**데이터형 변환**<br>
아래와 같은 상황에서 자동으로 데이터형 변환이 수행된다
  - 특정 데이터형의 변수에 다른 데이터형의 값을 대입했을 때
  - 수식에 데이터형을 혼합하여 사용했을 때
  - 함수에 매개변수를 전달할때

강제로 데이터형을 변환하고 싶을때에는 아래와 같이 코드를 작성하면 된다.
```cpp
(데이터형) 변수명
```
# 04장 복합 데이터형
**배열**<br>
데이터형이 같은 여러 개의 값을 연속적으로 저장할 수 있는 데이터구조<br>
배열 선언에는 아래와 같은 세 가지 를 선언한다.
  - 각 원소에 저장될 값의 데이터형
  - 배열의 이름
  - 배열 원소의 개수

아래는 선언 예시이다
```cpp
int sample[10]
즉
데이터형 배열명[배열크기]
```
<br>

**배열 초기화 규칙**<br>
  - 초기화 형식은 배열을 정의하는 곳에서만 사용할 수 있다.
  - 배열을 다른 배열에 통째로 대입할 수 없다.
  - 단 인덱스를 사용하여 배열 원소에 개별적으로 값을 대입하는것은 가능
  - 배열을 부분적으로 초기화하면 나머지 원소는 모두 0으로 설정됨

**문자열**<br>
메모리에 바이트 단위로 연속적으로 저장되어 있는 문자들
```cpp
char dog[8] = {'b','e','a','u','x','','I','I'}
//문자열이 아니다
char dog[8] = {'f','a','t','e','s','s','a','\0'}
//문자열 이다
```
위와 같이 두 번째 배열만이 문자열인 이유는 널 문자를 만날 때까지 문자 단위로 문자열을 처리하기 때문
아래와 같은 경우도 문자열이다.
```cpp
char bird[10] = "Mr. Cheeps" // \0을 저장
char fish[] = "Bubbles" // 컴파일러가 알아서 처리
```
큰 따옴표로 묶인 문자열은 끝내기 널 문자를 암시적으로 가지고 있다.<br>
그렇기에 문자열의 끝에 널 문자를 명시적으로 넣을 필요가 없다.

<br>**문자열 상수의 결합**<br>
빈칸,탭,캐리지 리턴과 같은 화이트스페이스로 분리된 두 개의 문자열 상수는 하나의 문자열 상수로 결합됨

<br>**배열에 문자열 사용**<br>
```cpp
char name[10] = "C++owboy"
// 문자열 상수로 초기화
char sample[15]
cin >> sample
//cin 을 통한 문자열을 배열에 저장
```
**string 클래스**<br>
string 클래스를 사용하기 위해서는 string 헤더를 포함시켜야 한다.<br>
string 과 문자 배열을 가장 큰 차이점은 string 은 **단순한 변수**로 선언한다는 점이다.<br>
string 클래스의 조작은 아래와 같다.
```cpp
strcpy(charr1, charr2) //charr2를 charr1에 복사한다
strcat(charr1, charr2) // charr2의 내용을 charr1에 추가한다
str1.size() // str1의 길이를 구한다
strlen(charr1) // charr1의 길이를 구한다
```
**구조체**
  - 모든 정보를 하나의 단위로 묶을 수 있는 데이터 형식
  - 사용자가 정의할 수 있는 데이터형
  - 구조체는 아래 두 단계를 거쳐 선언된다.
    - 구조체 서술 정의
    - 구조체 서술에 따라 구조체 변수 생성
구조체의 사용은 아래와 같다
```cpp
struct sample
{
  char name[10];
  int age;
};
void main(){
  sample guest =
  {
   "Sehyeon"; // name 값
  23; // age 값
  }
}
```
위와 같이 코드를 작성하면 아래와 같이 값이 할당된다
```cpp
guest.name = Sehyeon
guest.age = 23
```
**공용체**
서로 다른 데이터형을 한 번에 한 가지만 보관할 수 있는 데이터 형식<br>
즉 구조체는 여러 데이터형을 한 번에 보관할수 있지만 공용체는 하나의 데이터형 만 보관할수 있다.<br>
예시로 아래의 코드를 생각해보자
```cpp
union sample
{
  int int_sample
  long long_sample
}
```
만약 int_sample에 값을 저장한 후 long_sample에 값을 저장한다면<br>
int_sample 의 값은 소실되게 된다.<br>
즉 union 은 **특정 공간을 효율적으로 관리**하기 위해<br>
struct 는 **데이터를 효율적으로 처리**하기 위해서 사용된다.<br>
아래의 링크에서 Union의 보다 자세한 설명을 다룬다.<br>
[**Union 왜 쓰는지?**](https://suho413.tistory.com/entry/Union-%EC%82%AC%EC%9A%A9-%EC%9D%B4%EC%9C%A0)

<br>**열거체**<br>
열거체는 코드로 보는것이 이해가 빨라 코드를 사용하여 설명하겠다.<br>
```cpp
enum sample {one,two,three};
```
위 구문은 아래 두 가지 일을 수행한다.
  - sample을 새로운 데이터형의 이름으로 만든다. enum형 변수를 열거체 라고 부른다
  - one,two,three 등을 0에서 2까지의 정수 값을 각각 나타내는 기호 상수로 만든다. 이 상수들을 열거자라 부른다.

아래 코드처럼 열거자 값을 설정할수도 있다.
```cpp
enum sample {one = 3, two = 4, three = 5}
```
단 대입되는 값은 정수여야 한다.
# 05장 루프와 과계 표현식
