---
title: "[Github] Github 명령어 알아보기" 
excerpt: "Github Command"
categories:
    - Github

tag:
    - Command
    - Github 

author_profile: true    #작성자 프로필 출력 여부

last_modified_at: 2022-10-17T09:30:00.000Z

toc: true   #Table Of Contents 목차 

toc_sticky: true
---

## Github 명령어

> git init  
> (로컬저장소 초기화)

> git status  
> (로컬저장소 변동사항 출력)

> git add .  
> (현재까지의 모든 변동사항 및 파일을 올린다)

> git remote add origin [repository url]  
> (원격저장소 URL 및 사용자 정보를 로컬저장소에 저장)

> git commit -m "Commit Message"  
> (Commit 메세지와 함께 변동사항을 Commit)

> git push -u origin 브랜치이름  
> (Commit 내용을 원격저장소로 업로드)

> git clone [repository url]  
> (원격저장소로부터 모든 파일을 다운로드)

> git pull  
> (원격저장소의 Commit을 가져온뒤 현재 로컬저장소에 합체)

## git pull을 사용할떄 주의할점

- git pull의 경우 아래의 사진과 같이 원격저장소와 로컬저장소의 Commit이 일치하지 않을떄 사용하여
![1](https://user-images.githubusercontent.com/53817611/196068248-bfeed008-398b-4df4-9132-3a2a29af5a7d.png)

- 다음과 같은 상태, 원격저장소의 최신 커밋을 추적하여 가져온다.  
- (이 과정을 fetch라고 한다.)
![2](https://user-images.githubusercontent.com/53817611/196068268-f56e162e-e7d1-4679-8676-8f04424f0d7b.png)

- 이후 원격저장소의 <span style="background-color: #f5f0ff;">master Branch</span>를 로컬저장소의 <span style="background-color: #f5f0ff;">master Branch</span>와 합체시키면 로컬저장소의 <span style="background-color: #f5f0ff;">master Branch</span>도 HEAD Commit이 원격 저장소의 HEAD Commit과 같아지게 된다.  
- (이 과정을 merge라고 한다.)
![3](https://user-images.githubusercontent.com/53817611/196068398-d986cfce-807b-4a1d-a061-1d3f6c1380b5.png)

- 위에서 말했다싶이 pull 명령어는 fetch, merge 과정을 한번에 하는것이기때문에 잘못했다간 conflict, 즉 충돌이 일어날수도있다.
![4](https://user-images.githubusercontent.com/53817611/196073347-b217af58-e8ff-434c-9d18-782512d05602.png)

- 위의 그림과 같이 <span style="background-color: #f5f0ff;">second commit</span> 이후에 원격저장소는 <span style="background-color: #f5f0ff;">third commit</span>인데 로컬저장소에서는 <span style="background-color: #f5f0ff;">third commit</span>과 다른 <span style="background-color: #f5f0ff;">new commit</span>이 존재할때 pull 명령어를 사용하게 되면 원격저장소와 로컬저장소의 commit 상태가 다르기때문에 충돌이 일어나 오류가 발생한다.

> Reference: https://kotlinworld.com/m/288