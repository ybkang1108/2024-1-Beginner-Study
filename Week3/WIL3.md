### Beginner-Study WIL3

### git log 확인
commit 기록을 최신 순으로 확인   
commit id: commit의 식별을 위해 사용되는 40자 길이의 16진수   

    $ git log --oneline // 각 commit을 한 줄에 요약   
    
<img src="/Week3/git_log.jpg" width="70%" alt="Git Log"></img>   

### HEAD: 현재 작업 중인 위치를 가리킴
- 현재 작업중인 branch의 가장 최근 commit
- 다음 commit의 base가 되는 commit
- 새로운 commit이 생기면 HEAD도 변경됨

### commit --amend
- 마지막 commit의 내용에 변경이 있을 때 사용
- 완전히 새로운 commit으로 대체 -> commit id가 바뀜

#### 1. vim 진입 없이 commit msg 수정
    $ git commit --amend -m "commitMsg"

#### 2. commit msg 수정 없이 commit 수정
    $ git commit --amend --no-edit
_다른 사람이 작업 기반으로 삼고 있는 commit은 amend하면 안 됨!_


### reset
commit을 제거함

    $ git reset '--option' <commitID> // ex. $ git reset --soft a1s2d3f

#### 1. reset --soft
커밋만 취소되며 변경 사항이 Staging Area로 돌아감
#### 2. reset --mixed
커밋을 취소하고 변경 사항이 Working Directory로 돌아감
#### 3. reset --hard
커밋을 취소하고 변경사항을 모두 제거한 뒤 이전 커밋으로 돌아감

##### EXAMPLE
    $ git log --oneline
```
a1s2d3f (HEAD -> develop) fifth commit
s2d3f4g fourth commit
345hj26 third commit
7g8dg7f second commit
5g568vk first commit
```
##### Case 1.
    $ git reset --soft 345hj26
###### -> fourth, fifth commit이 Staging Area로 돌아감
##### Case 2.
    $ git reset --mixed 345hj26
###### -> fourth, fifth commit이 Working Directory로 돌아감
##### Case 3.
    $ git reset --hard 345hj26
###### -> fourth, fifth commit이 완전히 사라짐


### revert
<img src="/Week3/revert.jpg" width="40%" alt="Revert"></img>   
commit을 제거하는 게 아니라 이전으로 되돌림 -> 되돌리기 위한 새로운 commit이 생성됨
    $ git revert a1s2d3f // --edit이 default

#### 1. revert --no-edit
편집기 진입 없이 바로 revert 가능   

    $ git revert --no-edit <commitID>

#### 2. revert --no-commit
직접 commit하지 않고 revert내용을 Staging Area에 올림  

    $ git revert --no-commit <commitID>

### reset vs revert
- reset은 commit을 __삭제__ 하므로 위험함
- commit을 공유하는 다른 branch에도 영향을 줄 수 있으므로 삭제보다는 commit을 생성하여 되돌리는 revert를 쓰는 것이 안전함