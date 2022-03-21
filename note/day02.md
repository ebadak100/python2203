# 파이썬 기본 문법과 입출력
#### 학습목표 :  파이썬 프로그램 작성 및 실행 방법
> 1. 파이썬의 특징
> 2. 파이썬의 기본문법
> 3. 파이썬 기본 입출력 함수
> 4. 자료형과 연산자 : 숫자형, 문자열

## 1. 파이썬의 특징
- [파이썬 언어의 특징](https://jjinfotech.tistory.com/21)  
- [파이썬 언어의 특징](https://digital-play.tistory.com/44)

## 2. 파이썬의 기본문법
### 2.1 세미콜론
C, Java는 구문이 끝날 때 ;(세미콜론)을 붙여야만 한다. 그러나, 파이썬은 세미콜론을 붙이지 않는다. 
단, 붙여도 문법 에러는 발생하지 않는다. 보통 한 줄에 여러 구문을 사용할 때 세미콜론으로 구분한다.
```python 
print('Hello, Korea IT Academy')
print('Hello');print('Korea IT Academy')
```


```python
print("문자열") = print('문자열')
print(수식)
print(숫자값)
```



### 2.2 주석
- 프로그램의 실행에는 아무런 영향을 주지 않으며, 프로그램의 이해를 돕기 위해 작성하는 부분을 주석comment라고 함. 
- 보통 주석은 코드에 대한 자세한 설명을 작성하거나, 특정 코드를 임시로 사용하지 않도록 할 때 사용.   
- 한줄 주석 : 코드의 맨 앞에 #을 사용, 해당 줄을 모두 주석 처리 또는 코드 뒤에 #으로 주석 처리하여 뒤에 있는 부분 주석처리함.

```python
#Hello, Korea IT Academy 출력
print('Hello, Korea IT Academy')
a = 1 + 2 # 더하기
```
- 블록주석 : 각 줄마다 맨 앞에 #을 넣어주고, 코드를 읽기 쉽도록 # 뒤에 공백을 한 칸 띄운다.
```python
# 더하기
# a = 1 + 2
# print('Hello, Korea IT Academy')
```


```python

```

### 2.3 들여쓰기★★★
일정한 간격을 띄워서 작성하는 방법이다. 특히 파이썬은 들여쓰기 자체가 문법이다.   
예를 들어 if의 다음 줄은 항상 들여쓰기를 해야 한다. 만약 들여쓰기를 하지 않으면 문법 에러이므로 코드가 실행되지 않는다.
```python
a = 10
if a == 10:
print('10입니다.')    # 들여쓰기 문법 에러
```
올바른 코드는 다음과 같이 if 다음 줄은 들여쓰기를 해주어야 한다.  
```python
a=10
if a==10:
    print('10입니다')
```
※ 파이썬은 공백 2칸, 공백 4칸, 탭 문자 등을 각각 사용해도 동작이 잘 된다.   
하지만 [파이썬 코딩 스타일 가이드(PEP 8)](https://www.python.org/dev/peps/pep-0008/)에서는 공백 4칸으로 규정하고 있으니 공백 4칸을 사용하는 것이 좋겠다.


```python
# 파이썬에서 들여쓰기(Indentation)는 문법사항
# 필요한 곳에서 하지 않으면 오류 발생

if 5<10:
    print("5는 10보다 작다")
    print("***************")
print("프로그램이 종료되었습니다")
```

### 2.4 코드 블록
코드 블록은 특정한 동작을 위해서 코드가 모여 있는 상태를 뜻하며 파이썬은 들여쓰기를 기준으로 코드 블록을 구성한다.  
```python
if a == 10:
      print('10')
      print('입니다.')
```
단, 같은 블록은 들여쓰기 칸 수가 같아야 하고, 공백과 탭 문자를 섞어쓰면 안된다.


```python

```

#### 2.4.1 정수 계산하기
파이썬 IDLE를 실행하거나 콘솔(터미널, 명령 프롬프트)에서 파이썬을 실행한다.

사칙연산
``` python
1+1
2
```

나눗셈후 나머지를 구하는 %연산자
``` python
5 % 2
1
```

거듭제곱을 구하는 **연산자
``` python
2 ** 10
1024
```

#### 2.4.2 값을 정수로 만들기
int(숫자)
int(계산식)
int('문자열')
```python
int(3.3)
3
int(5 / 2)
2
int('10')
10
```

객체의 자료형 알아내기

type(값)
```python
type(10)
<class 'int'>
```

```python
# 타입Type : 숫자(정수형, 실수형), 문자(열), Boolean
numberInt = 100 #정수형 int타입
numberFloat = 1.234 # 실수형 float타입
varChar = 'A' # 문자형 str타입
varStr = 'Korea' # 문자열 Str타입
varBool = True # 부울bool 타입
```



#### 2.4.3 값을 실수로 만들기

float(숫자)
float(계산식)
float('문자열')
```python
>>> float(5)
5.0
>>> float(1 + 2)
3.0
>>> float('5.3')
5.3
```



## 3. 파이썬의 기본 입출력 함수
### 3.1 변수
변수Variable : 데이터를 저장할 수 있는 메모리 공간의 이름. 프로그래머가 쉽게 데이터에 액세스 할 수 있도록 특정 메모리에 이름을 붙인 것이며, 내용을 다른 값으로 갱신할 수 있다.  
```python
x = 10    # x:변수이름, =: 할당, 10: 값.   값 10을 x라는 변수에 할당함.
x
10
```  
#### 변수 여러개를 한번에 만들기
```python
 x, y, z = 10, 20, 30
 x
10
 y
20
 z
30
```

```python
 x = y = z = 10
 x
10
 y
10
 z
10
 
```




변수 이름은 원하는 대로 지으면 되지만 다음과 같은 규칙을 지켜야 한다.
- 영문 문자와 숫자를 사용할 수 있다.
- 대소문자를 구분한다.
- 문자부터 시작해야 하며 숫자부터 시작하면 안된다.
- _(밑줄 문자)로 시작할 수 있다.
- 특수 문자(+, -, *, /, $, @, &, % 등)는 사용할 수 없다.
- 파이썬의 키워드(if, for, while, and, or 등)는 사용할 수 없다.  
  
### 3.2 입력함수  
사용자가 입력한 값을 변수에 대입하고자 할 때 사용하는 함수로 input()함수가 있다.  
- input()의 사용
```python
number = input()
print(number)
```  
```python
>>> a = 10
>>> b = 20
>>> c = a + b
>>> c
30
```

  
- input 함수의 결과를 변수에 할당하기

변수 = input()
```python
>>> x = input()
Hello, world! (입력)
>>> x
'Hello, world!'
```


```python
number = input("숫자를 입력하세요: ")
print(number)
```  


```python
a = input('첫 번째 숫자를 입력하세요: ')
b = input('두 번째 숫자를 입력하세요: ')
 
print(a + b)
```


※ input()은 입력되는 모든 것을 문자열로 취급한다.   
따라서 숫자를 입력받아 연산하고자 한다면 정수형 등의 숫자 자료형으로 변환하여 사용하여야 한다.
```python
birthyear = input("생년을 입력하세요: ")
age = 2021 - int(birthyear)
print(age)
```



#### 3.2.1 입력값을 변수 두 개에 저장하기
input에서 split을 사용한 변수 여러 개에 저장해주면된다. (각 변수는 콤마로 구분해준다.)

변수1, 변수2 = input().split()  
변수1, 변수2 = input().split('기준문자열')  
변수1, 변수2 = input('문자열').split()  
변수1, 변수2 = input('문자열').split('기준문자열')

```python
a, b = input('문자열 두 개를 입력하세요: ').split()    # 입력받은 값을 공백을 기준으로 분리
 
print(a)
print(b)

문자열 두 개를 입력하세요: Hello Python (입력)
Hello
Python
```

```python
a, b = input('숫자 두 개를 입력하세요: ').split()    # 입력받은 값을 공백을 기준으로 분리
 
print(a + b)
숫자 두 개를 입력하세요: 10 20 (입력)
1020
```

```python
a, b = input('숫자 두 개를 입력하세요: ').split()    # 입력받은 값을 공백을 기준으로 분리
a = int(a)    # 변수를 정수로 변환한 뒤 다시 저장
b = int(b)    # 변수를 정수로 변환한 뒤 다시 저장
 
print(a + b)

숫자 두 개를 입력하세요: 10 20 (입력)
30
```

#### 3.2.2 map을 사용하여 정수로 변환하기

 map에 int와 input().split()을 넣으면 split의 결과를 모두 int로 변환한다.
 (실수로 변환할 때는 int 대신 float를 넣는다)

변수1, 변수2 = map(int, input().split())

변수1, 변수2 = map(int, input().split('기준문자열'))

변수1, 변수2 = map(int, input('문자열').split())

변수1, 변수2 = map(int, input('문자열').split('기준문자열'))

```python
a, b = map(int, input('숫자 두 개를 입력하세요: ').split())
 
print(a + b)

숫자 두 개를 입력하세요: 10 20 (입력)
30
```

```python
a, b = map(int, input('숫자 두 개를 입력하세요: ').split(',')) # 입력받은 값을 콤마를 기준으로 분리
 
print(a + b)

숫자 두 개를 입력하세요: 10,20 (입력)
30
```

6.6 연습문제

정수 세개를 입력받고 합계가 출력되게 하시오.
```python
_________________________________
print( a + b + c)

-10 20 30 (입력)
40
```

6.8 테스트
input으로 안내 문자열은 출력하지 않는 4자리의 숫자를 입력받아 평균을 구하는 프로그램을 만드시오.  
출력 결과 값은 정수로 출력되게 하시오.

```python
____________________
____________________

32 53 22 95
50
```

### 3.3 출력함수, print()함수
print에는 변수나 값 여러 개를 ,(콤마)로 구분하여 넣을 수 있다.

print(값1, 값2, 값3)
print(변수1, 변수2, 변수3)


- 기본출력, print("문자열") 
```python
print('Hello Python')
print("Hello Python")
print("""Hello Python""")
print('''Hello Python''')

print(1, 2, 3)
1 2 3
```
print에 변수나 값을 콤마로 구분해서 넣으면 각 값이 공백으로 한 줄로 출력된다.


- sep(separator) 옵션 사용
값사이에 공백이 아닌 다른 문자를 넣을때 사용

print(값1, 값2, sep='문자 또는 문자열')
print(변수1, 변수2, sep='문자 또는 문자열')

```python
print('P', 'y', 't', 'h', 'o', 'n')
print('P', 'y', 't', 'h', 'o', 'n', sep='')
print('2021', '03', '09', sep='-')
print('ebadak100', 'naver.com', sep='@')
```  

```python
a = input('메일 아이디를 입력하세요')
print(a,'naver.com',sep='@')
```

-줄바꿈(개행)

```python
print(1, 2, 3, sep='\n')
1
2
3
```
 - end 옵션 사용
출력을 할 때 끝 부분을 다음 라인과 연결시켜 주는 옵션  
```python
print('Welcom To')
print('Korea IT')
print('Academy')
print('====')
print('Welcom To', end=' ')
print('Korea IT', end=' ')
print('Academy')
```
- print("문자열" + "문자열")
- print("문자열","문자열")
- print("문자열" * 숫자)

- 포맷팅 출력 : % 기호 사용, 변수값 출력
%s : 문자열 타입의 변수 출력
```python
a = 'Hello'
b = 'Korea IT'
c = 'Academy'
print('%s, %s, %s'%(a,b,c))
```
%d : 정수형 타입의 변수 출력  
%f : 실수형 타입의 변수 출력  
%c : 문자형character   
%o : 8진수  
%x : 16진수  
%% : '%'문자  
- 고급 포매팅 출력  
format함수()와 {  }를 함께 사용, 서식을 지정할 수도 있다.
```python
a = 2021
b = 3
c = 9
print('안녕하세요. 오늘은 {}년 {}월 {}일입니다.'.format(a, b,c))
# {}안에 변수 인덱스 번호를 지정할 수 도 있다.

# 다음은 서식을 지정하는 예이다.
print("{0:d} {1:5d} {2:05d}".format(a,b,c))
#{}안의 0, 1, 2는 인덱스 번호를, d는 정수형으로, 정수형 앞의 수는 자리수를 자리수 앞의 0은 공백을 0으로 채운다.
```


print함수와 format()을 사용, 문장을 정렬할 수 있다.  
```python
print("{0:<10}".format("Hello"))  #왼쪽정렬
print("{0:>10}".format("Hello"))  #오른쪽정렬
print("{0:^10}".format("Hello"))  #가운데정렬
print("{0:*<10}".format("Hello"))  #왼쪽정렬 후 공백을 *로 채우기
```
- print()함수, 문장 정렬
```python
print('Hello'.center(10))
print('Hello'.rjust(10))
print('Hello'.ljust(10))
```

2000/10/27 11:43:59 와 같은 형식으로 오늘 날짜가 출력되게 하시오. 7.4  
```python
year,month,day = 
hour,minute,second = 

print(                          )
print(                          )
```

## 4. 자료형과 연산자
### 4.1 Data Type 자료형
데이터형(Data Type)은 자료형이라고도 하며, 컴퓨터에서 다루어지는 다양한 데이터 값들의 유형을 의미한다.  
파이썬에는 정수형, 실수형, 문자열형, 부울형 등이 있다.  
파이썬의 데이터타입은 type() 함수, 또는 isinstance() 함수를 이용하여 확인할 수 있다.  
다음의 코드를 각각 실행해 보자.
```python
num1 = 10
type(num1)

num2 = 1.234
type(num2)

str1 = 'korea it academy'
type(str1)

boolean1 = True
type(boolean1)  #변수의 타입을 확인

isinstance(num1, int) #특정 변수가 해당 타입에 속하는지 확인
      
```  
  
  
python은 진수변환과 관련한 함수도 제공한다.  
다음 코드를 실행해보자.  
```python
sel = int(input("입력 진수(16/10/8/2) : "))
num=input("값 입력 : ")
if sel == 16 :
    num10 = int(num, 16)  
elif sel == 10 :
    num10 = int(num, 10)
elif sel == 8 :
    num10 = int(num, 8)
else :
    num10 = int(num, 2)
    
print("16진수 : ", hex(num10))
print("10진수 : ", num10)
print("8진수 : ", oct(num10))
print("2진수 : ", bin(num10))
```


```python

```

### 4.2 연산자
- 산술연산자  
  +, -, \*, /(나누기), %(나머지), //(몫), **(거듭제곱)  
- 관계연산자
  >, <, >=, <=, ==, !=  
- 논리연산자
  and, or, not  
- 비트연산자  
  &, |, ^(배타적or, xor), ~, <<, >>
  
  ### 산술 연산 후 할당 연산자 사용하기
  산술 연산자 앞에 =(할당연산자)를 붙이면 연산 결과를 변수에 저장한다.
  단, 이때 미리 변수를 만들고 값을 할당해 두어야 한다.
  ```python
  a = 10
  a += 20 # a + 20 = 과 같은 문법
  a
  30
  ```
  
  8.4 합격여부 출력하기
표준 입력으로 4과목을 입력받아서 4과목 모두 80이상일때 합격, 한과목이라도 조건에 만족하지 않으면 불합격 처리하는소스
를 완성하시오. 합격이면 true 불합격이면 false  

``` python
  korean = 92
english = 47
mathematics = 86
science = 81
 
print(korean >= 50 and english >= 50 and mathematics >= 50 and science >= 50)                                                                       )
```





  
  
  
※ [파이썬 3.9 연산자](https://docs.python.org/ko/3/reference/lexical_analysis.html#operators)  
※[함수로서의 표준 연산자](https://docs.python.org/ko/3/library/operator.html)


```python 

```
