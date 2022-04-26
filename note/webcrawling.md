```python
import requests                  # 웹 페이지의 HTML을 가져오는 모듈
from bs4 import BeautifulSoup    # HTML을 파싱하는 모듈
 
# 웹 페이지를 가져온 뒤 BeautifulSoup 객체로 만듦
response = requests.get('https://pythondojang.bitbucket.io/weather/observation/currentweather.html')
soup = BeautifulSoup(response.content, 'html.parser')
 
table = soup.find('table', { 'class': 'table_develop3' })    # <table class="table_develop3">을 찾음
data = []                            # 데이터를 저장할 리스트 생성
for tr in table.find_all('tr'):      # 모든 <tr> 태그를 찾아서 반복(각 지점의 데이터를 가져옴)
    tds = list(tr.find_all('td'))    # 모든 <td> 태그를 찾아서 리스트로 만듦
                                     # (각 날씨 값을 리스트로 만듦)
    for td in tds:                   # <td> 태그 리스트 반복(각 날씨 값을 가져옴)
        if td.find('a'):             # <td> 안에 <a> 태그가 있으면(지점인지 확인)
            point = td.find('a').text    # <a> 태그 안에서 지점을 가져옴
            temperature = tds[5].text    # <td> 태그 리스트의 여섯 번째(인덱스 5)에서 기온을 가져옴
            humidity = tds[9].text       # <td> 태그 리스트의 열 번째(인덱스 9)에서 습도를 가져옴
            data.append([point, temperature, humidity])    # data 리스트에 지점, 기온, 습도를 추가
 
data    # data 표시. 주피터 노트북에서는 print를 사용하지 않아도 변수의 값이 표시됨
```




    [['서울', '25.6', '30'],
     ['백령도', '18.4', '62'],
     ['인천', '20.8', '54'],
     ['수원', '25.0', '41'],
     ['동두천', '24.9', '34'],
     ['파주', '25.1', '39'],
     ['강화', '20.0', '56'],
     ['양평', '25.5', '32'],
     ['이천', '25.6', '28'],
     ['북춘천', '24.6', '36'],
     ['북강릉', '19.9', '56'],
     ['울릉도', '16.8', '77'],
     ['속초', '19.1', '75'],
     ['철원', '23.9', '37'],
     ['대관령', '17.9', '49'],
     ['춘천', '25.7', '39'],
     ['강릉', '22.7', '41'],
     ['동해', '19.5', '77'],
     ['원주', '23.4', '36'],
     ['영월', '24.2', '34'],
     ['인제', '24.3', '31'],
     ['홍천', '25.4', '25'],
     ['태백', '19.6', '43'],
     ['정선군', '23.0', '32'],
     ['서산', '23.6', '49'],
     ['청주', '24.3', '33'],
     ['대전', '25.1', '37'],
     ['충주', '24.4', '32'],
     ['추풍령', '23.0', '35'],
     ['홍성(예)', '24.3', '46'],
     ['제천', '24.2', '32'],
     ['보은', '23.7', '28'],
     ['천안', '23.5', '35'],
     ['보령', '21.4', '56'],
     ['부여', '23.9', '37'],
     ['금산', '23.7', '30'],
     ['전주', '24.9', '44'],
     ['광주', '24.0', '35'],
     ['목포', '22.8', '51'],
     ['여수', '22.8', '49'],
     ['흑산도', '19.2', '93'],
     ['군산', '21.8', '55'],
     ['완도', '23.2', '45'],
     ['고창', '22.7', '53'],
     ['순천', '22.5', '40'],
     ['진도(첨찰산)', '22.2', '48'],
     ['부안', '22.9', '44'],
     ['임실', '22.8', '40'],
     ['정읍', '23.8', '47'],
     ['남원', '23.8', '35'],
     ['장수', '22.0', '33'],
     ['고창군', '23.7', '48'],
     ['영광군', '22.4', '40'],
     ['순창군', '23.5', '38'],
     ['보성군', '23.7', '34'],
     ['강진군', '24.1', '33'],
     ['장흥', '25.5', '33'],
     ['해남', '24.6', '40'],
     ['고흥', '24.4', '34'],
     ['광양시', '24.6', '43'],
     ['진도군', '21.9', '58'],
     ['제주', '20.7', '60'],
     ['고산', '19.1', '74'],
     ['성산', '23.1', '33'],
     ['서귀포', '24.0', '43'],
     ['안동', '25.0', '32'],
     ['포항', '19.0', '83'],
     ['대구', '25.7', '31'],
     ['울산', '19.7', '70'],
     ['창원', '20.6', '63'],
     ['부산', '20.2', '66'],
     ['울진', '17.6', '84'],
     ['상주', '25.0', '32'],
     ['통영', '20.0', '71'],
     ['진주', '23.8', '30'],
     ['김해시', '21.9', '60'],
     ['북창원', '22.8', '50'],
     ['양산시', '21.4', '63'],
     ['의령군', '25.1', '40'],
     ['함양군', '23.3', '38'],
     ['봉화', '22.0', '38'],
     ['영주', '23.0', '36'],
     ['문경', '25.5', '26'],
     ['청송군', '17.9', '71'],
     ['영덕', '19.4', '57'],
     ['의성', '25.7', '25'],
     ['구미', '25.7', '32'],
     ['영천', '21.8', '47'],
     ['경주시', '23.8', '49'],
     ['거창', '22.7', '38'],
     ['합천', '25.1', '32'],
     ['밀양', '24.7', '34'],
     ['산청', '24.8', '41'],
     ['거제', '23.1', '57'],
     ['남해', '24.5', '40']]




