## Beginner-Study WIL4

### Branch 관리의 필요성
- 서로의 작업에 영향을 주지 않기 위해 브랜치 분리
- 각 브랜치가 어떤 작업을 위해 존재하는지 구분

### Branch 보호 규칙
- 승인 없이 Pull Request를 병합할 수 없도록 제한할 수 있음
- 특정 branch에 Push 가능자를 제한할 수 있음

### _브랜치 전략: Git Flow vs GitHub Flow_

### Git Flow
<img src="/Week4/gitflow.jpg" width="50%" alt="Git Flow"></img>  

#### 브랜치 종류
- Main Braches
    - main(master): 영원히 존재하는 첫 번째 브랜치
        - 기본으로 생성되는 브랜치
        - 병합될 떄마다 새로운 버전이 탄생
    - develop: 영원히 존재하는 두 번째 브랜치
        - feature 브랜치의 기반이 됨
- Supporting branches
    - feature
        - develop 브랜치에서 분기하여 작업
        - 기능 개발 완료 후 develop으로 병합
        - 기본으로 있는 이름들 제외 대부분의 이름이 가능
    <img src="/Week4/feature.jpg" width="70%" alt="feature"></img>  

    - release: 배포 준비를 위한 브랜치
        - 자잘한 버그 수정, quality assurance 작업
        - develop 브랜치에서 분기하여 main 브랜치로 병합
    - hotfix: 배포 환경에서 즉각적인 수정이 필요한 경우
        - main 브랜치에서 분기
        - main, develop에 모두 병합해야함
    <img src="/Week4/hotfix.jpg" width="70%" alt="hotfix"></img>  

**배포가 수시로 이루어지는 현 시대의 웹앱과는 부적합함**    
**=> Github Flow**

### GitHub Flow
<img src="/Week4/githubflow.jpg" width="50%" alt="GitHub Flow"></img>  

#### 브랜치 종류
- main
    - 항상 배포 가능 상태 -> 병합 전 충분한 test 필요
- feature
    - main에서 분기하여 작업 후 다시 main으로 병합
    - branch의 목적을 이름에 잘 담아야 함
    - 코드 리뷰가 더 중요함

### _Convention을 만들어 사용하면 긴 시간이 지난 후에도 쉽게 의도를 파악할 수 있음_
