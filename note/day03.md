# 제어문의 이해와 활용
#### 학습목표 :  제어문의 이해와 활용
> 1. 조건제어문(if / if~ else / if elif... else)
> 2. 반복제어문(for)
> 3. 반복제어문(while)

파이썬 프로그램에서는 if구문과 for, while 구문을 제공한다.  
다른 프로그래밍 언어와 비슷한 점도 있으나 뚜렷한 차이도 있으니 이를 구별하여 기억하도록 한다.

## 1. if 조건 제어문
### if문
가장 단순한 형태의 if문은 참일 때는 실행하고, 거짓일 때는 아무것도 실행하지 않는다.    
```phthon
if 조건식:      # if를 쓰고 조건식 삽입후 ':' 입력  
    명령        # 들여쓰기 후, 명령입력   
```

```python
x = 10
if x==10:
    print('10입니다.') # 들여쓰기에 주의
```
```python
x = 10 # x에 5할당후 확인
 
if x == 10:
     print('x에 들어있는 숫자는')
print ('10입니다.')
```
```python
a = int(input("임의 숫자 입력 : "))
if a < 100:
    print("100보다 작은 수")
print("프로그램 종료")
```
x의 값이 20이 아닐때 pass 가 출력되게 하세요
```python
x = 10
if_______________________
    print('pass')
```

x != 20

### 연산자  
비교연산자  
x < y   ~보다 작음
x > y   ~보다 큼  
x == y  ~와 같음  
x != y  같음  
x >= y  크거나 같음  
x <= y  작거나 같음  

논리연산자  
and     두 값이 모두 참일 경우 True, 아니면 False  
or      두 값중 하나만 참일 경우 True, 모두 거짓일 경우 False  
not     값을 역으로 반환하여 판단  



## 13.6 퀴즈~
표준 입력으로 가격(정수)과 쿠폰이름이 각 줄에 입력된다.  
sale3000 쿠폰은 3,000원 sale5000쿠폰은 5,000원을 할인한다.  
할인된 가격을 출력하는 프로그램을 만드시오.

```python
a = int(input())
b = str(input())
if 조건:
    값1
if 조건:
    값2
print(a)
```




### if~else문
참일 때 실행할 문장과 거짓일 때 실행할 문장을 다르게 할 때 사용.
```python
a = int(input("임의 숫자 입력 : "))
if a < 100:
    print("100보다 작은 수")
else :
    print("100보다 큰 수")   
print("프로그램 종료")
```

```python
x = 10
y = 20
 
if x == 10 and y == 20:     # x가 10이면서 y가 20일 때
    print('참')
else:
    print('거짓')
```
필기 시험점수가 80점 이상고, 면접 테스트를 통과 하면 합격, 아니면 불합격을 출력하게 하시오.

```python
written_test = 75
interview_test = True
 
①   written_test           interview_test        :
    print('합격')
else:
    print('불합격')
```
if written_test >= 80 and interview_test == True:

## 14.7 퀴즈~

표준 입력으로 4과목의 점수를 입력받아 평균 점수가 80점 이상일때 합격 아니면 불합격을 출력
점수가 0점에서 100점까지만 입력으로 받으며, 범위오류일때 '잘못된 점수'를 출력하시오.
```python
a,b,c,d = map(int,input().split())






```




### if~elif문   
동일한 형태의 조건 비교를 위한 값을 다르게 여러 차례 비교할 때
``` python
x = 20
if x == 10:
    print('10입니다.')
elif x == 20:
    print('20입니다.')
    
```

음료수 자판 만들기
```python
button = int(input())
 
if button == 1:
    print('콜라')
elif button == 2:
    print('사이다')
elif button == 3:
    print('환타')
else:
    print('제공하지 않는 메뉴')
```
```python
print("당신의 태어난 연도를 입력하세요.")
birth_year = input()
age = 2022-int(birth_year)+1

if age <=26 and age >= 20:
    print('대학생')
elif age <20 and age >=17:
    print('고등학생')
elif age <17 and age >=14:
    print('중학생')
elif age <14 and age >=8:
    print('초등학생')
else:
    print('학생이 아닙니다.')
```

