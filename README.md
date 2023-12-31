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

<br>**포인터와 메모리 해제**<br>
포인터 : 값 자체가 아니라 값의 주소를 저장하는 변수<br>
*포인터변수명 : 주소에 저장된 값을 불러옴<br>
포인터를 선언하는 방법은 아래와 같다.
```cpp
데이터형 * 변수명;
```
포인터를 사용할 때에는 간접 참조 연산자를 사용하기 전에 반드시 포인터를 적절한 주소로 초기화 시켜주어야 한다.<br>
만약 초기화를 시켜주지 않는다면 엉뚱한 값이 들어가 있을수도 있어 에러가 발생할수 있다. 이와 같은 에러는 가장 찾기힘든 버그이다.

<br>**new를 사용한 메모리 대입**<br>
new 연산자는 데이터형을 보고 몇 바이트가 필요한지를 파악하고 적당한 메모리를 찾아 필요한 만큼 블록을 대입한뒤 그 주소를 리턴한다.<br>
사용 방법은 아래와 같다.
```cpp
typeName * pointer_name = new typeName
```
이때 두번의 데이터형을 요구하는데 한 번은 **요구하는 메모리의 종류를 지정하기 위해**
다른 한 번은 **적당한 포인터를 선언하기 위해** 사용한다.

<br>**delete 연산자**<br>
delete 연산자는 사용한 메모리 해제를 위해 사용한다.<br>
new 연산자로 메모리를 대입한 후에는 나중에 delete를 사용하여 해제해 줘야 한다. 그렇지 않으면 **메모리 누수**가 발생할수 있다.<br>
한번 해제한 메모리 블록은 다시 해제할수 없으며 또한 보통의 변수를 선언하여 대입한 메모리는 delete로 해제할 수 없다.<br>

**new를 사용한 동적 배열의 생성**<br>
아래와 같은 형식으로 동적 배열을 생성할수 있다.
'typeName * arrayName = new typeName[arraySize]; // arraySize개의 typeName형 값을 저장할 블록을 대입'
동적 배열을 해제하기 위해서는 아래와 같이 delete 형식을 사용해야 한다.
'delete []arrayName'
또한 new와 delete를 사용할 때 아래와 같은 규칙을 지켜야 한다.
1. new로 대입하지 않은 메모리는 delete로 해제하지 않는다.
2. 같은 메모리 블록을 연달아 두 번 delete로 해제하지 않는다.
3. new []로 메모리를 대입한 경우에는 delete []로 해제한다.
4. new를 대괄호 없이 사용했으면 delete도 대괄호 없이 사용한다.
5. 널 포인터에는 delete를 사용하는 것이 안전하다

**포인터 연산**<br>
예를 들어 ps 라는 포인터가 있다고 가정을 해보자<br>
만약 ps 포인터에 1을 더한다면 어떻게 될까? ps 포인터가 가르키는 값이 1이 증가할까? 아니면 ps 포인터의 주소값이 1이 증가할까?<br>
정답은 후자이다. <br>
아래의 코드로 포인터 연산을 알수 있다
```cpp
short stacks[3] = {3,2,1}
short * ps = &stacks[0]
ps = ps+1;
cout << *ps
```
출력 결과는 아래와 같다.<br>
`2`<br>
위 출력 결과로 알수 있든 주소값이 1이 증가하면 *ps는 증가한 주소값이 가르키는 값을 뱉어내게 된다.<br>

**new를 사용한 동적 구조체의 생성**
new를 사용하여 동적 구조체를 생성하는 방법은 아래와 같다
`structName * pointerName = new structName`
단 동적 구조체에는 도트 멤버 연산자를 사용할수 없다. 이유는 동적 구조체에는 이름이 없기 때문이다.<br>
따라서 동적 구조체에 접근하기 위해서는 아래와 같은 방법을 사용해야 한다.
```cpp
(*pointerName).ValueName
OR
pointerName->ValueName
```
**자동 공간, 정적 공간, 동적 공간**<br>
<br>
**자동 공간**
  - 자동 공간을 사용하는 함수 안에서 정의되는 보통의 변수들을 자동 변수 라고 부른다.
  - 자동 변수들이 자신이 정의되어 있는 함수가 호출되는 순간에 자동으로 생겨나 함수 종료 전까지만 존재
  - 자동 변수는 스택에 저장
  - 후입 선출 또는 LIFO

**정적 공간**
  - 프로그램이 실행되는 동안에 지속적으로 존재하는 공간
  - 정적 변수는 프로그램이 실행되는 동안에 지속적으로 존재


**동적 공간**
  - 자유 공간 혹은 힙 이라고 부르며 자유공간, 메모리 풀을 관리
  - new,delete 보다 융통성 있는 방법으로 제공해준다
  - 데이터의 수명은 프로그램의 수명이나 함수의 수명에 얽매이지 않음
  - new 와 delete를 함께 사용하면 일반 변수를 사용할때 보다 메모리에 대해 더 강력한 제어권을 가짐


