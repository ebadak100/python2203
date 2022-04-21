```python
import random

# 게임을 위한 랜덤 숫자 생성
rn = ["0", "0", "0"]
rn[0] = str(random.randrange(1, 9, 1))
rn[1] = rn[0]
rn[2] = rn[0]
while (): # 조건을 작성하세요
    rn[1] = str(random.randrange(1, 9, 1))
while (): # 조건을 작성하세요
    rn[2] = str(random.randrange(1, 9, 1))

# print(rn)

t_cnt = 0  # 시도횟수
s_cnt = 0  # 스트라이크 갯수
b_cnt = 0  # 볼 갯수

print("숫자야구게임을 시작합니다 !!!")
print("---------------------------")
while (s_cnt < 3):

    num = str(input("숫자 3자리를 입력하세요 : "))

    s_cnt = 0
    b_cnt = 0

    for i in range(0, 3):
        for j in range(0, 3):
            if ():  # 조건을 작성하세요
                s_cnt += 1
            elif (): # 조건을 작성하세요
                b_cnt += 1
    print("결과 : [", s_cnt, "] Strike [", b_cnt, "] Ball")
    t_cnt += 1
print("---------------------------")
print(t_cnt, "번 만에 정답을 맞추셨습니다.")
```