```python
import requests                  # 웹 페이지의 HTML을 가져오는 모듈
from bs4 import BeautifulSoup    # HTML을 파싱하는 모듈
 
# 웹 페이지를 가져온 뒤 BeautifulSoup 객체로 만듦
response = requests.get('https://pythondojang.bitbucket.io/weather/observation/currentweather.html')
soup = BeautifulSoup(response.content, 'html.parser')
table = soup.find('table', { 'class': 'table_develop3' })    # <table class="table_develop3">을 찾음
data = []                            # 데이터를 저장할 리스트 생성
for tr in table.find_all('tr'):      # 모든 <tr> 태그를 찾아서 반복(각 지점의 데이터를 가져옴)
    tds = list(tr.find_all('td'))    # 모든 <td> 태그를 찾아서 리스트로 만듦
                                     # (각 날씨 값을 리스트로 만듦)
    for td in tds:                   # <td> 태그 리스트 반복(각 날씨 값을 가져옴)
        if td.find('a'):             # <td> 안에 <a> 태그가 있으면(지점인지 확인)
            point = td.find('a').text    # <a> 태그 안에서 지점을 가져옴
            temperature = tds[5].text    # <td> 태그 리스트의 여섯 번째(인덱스 5)에서 기온을 가져옴
            humidity = tds[9].text       # <td> 태그 리스트의 열 번째(인덱스 9)에서 습도를 가져옴
            data.append([point, temperature, humidity])    # data 리스트에 지점, 기온, 습도를 추가   
            

```


```python
# 데이터를  csv파일에 저장하기
with open('weather.csv', 'w') as file:    # weather.csv 파일을 쓰기 모드로 열기
    file.write('point,temperature,humidity\n')                  # 컬럼 이름 추가
    for i in data:                                              # data를 반복하면서
        file.write('{0},{1},{2}\n'.format(i[0], i[1], i[2]))    # 지점,온도,습도를 줄 단위로 저장
```


