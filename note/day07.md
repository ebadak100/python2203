
# 객체지향 프로그래밍
#### 학습목표 :  객체지향 프로그래밍
> 1. 클래스의 선언
> 2. 생성자
> 3. 인스턴스변수와 클래스 변수
> 4. 클래스의 상속
> 5. 객체지향 프로그래밍의 심화내용

집, 자동차, 나무 버튼등 특정한 개념이나 모양으로 존해하는 것을 객체(object)라고 함
프로그래밍으로 객체를 만들 때 사용하는 것이 클래스이다.

## 1. 클래스 (예> 게임의 직업들(기사, 마법사, 궁수 등)
클래스는 객체지향을 공부할 때 가장 먼저 이해해야 할 개념 중 하나이다.  
 - 사물뿐 아니라 컴퓨터 안에서만 쓰이는 스크롤바, 버튼, 체크 박스등도 클래스이다.  
 - 특정한 개념이나 모양으로 존재하는 것을 객체(object)라고 부른다.  
 - 이처럼 프로그래밍으로 객체를 만들때 사용하는것이 클래스이다.  
클래스는 '현실 세계의 사물을 컴퓨터 안에서 구현하려고 고안된 개념'으로 사물의 정적 특성을 표현하는 attribute(속성)과 동적 특성을 표현하는 method(메서드)로 구성할 수 있다.  
 - 게임에 체력, 마나, 공격력 등의 데이터를 클래스의 속성(attribute)라 한다.  
 - 베기, 찌르기 등의 기능을 메서드(method)라고 한다.  

```python
                클래스
        속성                       메서드
  체력, 마나, 물리공격력...       베기, 지르기...
  
```
 
이렇게 프로그래밍한 방법을 객체지향(object oriented)프로그래밍이라고 한다.
객체지향 프로그래밍은 객체를 만들고, 객체를 조합해서 문제를 해결한다.

### 클래스와 메서드 만들기
클래스는 class에 클래스 이름을 지정하고 :(콜론)을 붙인 뒤 다음줄 부터 def로 메서드를 작성한다.  
메서드는 클래스 안에 들어 있는 함수를 뜻한다.

보통 클래스 이름은 대문자로 시작한다. 
메서드의 첫 번째 매개 변수는 반드시 self를 지정해야 한다.
self는 인스턴스 자기 자신을 의미한다.

```python
  class 클래스명:
        # 클래스 코드구현
        def 메서드(self):
            코드
```
```python
class Person:
    def greeting(self):
        print('hello')
        
james=Person() # 인스턴스 = 클래스()
```
```python
james.greeting() # 메서드 호출  

```
```Python

# int, list, dict 등도 클래스이다.
a=int(10)
b=list(range(10))
c = dict(x=10, y=20)
```
#### 빈 클래스 만들기
```python
class Person:
    pass
```

### 메서드 안에서 메서드 호출하기  
메서드 안에서 메서드를 호출할때는 self.메서드() 형식으로 호출한다.    
self없이 메서드 이름만 사용하면 클래스 바깥쪽에서 호출한다.  

```python
class Person:
    def greeting(self):
        print('Hello')
 
    def hello(self):
        self.greeting()    # self.메서드() 형식으로 클래스 안의 메서드를 호출
 
james = Person()
james.hello()    # Hello
```

### 인스턴스 속성 사용하기  
속성을 만들때는 __init__ 메서드 안에서 self.속성에 값을 할당한다.

```python
class 클래스 이름:
    def __init__(self):
        self.속성 = 값
```

```python
class Person:
    def __init__(self):       # self에 Person()이 들어간다.     # 파이썬이 자동호출하는 스페셜메서드, 매직 메서드
        self.hello = '안녕하세요.'
 
    def greeting(self):      # self에 james.greeting()이 들어간다.
        print(self.hello)
 
james = Person()
james.greeting()    # 안녕하세요.
```
__init__ 메서드는 james=Person()처럼 클래스에()를 붙여서 인스턴서를 만들때 호출되는 특별한 메서드이다.  
__init__(initialize) 인스턴스(객체)를 초기화 한다.  


