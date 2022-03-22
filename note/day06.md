# 함수
#### 학습목표 :  함수와 내장함수
> 1. 함수 선언 및 호출
> 2. 매개변수(기본값설정, 가변 매개변수)
> 3. 람다
> 4. 변수의 유효범위
> 5. 파이썬 내장함수

## 1. 함수선언과 호출
##### 함수의 정의   
특정 작업을 수행하기 위해 독립적으로 설계된 프로그램 코드의 집합

##### 함수를 사용하는 이유
프로그램 내에서 중복적인 코드의 작성을 최소화하고, 코드의 재사용성을 높여줄 수 있다.

### 함수 선언
파이썬에서 함수는 다음과 같이 선언한다.
```python
def 함수명(매개변수1, ...) :
    실행코드1
    실행코드2
    ...
```
함수명은 함수를 호출할 때 사용할 이름이며, 매개변수(parameter)는 함수 호출시 전달되는 인수의 값을 함수 내부에서 사용할 수 있도록 저장할 변수의 이름이다.
### 함수 호출
위와 같이 선언된 함수는 다음과 같은 방식으로 호출할 수 있다.
```python
함수명(인수, ...)
```
인수(arguments)는 함수를 호출할 때 함수에서 사용할 데이터를 전달해 주는 역할을 한다.


### 함수 사용의 예
```python
def hello():
    print('hello! world!')
```
hello()

```python
def greet(name):
    print("Hello, " + name +". Good Morning")
    
greet('철수야')
greet('영수야')
```

```python

def personalInfo(age, name, address):
    print('이름 : ', name)
    print('나이 : ', age)
    print('주소 : ', address)
    
personalInfo(age=19, name='홍길동', address='청주시 상당구')

```



```python
def add(a,b):
    print(a + b)

```
add(10,20) - 인수(argument)


```python
def sumFunction(num1, num2):
    print("{0:d} + {1:d} = {2:d}".format(num1, num2, num1+num2))
          
a = int(input("숫자 a를 입력해주세요 : "))
b = int(input("숫자 b를 입력해주세요 : "))

sumFunction(a,b)
          
```
### 값을 반환(return)하는 함수
전달받은 인수를 함수 내부에서 처리한 결과를 return문을 사용하여 반환할 수 있다. 또한 return문은 함수의 종료를 의미하며, 함수를 호출한 곳으로 해당 결과값을 반환한다.
```python
def 함수명(매개변수1,...):
    실행코드1
    실행코드2
    ...
    return 결과값

변수명 = 함수명(인수1,...)
```
```python
def add(a,b):
    return a + b
```
x = add(10,20)

```python

def functionAdd(num1, num2):
    return num1+num2, num1*num2
r1, r2 = functionAdd(10,20)
print(r1)
print(r2)

```


## 함수 독스트링 사용하기
함수의 : 바로 다음줄에 """ """(큰따옴표 세개)로 문자열을 입력하면 설명을 넣을수 있다.
```python
def add(a,b):
    """이 함수는 a와 b를 더한 뒤 결과를 반환하는 함수입니다."""
    return a + b
 
x = add(10, 20)       # 함수를 호출해도 독스트링은 출력되지 않음
print(x)
 
```
print(add.__doc__)    # 함수의 __doc__로 독스트링 출력



## 2. 매개변수
### 매개변수의 기본값 설정과 인수 생략
함수를 선언할 때 미리 매개변수의 기본값을 설정하면, 함수 호출시 전달받지 못한 인수에 대해서는 설정해 놓은 기본값으로 자동 초기화할 수 있다.
```python
def total(a, b=2, c=3):
    print(a + b + c)    

total(10)
total(10, 20)
total(10, 20, 30)
```
### 가변 매개변수의 사용
매개 변수의 갯수가 정해져 있지 않은 것을 가변 매개변수라 한다. 가변 매개변수를 사용하고자 할 때는 매개변수명 앞에 \*를 추가하여 선언한다.
```python
def 함수명(*매개변수명):
    실행코드...
```
다음 예제는 가변 매개변수를 사용하여 더하고자 하는 숫자를 임의로 입력할 수 있다.
```python
def varSum(*numbers):
    print(numbers)
    sum = 0
    for number in numbers:
        sum += number
    return sum

print(varSum(1))
print(varSum(1,2))
print(varSum(1,2,3))
```
### 여러 개의 결과값 반환
파이썬에서는 두 개 이상의 결과값을 반환할 수 있다.
```python
def calc(a, b):
    add = a + b
    sub = a - b
    return add, sub    

add, sub = calc(10, 1)

print(add)
print(sub)
```

