### 1주차 개발 입문 스터디 WIL    

#### Git이란   
###### 버전 관리 및 협업을 위해 사용하는 오픈소스 소프트웨어   

#### 파일의 생명주기
<img src="/Week1/life-cycle.jpg" width="50%" alt="Life Cycle"></img>

#### Git/GitHub 흐름
<img src="/Week1/Git-Flow.jpg" width="50%" alt="Git Flow"></img>

#### Git 최초 설정
    $ git config --global user.name "<user name>"
    $ git config --global user.email "<user email>"   
    $ git remote add origin <address>
    $ git branch -M main
    $ git push -u origin main

#### GitHub에 올리기
    $ git add <file name>
    $ git commit -m "<commit message>"   
    $ git push origin main 

#### Commit Message Type
###### - feat: 새로운 기능 추가
###### - refactor: 기존 코드 개선
###### - fix: 버그 수정
###### - chore: 코드 외의 설정 변경
###### - docs: 문서화
###### - test: 테스트코드     

---
#### 실습 레포지토리 링크
###### https://github.com/ybkang1108/ybkang1108.git