### Beginner-Study WIL2
---
#### git log 확인
###### commit 기록을 최신 순으로 확인
###### commit id: commit의 식별을 위해 사용되는 40자 길이의 16진수
    $ git log --oneline // 각 commit을 한 줄에 요약   
<img src="/Week3/git_log.jpg" width="50%" alt="Git Log"></img>   

#### HEAD: 현재 작업 중인 위치를 가리킴
###### - 현재 작업중인 branch의 가장 최근 commit
###### - 다음 commit의 base가 되는 commit
###### - 새로운 commit이 생기면 HEAD도 변경됨

#### commit --amend
###### - 마지막 commit의 내용에 변경이 있을 때 사용
###### - 완전히 새로운 commit으로 대체 -> commit id가 바뀜
###### - vim 진입 없이 commit msg 수정
    $ git commit --amend -m "commitMsg"
###### - commit msg 수정 없이 commit 수정
    $ git commit --amend --no-edit
##### 다른 사람이 작업 기반으로 삼고 있는 commit은 amend하면 안 됨!

#### reset
###### commit을 제거함
    $ git reset '--option' <commitID> // $git reset --soft a1s2d3f
##### 1. reset --soft
###### 커밋만 취소되며 변경 사항이 Staging Area로 돌아감
##### 2. reset --mixed
###### 커밋을 취소하고 변경 사항이 Working Directory로 돌아감
##### 3. reset --hard
###### 커밋을 취소하고 변경사항을 모두 제거한 뒤 이전 커밋으로 돌아감

#### revert
###### commit을 제거하는 게 아니라 이전으로 되돌림 -> 되돌리기 ㅜ이한 새로운 commit이 생성됨
    $ git revert a1s2d3f // --edit이 default

##### revert --no-edit
###### 편집기 진입 없이 바로 revert 가능
    $ git revert --no-edit <commitID>
##### revert --no-commit
###### 직접 commit하지 않고 revert내용을 Staging Area에 올림

#### reset vs revert
###### - reset은 commit을 <<삭제>>하므로 위험함
###### - commit을 공유하는 다른 branch에도 영향을 줄 수 있으므로 삭제보다는 commit을 생성하여 되돌리는 revert를 쓰는 것이 안전함