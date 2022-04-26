```python
import random

rn = ['0','0','0']
rn[0] = str(random.randrange(1,9,1))
rn[1] = rn[0]
rn[2] = rn[0]

while (rn[0] == rn[1]):
    rn[1] = str(random.randrange(1,9,1))
while (rn[0] == rn[2] or rn[1] ==rn[2]):
    rn[2] = str(random.randrange(1,9,1))

# print(rn)

t_cnt = 0
s_cnt = 0
b_cnt = 0

print('숫자 야구를 시작합니다 !!!')
print('--------------------------')

while (s_cnt <3):
    num = str(input('숫자 3자리를 입력하세요 :'))

    s_cnt = 0
    b_cnt = 0

    for i in range(0,3):
        for j in range(0,3):
            if (num[i] == str(rn[j]) and i == j):
                s_cnt += 1
            elif (num[i] == str(rn[j]) and i != j):
                b_cnt += 1
    print('결과 : ', s_cnt,'strike',b_cnt,'ball')
    t_cnt += 1
print(t_cnt,'번 만에 맞추셨습니다.')
```

