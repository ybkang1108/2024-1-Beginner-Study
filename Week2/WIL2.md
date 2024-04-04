## Beginner-Study WIL2

### Fork
다른 사용자의 Repository를 자신의 계정으로 복사하여 독립적으로 수정하고 관리함   

### Star
관심 있는 Repository나 Project에 star를 달아 <북마크>와 같이 관리

### Issue
Repository에서 작업 계획, 토론 및 추적을 위해 활용

### Branch
기존 브랜치에서 분기되어 생성되는 별도의 작업 공간   
fork와 달리 같은 Repository에 생성됨    
  
    type/<issue 번호>-<간략한 설명> (ex. docs/1-readme)

### Pull Request
- 분기된 Branch를 다시 병합하기 위한 절차
- 새로운 변경을 제안하거나 병합 시 발생하는 충돌 해결
- Merge 전 코드 리뷰

### Merge
1. Merge Commit
* A, B, C commit을 SQUASH
* 하나의 커밋으로 main branch로 병합   
<img src="/Week2/SquashnMerge.jpg" width="50%" alt="Squash n Merge"></img>   

2. Squash and Merge
* A, B, C commit의 base를 재설정
* 모두 새로운 commit으로 변경   
<img src="/Week2/RebasenMerge.jpg" width="50%" alt="Rebase n Merge"></img>   

3. Rebase and Merge
* commit hash(commit의 식별을 위해 사용하는 ID)
* 많은 충돌이 생길 수 있음

### Branch Command
- 현재 branch 확인   
    $ git branch
- 모든 branch 확인   
    $ git branch -a
- branch 생성   
    $ git branch "Branch Name"
- branch 삭제   
    $ git branch -D "Branch Name"
- branch 이동   
    $ git checkout "Branch Name"
- branch 생성 후 이동   
    $ git checkout -b "Branch Name"

### Branch에서 파일 생성 후 PUSH 과정
1. branch 생성 후 이동
2. file 생성
3. $ git commit -m "Commit MSG"
4. $ git push origin "Branch Name"
5. Git에서 Pull Request   
    comment에 "- close #issueNum"을 쓰면 Merge와 동시에 issue가 닫힘!
6. Merge
---
### 실습 링크    
###### https://github.com/ybkang1108/2024-1-Beginner-Study/pull/2