### 중첩 if문  
조건을 검사하는 과정이 2번 이상일 때.     
예를 들어 성별 연령대별 학생의 수를 카운트 한다면 다음과 같이 코딩할 수 있을 것이다.
```python
gender = input("성별을 입력하세요(M:남자/F:여자) : ")
age = int(input("나이를 입력하세요. : "))
if gender == 'M' or gender == 'm' :
    if age >= 40 :
        print("40대 이상 남자")
    elif age >= 30 : 
        print("30대 남자")
    elif age >= 20 :
        print("20대 남자")
    else:
        print("10대 이하 남자")
else :
    if age >= 40 :
        print("40대 이상 여자")
    elif age >= 30 : 
        print("30대 여자")
    elif age >= 20 :
        print("20대 여자")
    else:
        print("10대 이하 여자")    
              
```

## 15.3 퀴즈~
표준 입력으로 만나이를 입력 (7이상 입력), 나이에 맞게 요금을 차감한뒤 잔액이 출력되게 하시오.  
현재 교통카드에는 10,000이 들어 있음  
어린이(초등학생, 만 7세 이상 12세 이하): 650원  
청소년(중∙고등학생, 만 13세 이상 18세 이하): 1,050원  
어른(일반, 만 19세 이상): 1,250원  

```python
age = int(input('탑승자의 나이를 입력하세요 :'))
card = 9000    # 교통카드 잔액

________________
________________
________________
________________
________________
________________

print(card)
```



```python

```

### 삼항 연산자를 사용한 if문  
```python
score = 55
result = ''
if score >= 60:
    result = '합격'
else :
    result = '불합격'
print(result)
```
다음과 같이 삼항 연산자를 사용해 한 줄로 줄일 수 있다.
```python
score = 50
result = ''
result = '합격' if score >= 60 else '불합격'
print(result)
```


```python

```

## 2 for 반복제어문
### for문의 기본 형식
```python
for i in range(100):
    print('hi',i)
    
```

```python
for 변수 in range(시작값, 끝값+1, 증가값):
    반복문
```
range()함수는 지정된 범위의 값을 반환. range(0,3,1)은 0에서 시작해 2까지 1씩 증가하는 값을 반환한다. 세번재 증가값은 생략하면 1로 인식한다.
```python
   for i in range(0,3,1):
        print("for문을 공부중입니다.")
```
range(0,3,1)은 [0,1,2]와 같다. 


```python
# 1부터 10까지의 합계를 구하는 프로그램을 작성하세요.
sum = 0
for number in range(1, 11):
    sum += number
print("1부터 10까지의 합 : %d" % sum)
```
#### 구구단 한단을 출력
```python
n=int(input())

for i in range(1,10):
  print(n,'*',i,'=',n*i)  
  # print('%d * %d = %d'%(n,i,n*i))

```


### 중첩 for문  
```python
for i in range(0,3,1):
    for k in range(0,2,1):
        print("파이썬 중첩(i값 : %d, k값:%d)"%(i,k))
   
```

```python
for i in range(5):
    for j in range(5):
        print('*', end='')
    print()
```
계단식 별 출력
```python
for i in range(5):        # 0부터 4까지 5번 반복. 세로 방향
    for j in range(5):    # 0부터 4까지 5번 반복. 가로 방향
        if j <= i:                # 세로 방향 변수 i만큼
            print('*', end='')    # 별 출력. end에 ''를 지정하여 줄바꿈을 하지 않음
    print()    # 가로 방향으로 별을 다 그린 뒤 다음 줄로 넘어감
               # (print는 출력 후 기본적으로 다음 줄로 넘어감)
```
대각선 별 출력
```python
for i in range(5):        # 0부터 4까지 5번 반복. 세로 방향
    for j in range(5):    # 0부터 4까지 5번 반복. 가로 방향
        if j == i:                # 세로 방향 변수와 같을 때
            print('*', end='')    # 별 출력. end에 ''를 지정하여 줄바꿈을 하지 않음
        else:                     # 세로 방향 변수와 다를 때
            print(' ', end='')    # 공백 출력. end에 ''를 지정하여 줄바꿈을 하지 않음
    print()    # 가로 방향으로 별을 다 그린 뒤 다음 줄로 넘어감
               # (print는 출력 후 기본적으로 다음 줄로 넘어감)
```
        실행 결과

