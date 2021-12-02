# GIT 

## GIT 이란?

version control system - 버전 관리를 위함

git - 버전 컨트롤 시스템, 버전 관리

특정 파일이 아닌 폴더를 관리해주는 tool

프로젝트는 한 개가 아닌 몇백개의 프로그램 파일이 필요하기 때문에 '폴더'가 깃이 관리하는 대상

폴더(디렉토리) - 단순 파일 철로서의 기능밖에 없음

기능을 갖춘 저장소(리포) 로 업그레이드하기

## GIT basic



폴더를 리포로 업그레이드하기

업그레이드 명령어는 git init

.git이라는 폴더가 생겼다

(master)

잘못 만들면 어떻게 삭제?

rm -rf .git (함부로 사용 X)

```
git status 상황을 묻는 것 . 계속 물어볼거야
```



On branch master

No commits yet -> commit(버저닝)



```
touch README.md
```

```
git status
```

untracked file : use file ~~ 

```
git add README.md
```

changes to be committed

new file: README.md

```
git commit -m 'first commit'
```

깃을 통해 버전 + 메세지를 남길 거다 ~ ' 이렇게 '

Author identity unknown

***Please tell me who you are: by 누구 인지 알려줘 ! (폴라로이드 사진 연상 ~ by 누구: 반드시 남겨야 함)

-> 계정당 한번씩만 하면 되는 작업

```
git config --global user.name '닉네임' 
```

```
git config --global user.name 'zoey.ppb@gmail.com' 
```

사용자의 이름과 메일주소 입력하는거 (이메일은 깃허브 가입이메일)

잘 됐는지 확인하기

```
cat ~/.gitconfig
```

입력한 이름, 이메일대로 들어가있는지 확인하기 

<<<<다시 처음부터 필요한거 >>>>

```
git init
touch README.md
git add .
git config --global user.name '내이름'
git config --global user.email 'github에서@쓸메일주소'
cat ~/.gitconfig # => 입력한대로 잘 나오는지 확인 !
git commit -m 'first commit'
```

이전 명령어: 커서에서 키보드 위 아래 누르면 나온다!



<현재까지 중요한 5개 명령어!>

초기화 시점에 1회 입력

```
git init -> 초기화 시점에 1회 입력
```

작업하며 계속 입력하는 명령어

```
$ git add <filename>
$ git commit -m 'MESSAGE'
```

모니터링 명령어

```
$ git status #현재 상황
$ git log    #commit 로그
```



터미널 위 창 띄어쓰기 하나만 해도 git status ->변경됨 (빨간글씨)

그럼 ~ git add README.md 입력하면

Modified 에서 ??로 바뀜 (맥이라 다름)

다시 git status 해보면 ㅇㅋ.





분장실 / 스테이지 / 사진첩 이라는 개념으로 이해

분장실에서 스테이지로 옮겨주는게 git add <filename>

개발자가 존재하는 공간 -> 분장실 (코드 짜기, 파일 수정)

코드 짠다 - 스테이지 올린다 - 사진찍는다 (커밋한다)

이 과정의 반복

git status (분장 중이야? 물어보는거)



찍은 사진들을 체크하는게 git log

$ git commit -m 'MESSAGE' - 스테이지에 안올라갓음 - add 

새로 파일 만들기 

touch ~~

git status

(use "git add <file>..." to include in what will be committed)
        exit.md
        register.md
        welcome.md

아직 얼굴도장 안찍었어 (스테이지에 올라가 있지 않다)

git add . (.의 의미는 내가 현재 있는 위치의 모든 파일을 다 애드하겠다)

스테이지 왜필요? 스테이지에는 여러개 파일을 올리고 한번에 묶어서 커밋하기 위해서 

```
git commit -m '신입사원 안내 문서 생성' 
 # 스테이지의 여러 개 파일을 하나의 이름으로 묶어서 커밋하기
```



git commit -m '신입사원 안내 문서 생성' 

이제 사진첩을 봐볼까? git log 



commit -> 사진 (파일 1,2,3의 고유 번호)

author -> 찍은 사람

신입사원 안내 문서 생성: 남긴 메모! -> 이건 사진에 메모가 추가된 것





*** 절대 하면 안되는 것

1. ~ 에서 $ git init 진행 (홈은 리포하면 안됨)
2. 리포 안에 리포 만들기
3. 즉, $ git init 입력 전 확인할 점
   1. ~ 인지
   2. (master) 떠 있는지