### 인스턴스를 만들때 값 받기

다음과 같이 __Init__ 메서드에 self 다음에 값을 받을 매개변수를 지정한다.   
매개변수를 self.속성에 넣어준다.
```python
class 클래스이름:
    def __init__(self, 매개변수1, 매개변수2):
        self.속성1 = 매개변수1
        self.속성2 = 매개변수2
 ```
 ```python

class Person:
    def __init__(self, name, age, address): # Person 클래스에(hello, name, age, address) 속성이 존재
        self.hello = '안녕하세요.'
        self.name = name
        self.age = age
        self.address = address
 
    def greeting(self):
        print('{0} 저는 {1}입니다.'.format(self.hello, self.name))
 
maria = Person('마리아', 20, '서울시 서초구 반포동')
maria.greeting()    # 안녕하세요. 저는 마리아입니다.
 
print('이름:', maria.name)       # 마리아
print('나이:', maria.age)        # 20
print('주소:', maria.address)    # 서울시 서초구 반포동

```
### 비공개 속성 사용하기  

- 클래스 바깥에서는 접근할 수 없고 클래스 안에서만 사용할수 있는 비공개 속성(private attribute)  
- __(밑줄 두 개)로 시작해야 한다.
- 단, __속성__처러 밑줄 두 개가 양 옆에 왔을때는 비공개 속성이 아님

```python
class 클래스이름:
    def __init__(self, 매개변수)
        self.__속성 = 값
```

```python
class Person:
    def __init__(self, name, age, address, wallet):
        self.name = name
        self.age = age
        self.address = address
        self.__wallet = wallet    # 변수 앞에 __를 붙여서 비공개 속성으로 만듦
 
maria = Person('마리아', 20, '서울시 서초구 반포동', 10000)
maria.__wallet -= 10000    # 클래스 바깥에서 비공개 속성에 접근하면 에러가 발생함

```

```python
class Person:
    def __init__(self, name, age, address, wallet):
        self.name = name
        self.age = age
        self.address = address
        self.__wallet = wallet    # 변수 앞에 __를 붙여서 비공개 속성으로 만듦
 
    def pay(self, amount):
        self.__wallet -= amount   # 비공개 속성은 클래스 안의 메서드에서만 접근할 수 있음
        print('이제 {0}원 남았네요.'.format(self.__wallet))
 
maria = Person('마리아', 20, '서울시 서초구 반포동', 10000)
maria.pay(3000)

```

- 비공개 속성은 클래스 바깥으로 드러내고 싶지 않은 값에 사용



### 클래스 속성 사용하기

사람 클래스에 클래스 속성으로 가방 속성을 사용  

```python
class 클래스이름:
    속성 = 값
```


```python

class Person: # 클래스
    bag = [] # 속성 <-(james.put_bag('책'), maria.put_bag('열쇠')
 
    def put_bag(self, stuff): # 메서드
        self.bag.append(stuff)
 
james = Person()
james.put_bag('책')
 
maria = Person()
maria.put_bag('열쇠')
 
print(james.bag)
print(maria.bag)
```

- 클래스 속성은 클래스에 속해 있으며 모든 인스턴스에서 공유한다.  

```python

class Person:
    bag = []
 
    def put_bag(self, stuff):
        self.bag.append(stuff)  # self라는 인스턴스를 이용 접근
-----------------------------
class Person:
    bag = []
 
    def put_bag(self, stuff):
        Person.bag.append(stuff)    # 클래스 이름으로 클래스 속성에 접근
        
```
        


### 인스턴스 속성으로 사용하기 - 공유하지 않기

```python
class Person:
    def __init__(self):
        self.bag = []
 
    def put_bag(self, stuff):
        self.bag.append(stuff)
 
james = Person()
james.put_bag('책')
 
maria = Person()
maria.put_bag('열쇠')
 
print(james.bag)
print(maria.bag)

```

