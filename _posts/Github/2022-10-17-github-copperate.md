---
title: "[Github] Github으로 협업하기"
excerpt: "깃헙으로 팀원들과 협업하기"
categories: 
        - Github

tag:
       - Github
       - Team

author_profile: true

last_modified_at: 2022-10-17T16:10:00:000Z

toc: true

toc_sticky: true
---

## Repository, Branch
- Team Leader가 협업할 Repository를 생성하여 Team member들을 초대한다.
- Branch는 최종버전이 올라갈 master branch와 멤버들의 개인 Branch를 생성한다. (에러 방지)

```
Repository
|  ├── master (branch)
|  ├── Team member 1 (branch)
|  ├── Team member 2 (branch)
|  ├── Team member 3 (branch)
                             ·
                             ·
                             ·
```

- 먼저 master 브랜치에 Team Leader가 생성한 프로젝트를 Commit, Push한다.  
이후 Team member들이 Repository를 클론하고, 각자 맡은 부분을 개발하고 개인 Branch에 Commit, Push하고 개발이 끝나면 Team Leader에게 PR을 작성해 요청한다.

## Pull, Merge Pull requests

- Team Leader는 Repository의 상단 Pull request 메뉴에 Team member가 작성한 PR이 추가된것을 볼 수 있을 것이다.  
Team member가 작성한 PR을 확인하고 아래와 같이 행동한다.

```
수정해야할 부분이 있을 경우: Review changes
문제가 없다면: Merge pull requests => Confirm merge
```

- Confirm merge까지 성공했다면 Team member의 개발내용이 master branch에 동기화 되었다는것이다.

<span style="color: red;">
         여기서 잠깐! ⚠️
</span>

- 물론 Team Leader도 개발중이었을 텐데 이때 pull을 통해 Team Leader의 개발내용과 master branch의 버전이 맞지 않기 때문에 동기화 작업을 진행해준다.

```
git add .
git commit -m “Commit 메세지”
```

- 위의 명령어를 통해 먼저 Team Leader의 진행상황을 저장 및 master branch와 동기화 시켜준다.

```
git pull origin master
```

- 위의 명령어로 Team Leader의 로컬저장소의 branch와 원격저장소의 master branch와 합쳐준다.

```
git push -u origin master
```

- Team Leader또한 개발이 완료되었다면 master branch에 push하여 준다.