# 파이썬 개발환경 구성

#### 학습목표 :  개발환경 설치 실습   
> 1.  Python 설치와 제거
> 2.  Jupyter Notebook 설치와 제거
> 3. Github 회원가입과 설치
> 4. Pycharm 설치와 Git 연동, 버전관리

#### [프로그래밍 언어순위](https://www.tiobe.com/tiobe-index/)  


### 1. Python 설치
#### 1.1 [Python](https://www.python.org/) 사이트에서 다운로드 
#### 1.2 설치  
- 다운로드한 파일을 더블 클릭해서 실행한다.  
- 첫 설치화면에서 Add Python 3.9 to PATH에 체크하는 것 필수!!  
  ( 미체크시 경로 오류 발생)

#### 1.3 실행
- 윈도우 <시작> 버튼을 누르고 모든프로그램 > Python3.9 > IDLE 메뉴를 선택한다.
- IDLE이 시작되면 두세 줄의 파이썬 버전 정보가 출력되고 프롬프트인 >>> 옆에 커서가 깜박인다.
- CMD 창에서 python 명령어를 통해서도 실행 가능하다.


```python

```

### 2. Jupyter Notebook 설치와 실행
Jupyter 설치 전, python의 패키지 관리자인 pip를 업그레이드 한다. pip가 최신 버전인 상태라면 pip upgrade는 생략가능하다.  
pip 업그레이드 후, jupyter notebook을 설치한다.
#### 2.1 Jupyter 설치
```python
  C:\...>pip install pip --upgrade --user pip
  C:\...>pip install jupyter  
```  

Jupyter Notebook이 설치되었으면, 기본폴더를 설정하도록 한다.  
기본 폴더를 설정하지 않으면 사용자 계정의 기본 폴더에 모든 파일을 저장한다.  
#### 2.2 Jupyter Notebook 기본 폴더 설정하기
```python
  C:\...>jupyter notebook --generate-config
```
와 같이 실행 후, 생성된 ./jupyter/jupyter_notebook_config.py 파일을 편집  
c.NotebookApp.notebook_dir = 'e:/python'  
을 찾아서 ''을 적절하게 지정한다.  

#### 2.3 Jupyter Notebook 실행
```python
  C:\...>jupyter notebook
```
### Jupyter Notebook 사용법
* 셀의 개념 :  
* Code 와 Markdown 모드의 변경 : 
  + ESC(명령모드상태에서) m을 누르면 Markdown, 
  + ESC(명령모드상태에서) y를 누르면 Code상태로 변경된다.  
* 셀의 실행 :   
  + Ctrl + Enter - 실행만  
  + Shift + Enter - 실행 후 아래셀로 이동(없으면 새로 만들고 이동)  
  + Alt + Enter - 실행 후 아래셀로 이동  
* 셀의 추가  :   
  + a - 기준 셀의 위에  
  + b - 기준 셀의 아래에  
* 줄바꿈 - 마지막 글자뒤에 공백 두칸 추가  
* 들여쓰기 - 앞부분에 공백 두칸 추가


### 3. Github 회원가입과 Repository 만들기
#### 3.1. [Github](https://github.com/) 사이트에서 SignUp
#### 3.2. Repository 만들기


```python

```

### 4. Pycharm 설치와 Git 연동
#### 4.1 [Jetbrains.com](https://www.jetbrains.com/pycharm/) 사이트에서 community version download
#### 4.2 설치 후, Get from VCS(Version Control System) 체크, Github 선택 후, Git 설치 과정 진행
#### 4.3 coding용 글꼴 [d2coding](https://github.com/naver/d2codingfont/releases)
      - C:\Windows\fonts에 복사
      - Appearance & Behavior - Apperance - Use Custom font 
      - Editor - font  
[주피터 노트북 폰트 변경](https://blog.naver.com/duqrlwjddns1/221612863295)
##### pycharm 계정 로그인정보  
- Settings - Version Control - Github
      
설치후 pycharm에 글꼴 변경!


#### [참고자료]
- [Pycharm 프로젝트와 Github 저장소 연동하기](https://ellun.tistory.com/280)  
- [Git + pycharm 연동 토큰생성](https://blog.naver.com/milktea0614/222653009315)


```python

```