```python
# %matplotlib inline을 설정하면 matplotlib.pyplot의 show 함수를 호출하지 않아도
# 주피터 노트북 안에서 그래프가 표시됨
%matplotlib inline
import pandas as pd                # 데이터를 저장하고 처리하는 패키지
import matplotlib as mpl           # 그래프를 그리는 패키지
import matplotlib.pyplot as plt    # 그래프를 그리는 패키지
 
# csv 파일을 읽어서 DataFrame 객체로 만듦. 인덱스 컬럼은 point로 설정
df = pd.read_csv('weather.csv', index_col='point', encoding='euc-kr')
df    # df 표시
```

    Matplotlib is building the font cache; this may take a moment.
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>temperature</th>
      <th>humidity</th>
    </tr>
    <tr>
      <th>point</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>서울</th>
      <td>25.6</td>
      <td>30</td>
    </tr>
    <tr>
      <th>백령도</th>
      <td>18.4</td>
      <td>62</td>
    </tr>
    <tr>
      <th>인천</th>
      <td>20.8</td>
      <td>54</td>
    </tr>
    <tr>
      <th>수원</th>
      <td>25.0</td>
      <td>41</td>
    </tr>
    <tr>
      <th>동두천</th>
      <td>24.9</td>
      <td>34</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>합천</th>
      <td>25.1</td>
      <td>32</td>
    </tr>
    <tr>
      <th>밀양</th>
      <td>24.7</td>
      <td>34</td>
    </tr>
    <tr>
      <th>산청</th>
      <td>24.8</td>
      <td>41</td>
    </tr>
    <tr>
      <th>거제</th>
      <td>23.1</td>
      <td>57</td>
    </tr>
    <tr>
      <th>남해</th>
      <td>24.5</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
<p>95 rows × 2 columns</p>
</div>




```python
# 아나콘다를 사용하지 않을시 pip 로 import 할 패키지를 설치해주면 됨.
```


```python
# 특별시, 광역시만 모아서 DataFrame 객체로 만듦
city_df = df.loc[['서울', '인천', '대전', '대구', '광주', '부산', '울산']]
city_df    # city_df 표시
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>temperature</th>
      <th>humidity</th>
    </tr>
    <tr>
      <th>point</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>서울</th>
      <td>25.6</td>
      <td>30</td>
    </tr>
    <tr>
      <th>인천</th>
      <td>20.8</td>
      <td>54</td>
    </tr>
    <tr>
      <th>대전</th>
      <td>25.1</td>
      <td>37</td>
    </tr>
    <tr>
      <th>대구</th>
      <td>25.7</td>
      <td>31</td>
    </tr>
    <tr>
      <th>광주</th>
      <td>24.0</td>
      <td>35</td>
    </tr>
    <tr>
      <th>부산</th>
      <td>20.2</td>
      <td>66</td>
    </tr>
    <tr>
      <th>울산</th>
      <td>19.7</td>
      <td>70</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc['서울']
```




    temperature    25.6
    humidity       30.0
    Name: 서울, dtype: float64




```python
df.loc[['서울','부산']]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>temperature</th>
      <th>humidity</th>
    </tr>
    <tr>
      <th>point</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>서울</th>
      <td>25.6</td>
      <td>30</td>
    </tr>
    <tr>
      <th>부산</th>
      <td>20.2</td>
      <td>66</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Windows 한글 폰트 설정
font_name = mpl.font_manager.FontProperties(fname='C:/Windows/Fonts/malgun.ttf').get_name()
mpl.rc('font', family=font_name)
 
# 차트 종류, 제목, 차트 크기, 범례, 폰트 크기 설정
ax = city_df.plot(kind='bar', title='날씨', figsize=(12, 4), legend=True, fontsize=12)
ax.set_xlabel('도시', fontsize=12)          # x축 정보 표시
ax.set_ylabel('기온/습도', fontsize=12)     # y축 정보 표시
ax.legend(['기온', '습도'], fontsize=12)    # 범례 지정
```




    <matplotlib.legend.Legend at 0x28a0476bbe0>




    
![png](web%20crawling_files/web%20crawling_8_1.png)
    



```python

```