# 05장 루프와 관계 표현식
**for 루프**<br>
for 루프문은 아래와 같이 사용한다
```cpp
for(선언문; 조건문; 지시문)
{
  반복실행할 구문;
}
```
따라서 for 루프는 아래의 순서로 진행된다.
1. 조건 검사에 사용할 카운터 값을 초기화한다.
2. 루프를 진행할 것인지 조건을 검사한다.
3. 루프 몸체를 수행한다.
4. 카운터 값을 갱신한다.
<br> 따러서 루프 몸체(반복실행될 구문)은 조건 검사가 참일 경우에만 수행한다.<br>

**구문과 표현식**<br>
아래는 표현식의 예시이다
`28 * 20, 10'
28*20 은 값이 560인 표현식이며 10은 값이 10인 표현식이다.<br>
C++ 에서의 표현식은 하나의 값을 가진다. 그 값은 대부분이 명백하다.<br>
**부수효과** : 표현식의 값을 평가하려는 목적이 메모리에 있는 데이터 값의 변경을 부수적으로 가져오는 것<br>
즉 수식을 평가할 때 변수에 저장되어 있는 값과 같은 것이 변경될 때 일어나는 효과<br>
**시퀸스포인트** : 프로그램의 실행이 다음 단계로 넘어가기 전에 모든 부수효과들이 확실하게 평가되는 포인트<br>
즉 명령한 값의 변경이 이루어지는 지점이다.<br>

**접두어와 접미어**<br>
접두어와 접미어는 최종적으로 같은 역할을 수행한다. <br>
둘의 차이점은 C++ 버전에서는 이 연산자들을 클래스에 대해 정의하는 것을 허용하는데<br> 
이와 같은 경우에 접미어 버전은 값의 복사본을 만든뒤 복사본의 값을 증가시키고 그 복사본의 값을 리턴하는 방식으로 동작한다.<br>
즉 클래스의 경우 접두어 버전이 접미어 버전보다 약간 더 효율적이다.<br>

**증가 감소 연산자와 포인터**<br>
`*++pt // ++가 pt에 적용되고 난 후 pt의 새로운 값에 (*)이 적용됨`<br>
`++*pt //*pt 가 지시하는 값이 증가됨`

**조합 대입 연산자**<br>
조건 대입 연산자는 표현식을 보다 간결하게 나타낼수 있게 해준다.<br>
예시로 아래와 같은 조합 대입 연산자는 주석과 같은 역할을 수행한다. <br>
`a += b // a = a + b`<br>
주의할 점은 결과를 왼쪽 피연산자에 대입하는 것이기 때문에 왼쪽 피연산자는 변수, 배열의 원소, 구조체의 멤버, 포인터에 의해 참조되는 데이터와 같이<br>
**실제로 값을 대입할 수 있는 것**이어야 한다.<br>

**관계 표현식**<br>
```cpp
a < b // b보다 작다.
a <= b // b보다 작거나 같다.
a == b // b와 같다.
a > b // b보다 크다.
a >= b // b보다 크거나 같다.
a != b // b와 다르다 
```
위 표현식의 비교에 따라 true 혹은 false 를 return 한다.<br>

**while 루프**<br>
for 루프에서 초기화 부분과 갱신 부분을 없애고 **루프 몸체와 조건 검사 부분만 남겨놓은것**이 while 루프이다.<br>
즉 아래와 같이 사용한다
```cpp
while (조건식)
  루프 몸체
```
조건식이 true일 경우에만 루프 몸체를 실행한다. 처음 부터 조건식이 false 일 경우 한번도 실행되지 않는다.<br>
만약 한번이라도 실행시키고 싶다면 do while 문이 있다.
**do while 루프**
do while 루프는 루프 몸체를 먼저 실행후 조건 검사가 실행된다. 즉 무조건 한번은 실행된다는 소리이다.<br>
사용 방법은 아래와 같다.
```cpp
do
  루프 몸체
while(조건식)
```

**중첩 루프와 2차원 배열**
중첩 루프를 통해 다차원 배열을 사용할수있다.<br>
물론 선언을 할 때 초기화를 하고 인덱스를 직접 지정해서 사용할수도 있다.<br>
아래는 예시 코드이다.
```cpp
int sample[3][3] =
{
  {1,2,3},
  {4,5,6},
  {7,8,9},
}; //선언 하자마자 초기화
for(int i = 0; i < 3; i++)
{
  for(int j = 0; j < 3; j++)
  {
    sample[i][j] = i+j; //중첩 루프를 통해 2차원 배열 접근
  }
}
``` 