#### 클래스 속성과 인스턴스 속성의 차이점

 - 클래스속성 : 모든 인스턴스가 공유. 인스턴스 전체가 사용해야 하는 값을 저장할 때 사용 (길드 창고)  
 - 인스턴스 속성 : 인스턴스별로 독립되어 있음. 각 인스턴스가 값을 따로 저장해야 할 때 사용 (개인 창고)  

### 클래스 상속하기  
- 물려받은 기능을 유지한채로 다른 기능을 추가할 때 사용  
  - 부모 클래스(parent class), 슈퍼 클래스(super class)  
- 물려주는 클래스를 기반 클래스(base class), 새롭게 만드는 클래스를 파생 클래스(derived class)  
  - 자식클래스(child class), 서브클래스(sub class)  
- 상속은 기존 기능을 재사용할 수 있어서 효율적이다.

#### 사람 클래스로 학생 클래스 만들기
class 기반클래스이름:
    코드
class 파생클래스이름(기반클래스이름):
    코드
    
```python
class Person:
    def greeting(self):
        print('안녕하세요.')
 
class Student(Person): # 기반클래스인 Person 클래스 삽입
    def study(self):
        print('공부하기')
 
james = Student()
james.greeting()    # 안녕하세요.: 기반 클래스 Person의 메서드 호출
james.study()       # 공부하기: 파생 클래스 Student에 추가한 study 메서드
```

### 메서드 오버라이딩 사용하기  
#### 오버라이딩 
 - 기반 클래스의 메서드를 무시하고 새로운 메서드를 만듬
 - 프로그램상 기능이 같은메서드 이름으로 계속 사용되어야 할 때 메서드 오버라이딩을 활용한다.
 

```python
class Person:
    def greeting(self):
        print('안녕하세요.')
 
class Student(Person):
    def greeting(self):  # Person 클래스의 greeting 메서드를 무시하고 Student 클래스에 새로운 greeting 메서드를 만듬
        print('안녕하세요. 저는 한국IT학원 학생입니다.')
 
james = Student()
james.greeting()

```

오버라이딩 후
```python
class Person:
    def greeting(self):
        print('안녕하세요.')
 
class Student(Person):
    def greeting(self):
        super().greeting()    # 기반 클래스의 메서드 호출하여 중복을 줄임
        print('저는 파이썬 코딩 도장 학생입니다.')
 
james = Student()
james.greeting()

```

### 다중 상속 사용하기

- 여러 기반 클래스로부터 상속을 받아서 파생 클래스를 만듬

class 기반클래스이름1:
    코드
 
class 기반클래스이름2:
    코드
 
class 파생클래스이름(기반클래스이름1, 기반클래스이름2):
    코드
    
    
```python
class Person:
    def greeting(self):
        print('안녕하세요.')
 
class University:
    def manage_credit(self):
        print('학점 관리')
 
class Undergraduate(Person, University):
    def study(self):
        print('공부하기')
 
james = Undergraduate()
james.greeting()         # 안녕하세요.: 기반 클래스 Person의 메서드 호출
james.manage_credit()    # 학점 관리: 기반 클래스 University의 메서드 호출
james.study()            # 공부하기: 파생 클래스 Undergraduate에 추가한 study 메서드
```


##  추가 반복 - 간단하게 자동차 클래스를 정의해 보자.  

## 클래스

```python
class Car:
    # 자동차의 필드
    색상 = ""
    현재속도 = 0
    # 또는 __init__ 메서드 안에서 속성을 만들고 사용한다. 이때는 인스턴스 속성이라 한다.
    # __init__(self):
    #     self.속성 = 값
    
    # 자동차의 메서드
    def upSpeed(증가할속도):
        # 현재 속도에 증가할 속도만큼 속도를 올리는 코드
    def downSpeed(감소할속도):
        # 현재 속도에 감소할 속도만큼 속도를 내리는 코드
    def showInfo(self):
        # 현재 자동차의 정보와 속도를 출력한다.
```