다른 방법
```python
x=int(input('줄수를 입력하세요'))
for i in range(1, x+1):
    for j in range(i):
        print("*", end="")
    print()

```




## 구구단 출력하기
```python
# 전체 구구단이 출력되게 

```




## 3. while 반복 제어문
### while문의 기본형식
```python
변수 = 시작값
while 변수 < 끝값 :
    이 부분을 반복
    변수 = 변수 + 증가값
```
```python
i = 0                     # 초기식
while i < 100:            # while 조건식
     print('Hello, world!')    # 반복할 코드
     i += 1                    # 변화식
```

```python
count = int(input('반복할 횟수를 입력하세요: '))
 
while count > 0:     # count가 0보다 클 때 반복
    print('Hello, world!', count)
    count -= 1       # count를 1씩 감소시킴

```

### 무한 루프 while문
```python
while True:
    반복할문장
```

### for문과 while문 상호 변환 가능
```python
# for문
for i in range(0,5):    # 반복 실행 횟수를 명확히 알때
    print(i)
    
# while
i = 0                   # 반복 실행 횟수가 명확하지 않을때
while i < 5:
    print(i)
    i = i + 1
```

### break문 
반복문에서 break문을 만나면 무조건 반복문을 벗어난다.
```python
i = 0
while True:    # 무한 루프
    print(i)
    i += 1          # i를 1씩 증가시킴
    if i == 100:    # i가 100일 때
        break       # 반복문을 끝냄. while의 제어흐름을 벗어남
 
```


```python
for i in range(1,100):
    print("for문을 %d번 실행했습니다." % i)
    break
```
```python
for i in range(10000):    # 0부터 9999까지 반복
    print(i)
    if i == 100:    # i가 100일 때
        break       # 반복문을 끝냄. for의 제어흐름을 벗어남
        
```

### continue문
continue를 만나면 블록의 남은 부분을 무조건 건너뛰고 반복문의 처음으로 다시 돌아간다.  
즉, 반복문을 처음부터 다시 수행한다.
```python
for i in range(100):       # 0부터 99까지 증가하면서 100번 반복
    if i % 2 == 0:         # i를 2로 나누었을 때 나머지가 0면 짝수
        continue           # 아래 코드를 실행하지 않고 건너뜀
    print(i)                # 홀수 값만 출력
    
```

입력 횟수만큼 반복
```python
count = int(input('반복할 횟수를 입력하세요: '))
 
i = 0
while True:    # 무한 루프
    print(i)
    i += 1
    if i == count:    # i가 입력받은 값과 같을 때
        break         # 반복문을 끝냄
        
```
3의 배수 제외
```python
sum, i = 0, 0
for i in range(1,101):
    if i % 3 == 0:
        continue
    sum += i
print("1~100의 합계(3의 배수 제외) : %d" % sum)
```

0~ 100중  
3으로 끝나는 숫자만 출력하기

```python
i = 0
while True:
    ①              
                   
                   
    ②              
                   
    print(i, end=' ')
    i += 1
```
①
if i % 10 != 3:  
    i += 1  
    continue  
②
if i > 73:  
    break  
    
### else문
```phthon
for i in range(1,10):
    print(i)
else:
    print("프로그램이 종료되었습니다.")
    
```
    
## 18.5 퀴즈   
표준 입력으로 정수 두개를 입력  
첫번째 : 1 ~ 200 (두번째 입력값보다 항상 작음)  
두번째 : 10 ~ 200   
첫번째 정수와 두번째 정수 사이의 숫자중 3으로 끝나지 않는 숫자가 출력되게 하시오.  
```python
start, stop = map(int, input().split())
 
i = start
 
while True:
_____________________
_____________________
_____________________
_____________________
_____________________
    print(i, end=' ')
    i += 1
```