함수 호출

```python
def mul(a, b):
    c = a * b
    return c
 
def add(a, b):
    c = a + b
    print(c)
    d = mul(a, b)
    print(d)
 
x = 10
y = 20
add(x, y)
```
## 29.3 퀴즈
숫자 두개를 입력으로 받아서 사칙연산이 출력되게 만드시오.
``` python
x, y = map(int, input().split())

________________
________________

a, s, m, d = calc(x, y)
print('덧셈: {0}, 뺄셈: {1}, 곱셈: {2}, 나눗셈: {3}'.format(a, s, m, d))
```
def calc(a, b):
	return(a+b, a-b, a*b, a/b)


## 3. 람다lambda
람다란 간단한 함수의 선언과 호출을 하나의 식으로 간략하게 표현한 것이다. 람다는 일반함수와 달리 이름을 가지지 않으며, 한 번밖에 사용할 수 없는 차이점을 갖는다.
```python
lambda 매개변수리스트 : 매개변수이용표현식
```
10에 숫자를 더해서 반환하는 함수
```python
def plus_ten(x):
	return x + 10
	
```
plus_ten(1)

람다표현식
```python
plus_ten = lamda x: x + 10
```
plus_ten(1)
```python
(lambda x : x+10)(1)
```

두 수를 입력받아 반환하는 함수를 람다식으로 표현식 자체 호출
```python
def add(a, b):
    return a+b
print(add(1,2))

print((lambda a, b:a+b)(1,2))
```

람다 표현식 인수로 사용하기
```pytho
def plus_ten(x):
	return x + 10
	
list(map(plus_ten, [1,2,3]))
```

람다표현식
```python
list(map(lambda x: x + 10, [1,2,3]))
```


## 4. 변수의 범위
파이썬에서 변수는 유효범위에 따라 다음과 같이 구분한다.  
#### 지역변수(local variable)  
함수 내에서 선언한 변수로 일반적으로 함수 내에서만 사용가능하다.
```python
def func():
    local_var = "지역 변수"
    print(local_var)    

func()
#print(local_var)
```
```python
x=10
def foo():
    x=20
    print(x)
foo()
print(x)
```


#### 전역변수(global variable) 
```python
def func():
    global global_var
    local_var = "지역 변수"
    print(local_var)
    print(global_var)    

global_var = "전역 변수"
func()
print(global_var)
```


```python

```

## 5. 파이썬 내장함수
파이썬 인터프리터에는 항상 사용할 수 있는 많은 함수와 타입이 내장되어 있다.   
내장함수의 상세한 내용은 [파이썬 문서 중 내장함수](https://docs.python.org/ko/3/library/functions.html) 부분을 확인해보자.


## 6. 클로저 사용하기 - 지켜보기
클러저를 사용하면 프로그램의 흐름을 변수에 저장할수 있다.  
즉, 클로저는 지역 변수와 코드를 묶어서 사용하고 싶을 때 활용한다.  
또한, 클로저에 속한 지역 변수는 바깥에서 직접 접근할수 없으므로 데이터를 숨기고 싶을 때 활용한다.

### 함수를 클로저 형태로 만드는 방법  
함수 바깥쪽에 있는 지역 변수 a,b를 사용하여 a * X = b  를 계산하는 함수 mul_add 를 만든뒤 함수 mul_add 자체를 반환한다.

```python
def calc():
    a = 3
    b = 5                 # 지역변수 a, b를 만들고 3, 5를 저장
    def mul_add(x):
        return a * x + b # 함수 바깥쪽에 있는 지역 변수 a, b를 사용하여 계산
    return mul_add       # mul_add함수를 반환 
c = calc()               # calc를 호출한뒤 반환값을 C에 저장한다. calc에서 mul_add를 반환했을으므로 c에는 함수 mul_add가 들어간다.
print(c(1), c(2), c(3),c(4),c(5)) # 8 11 14 17 20
```
클러저의 지역 변수를 변경하고 싶다면 nonlocal을 사용한다.  
다음은 a * X + b의 결과를 함수 calc의 지역변수 total에 누적한다.
```python
def calc():
    a = 3
    b = 5
    total = 0
    def mul_add(x):
        nonlocal total     # 현재 함수의 바깥쪽에 있는 지역 변수 사용
        total = total + a * x + b
        print(total)
    return mul_add
 
c = calc()
c(1)
c(2)
c(3)
```