## 위 코드를 python코드로 구현해보자.  

### 1단계 클래스 선언  
class 클래스명:
    # 필드선언
    # 메서드 선언

```python
class Car :
    color = ""
    speed = 0
    
    def upSpeed(self, value):
        self.speed += value # 3행의 speed를 의미
        
    def downSpeed(self, value):
        self.speed -= value
        
```



### 2단계 인스턴스 생성
인스턴스 - 클래스명()
```python
```  
  
자동차의 인스턴스를 생성하는 코드는 다음과 같다.
```python
Car1 = Car()
Car2 = Car()
Car3 = Car()
```


### 3단계 필드나 메서드 사용
인스턴스.필드명 = 값  
인스턴스.메서드()  

인스턴스가 생성되면 각 자동차는 독립적이다. 각 인스턴스에는 별도의 필드가 존재하며, 각각 별도의 값을 가질 수 있다. 
```python
Car1.color = "빨강"
Car1.speed = 0
Car2.color = "파랑"
Car2.speed = 0
Car3.color = "노랑"
Car3.color = 0
```

#### 메서드의 호출
```python
Car1.upSpeed(30)
Car2.downSpeed(60)

```  

#### 클래스 작동

```python
## 클래스 선언 부분 ##
class Car:
    color = ""
    speed = 0
    
    def upSpeed(self,value):
        self.speed += value
       
    def downSpeed(self, value):
        self.speed -= value
        
## 메인 코드 부분 ##
Car1 = Car()              # 인스턴스 생성
Car1.color = "빨강"       # 필드 사용 # 인스턴스.필드명 = 값
Car1.speed = 0             

Car2 = Car()
Car2.color = "파랑"
Car2.speed = 0

Car3 = Car()
Car3.color = "노랑"
Car3.speed = 0

Car1.upSpeed(30)              # 메서드 사용 # 인스턴스.메서드() 
print("자동차1의 색상은 %s이며, 현재 속도는 %dkm입니다." %(Car1.color, Car1.speed))

Car2.upSpeed(60)
print("자동차2의 색상은 %s이며, 현재 속도는 %dkm입니다." %(Car2.color, Car2.speed))

Car3.upSpeed(0)
print("자동차3의 색상은 %s이며, 현재 속도는 %dkm입니다." %(Car3.color, Car3.speed))
     

```

#### 퀴즈
upSpeed를 수정해서 속도가 150이 넘으면 최대 150으로 고정되게 작성해 보시오.
```python
def upSpeed(self,value)
    self.speed =+ value
    ___________________
    ___________________
    
   

```





## 2. 생성자

### 기본 생성자
- 생성자는 인스턴스를 생성하면 무조건 호출되는 메서드이다. 
- 인스턴스를 생성하면서 필드값을 초기화 시키는 함수를 생성자라고 한다.
ex)
```python
Car1 = Car()           # Car1 인스턴스 생성
Car1.color = "빨강"    # 색상을 빨강으로 초기화
Car1.speed = 0         # 속도를 0으로 초기화


```

- 생성자는 __init__() 라는 이름을 가진다. 생성자의 기본 형태는 다음과 같다.
```python
   def __init__(self):
        # 이부분에 초기화 코드 입력
```

### 매개변수가 있는 생성자
```python
# 클래스의 선언
class Car :
    color =""
    speed = 0
    
    def __init__(self, value1, value2) :
        self.color = value1
        self.speed = value2
        
# 메인코드 부분
myCar = Car("빨강", 30)
```


