```python
import random
# 게임을 위한 랜덤 숫자 생성

rn = random.randrange(1,101,1)
num = -1

t_cnt = 0

print('1~100 까지의 숫자 up & down 게임을 시작합니다 !!!')
print('-------------------------------------------------')

while (rn != num):
    num = int(input('1~100 사이의 숫자를 입력하세요 :'))

    if (num > rn ):
        print('down')
    elif (num < rn):
        print('up')

    t_cnt += 1




print('--------------------------------------------------')
print(t_cnt,'번 만에 정답을 맞추셨습니다.')
```
