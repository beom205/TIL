# Git 기본


### Git 설치

#### 명령어

##### add

- 커밋할 목록에 추가

##### commit

- 커밋(create a snapshot)을 만들기

##### push

- 현재까지의 역사(commits)가 기록되어 있는 곳에 새로 생성한 커밋들 반영하기
- 내가 만들어 놓은 코드를 서버에 반영해주는 것

## 설치하기

1. Git Bash 검색

![1209%203%20Git/Untitled.png](1209%203%20Git/Untitled.png)

Git for Windows 클릭

[Git for Windows](https://gitforwindows.org/)

2.  Download 클릭하여 설치함

옵션

![1209%203%20Git/Untitled%201.png](1209%203%20Git/Untitled%201.png)

최소한 이거 추가

이거해야 폴더에서 우클릭으로 Bash 불러올 수 있음

- Use Vim

![1209%203%20Git/Untitled%202.png](1209%203%20Git/Untitled%202.png)

- 3번째 Use Git and Unix tools ~~

![1209%203%20Git/Untitled%203.png](1209%203%20Git/Untitled%203.png)

나머지는 Default로 설치함

CMD와 비슷하지만 CMD보단 깔끔하고, Git도 같이 설치되기 때문에 설치됨.

---

# Git bash로 마크다운 파일 Git에 올리기

- git 유저 설정

    #이메일 설정
    git config --global user.email "beom205@gmail.com"
    
    #이름 설정
    git config --global user.name "beom205"

- 유저 설정 확인

    B@DESKTOP-5UIA6BE MINGW64 ~/Desktop/Github 특강/TIL (master)
    $ git config --global user.email
    beom205@gmail.com
    
    B@DESKTOP-5UIA6BE MINGW64 ~/Desktop/Github 특강/TIL (master)
    $ git config --global user.name
    beom205

![1209%203%20Git/Untitled%204.png](1209%203%20Git/Untitled%204.png)

### 1. Git 초기화

    Git init

- 우리는 TIL 폴더를 Git으로 관리할 것이다.

![1209%203%20Git/Untitled%205.png](1209%203%20Git/Untitled%205.png)

1. 해당 폴더로 이동한 후
2. git init을 하면  (master)란 글씨가 추가된다.

- ls -a 로 숨긴파일을 보면

![1209%203%20Git/Untitled%206.png](1209%203%20Git/Untitled%206.png)

### 2. Git add

![1209%203%20Git/Untitled%207.png](1209%203%20Git/Untitled%207.png)

### 3. git status

- 깃 상태 확인

![1209%203%20Git/Untitled%208.png](1209%203%20Git/Untitled%208.png)

마크다운.md는 committed에 올라왔지만,  .assets는 untracked files에 있다.

### 4. git commit -m ""

m: 메세지의 약자

    git commit -m "마크다운 설명을 작성한 마크다운.md 추가"

![1209%203%20Git/Untitled%209.png](1209%203%20Git/Untitled%209.png)

### 5. git add .

git에서 . 이란 현재 폴더에있는 모든 파일과 폴더다

![1209%203%20Git/Untitled%2010.png](1209%203%20Git/Untitled%2010.png)

### 6. 파일 변경하고,  add 후 status로 확인하기

![1209%203%20Git/Untitled%2011.png](1209%203%20Git/Untitled%2011.png)

변경되었으면 modified로 나와있다.

### 7. Github에 TIL라는 레파지토리 생성

Push할 때 어디로 보낼지에대한 설정을  보낼 폴더 안에(.git 폴더)에 알려줘야한다.

이 설정 명령어는 레파지토리를 생성하면 알려준다.

![1209%203%20Git/Untitled%2012.png](1209%203%20Git/Untitled%2012.png)

    echo "# TIL" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin https://github.com/beom205/TIL.git
    git push -u origin master

여기서 remote 부터 시작하면 된다.

### 8.  git remote add 설정

- push를 할 때 어디로 할지 목표를 설정해준다.

    git remote add origin https://github.com/beom205/TIL.git

![1209%203%20Git/Untitled%2013.png](1209%203%20Git/Untitled%2013.png)

### 9. git remote -v 로 확인

    git remote -v

![1209%203%20Git/Untitled%2014.png](1209%203%20Git/Untitled%2014.png)

### 10. push 하기

    git push origin master

위 명령어를 입력하면 로그인 창이 뜬다.

![1209%203%20Git/Untitled%2015.png](1209%203%20Git/Untitled%2015.png)

로그인하면  push가 시작된다.

![1209%203%20Git/Untitled%2016.png](1209%203%20Git/Untitled%2016.png)

### 11. 레파지토리를 새로고침하면 push가 된 것을 확인할 수 있다.

![1209%203%20Git/Untitled%2017.png](1209%203%20Git/Untitled%2017.png)

### 12. 다시 수정 후 올리기

1. git add .
2. git status (확인)
3. git commit -m "메세지"
4. git push origin master

### 13. gitignore 자동 생성 사이트

[gitignore.io](https://www.gitignore.io/)

### 14. gitignore 설정하기

1. vs code에서 TIL(git 폴더) 불러오기
2. .gitignore 파일 추가
3. [README.md](http://readme.md)  파일 추가
4. [gitignore.io](http://gitignore.io) 사이트에서 무시할 os나 언어 추가해서 생성하고 나온 결과를 .gitignore 파일에 복사
5. push하기

![1209%203%20Git/Untitled%2018.png](1209%203%20Git/Untitled%2018.png)

![1209%203%20Git/Untitled%2019.png](1209%203%20Git/Untitled%2019.png)

### 16. 커밋 내용

기능이 추가되거나, 

차이(diff)가 무엇이고, 수정 이유를 log로 남길 수 있다.

뼈대 코드 구성

메인 기능 구현

로그인 기능 구현

채팅 기능 구현

디자인 적용

현재 파일들을 안전한 상태로 과거