```python
## 클래스 선언 부분 ##
class Car :
    name = "" 
    speed = 0 
    
    def __init__(self, name, speed):
        self.name = name
        self.speed = speed
        
    def getName(self):
        return self.name
        
    def getSpeed(self):
        return self.speed
        
## 변수 선언 부분 ##
car1, car2 = None, None

## 메인 코드 부분 ##
car1 = Car("아우디",0)
car2 = Car("벤츠",30)

print("%s의 현재 속도는 %d입니다." % (car1.getName(), car1.getSpeed()))
print("%s의 현재 속도는 %d입니다." % (car2.getName(), car2.getSpeed()))
```

### 3. 인스턴스 변수와 클래스 변수
### 인스턴스 변수
인스턴스를 생성해야 비로소 사용할 수 있는 변수

### 클래스 변수  
클래스 안에 공간이 할당된 변수. 인스턴스에 별도의 공간을 할당하지 않고, 여러 인스턴스가 클래스 변수의 공간을 함게 사용


```python
## 클래스 선언 부분 ##
class Car :
    color = "" # 인스턴스 변수
    speed = 0 # 인스턴스 변수
    count = 0 # 클래스 변수
    
    def __init__(self):
        self.speed = 0
        Car.count += 1
         
## 변수 선언 부분 ##
myCar1, myCar2 = None, None

## 메인코드 부분 ##
myCar1 = Car()
myCar1.speed = 30
print("자동차1의 현재 속도는 %dkm, 생산된 자동차는 총 %d대입니다." % (myCar1.speed, myCar1.count))

myCar2 = Car()
myCar2.speed=200
print("자동차2의 현재 속도는 %dkm, 생산된 자동차는 총 %d대입니다." % (myCar2.speed, myCar2.count))
    
   
```

### 4. 클래스의 상속
### 상속의 개념
기존 클래스에 있는 필드와 메서드를 그대로 물려받는 새로운 클래스를 만들기 위한 방법. 
class 서브_클래스(슈퍼_클래스):
    # 이 부분에 서브 클래스의 내용 코딩
    

### 메서드 오버라이딩  
상위 클래스의 메서드를 서브 클래스에서 재정의 하는 것. 

```python
class 서브클래스(슈퍼클래스):
    #서브클래스의 내용 코딩
```

```python
## 클래스 선언 부분 ##
class  Car :
    speed = 0
    def upSpeed(self, value):
        self.speed += value
        
        print("현재 속도(슈퍼 클래스) : %d" % self.speed)

class Sedan(Car) :
    def upSpeed(self, value):
        self.speed += value
        
        if self.speed > 150 :
            self.speed = 150
            
        print("현재 속도(서브 클래스) : %d" % self.speed)

class Truck(Car) :
    pass

## 변수 선언 부분 ##
sedan1, truck1 = None, None

## 메인 코드 부분 ##
truck1 = Truck()
sedan1 = Sedan()

print("트럭 --> ", end = "")
truck1.upSpeed(200)

print("승용차 --> ", end = "")
sedan1.upSpeed(200)
```

### 다중상속



```python

```

### 5. 객체지향 프로그래밍의 심화내용
### 추상클래스
  
### 클래스의 특별한 메서드
- __del__() 메서드 : destructor. 생성자와 반대로 인스턴스를 삭제할 때 자동으로 호출.   
- __repr__()메서드 : 인스턴스를 print()문으로 출력할 때 실행되는 메서드. print(인스턴스)를 실행하면 호출된다.  
- __add()__()메서드 : 인스턴스 사이에 덧셈 작업이 일어날 때 실행되는 메서드.
- 비교메서드 : __lt__(), __le__(), __gt__(), __ge__(), __eq__(), __ne__() 인스턴스 사이의 비교 연산자를 사용할 때 호출되는 메서드.  

#### 멀티스레드  
스레드는 프로그램 하나에서 여러 개를 동시에 처리할 수 있도록 제공하는 기능. 

#### 멀티프로세싱  
스레드는 내부적으로 CPU를 1개만 사용. 동시에 수행하더라도 실질적인 속도는 오히려 느려질 수 있음.   
반면, 멀티 프로세싱 기법은 동시에 CPU를 여러 개 사용.  



```python

```
