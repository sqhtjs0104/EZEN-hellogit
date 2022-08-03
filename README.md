# 서보선 과제
> 2022-08-03

### 실습 목표
1. Github 내 새 프로젝트 생성
2. 로컬 디렉토리에 Git Clone 내려받기 및 수정
3. 변경 사항 add, commit, push 과정을 통해 반영
4. 두 번째 로컬 디렉토리에 Git Clone
5. 양 디렉토리의 Git Repository 수정 및 Push, Pull
- - -

## 0. Git 명령어
1. Add
    
    현 디렉토리 변경 사항을 스테이지에 업로드

        git add <file명>

        git add --all //모든 파일 add

2. Commit

    스테이지 변경 사항을 원격지 저장소가 업로드 가능하도록 대기시킴

        git commit -m "<comment>"
    커밋 내용을 -m을 통해 달아줄 수 있음

3. Push

    원격지 저장소에 업로드

        git push origin main

4. Pull

    원격지 저장소의 내용을 내려받기

        git pull origin main

- - -
   
## 1. Github 프로젝트 생성
![img](../0803_Git생성및활용/1_newGitProject_main.PNG "New Git project")
개인 Github에 *EZEN-hellogit*이란 이름의 **새 프로젝트 생성**

## 2. 로컬 환경에 school 디렉토리 생성 및 Git Clone 내려받기
![img](../0803_Git생성및활용/2_cloneGitToSchool.PNG "Clonning Git")
터미널의 **mkdir** 명령어를 통해 *school* 디렉토리를 작업 영역에 생성한 뒤,
**git clone** 명령에 본인 Github 프로젝트 주소를 입력. *school* 디렉토리 내에 Git Clone을 내려받습니다.

Git clone 명령어:
    
    git clone git@github.com:<개인github아이디>/<개인project명>.git

## 3. Clone 받은 디렉토리에 임의 파일 3개 생성 후 Push
### A) 1번 Text file 생성 및 Git add
![img](../0803_Git생성및활용/3_firstFile.PNG "Create file1")
txt 파일 *file1*을 생성 후 저장합니다.

그 뒤 터미널에서 Git status 명령으로 현 Git 작업소의 상태를 확인, *file1*을 **add** 명령으로 스테이지에 등록합니다.
![img](../0803_Git생성및활용/4_firstGitAdd.PNG "Add file1")
수행 뒤 **git status** 명령 입력 시 터미널에 **new file: file1.txt**가 출력됩니다(초록색 문자).

### B) 2개 파일 더 생성 후 add --all
![img](../0803_Git생성및활용/5_otherFiles.PNG "Create Two more")
두 개의 text file을 더 생성한 뒤

![img](../0803_Git생성및활용/6_addAll.PNG "Git add all")
**git add --all** 명령을 통해 만든 두 파일 모두 스테이지에 등록합니다.

### C) Commit and Push
![img](../0803_Git생성및활용/7_completePush.PNG "Commit and Push")
스테이지에 올라간 파일 변동 사항을 **Commit**을 통해 원격지 저장소를 업로드 대기 상태로 만든 뒤

**Push** 명령으로 작업 내역을 모아서 원격지 저장소에 업로드합니다.

### D) 결과 Github
![img](../0803_Git생성및활용/8_resultOfFirstPush.PNG "Result of first push")
Github 작업소에 성공적으로 반영된 것이 확인됩니다.

## 4. 로컬 디렉토리에 home 디렉토리 생성 후 Git Clone 내려받기
![img](../0803_Git생성및활용/9_makeHomeDir.PNG "Create home directory")
##2와 마찬가지로 **mkdir**을 이용, *home* 디렉토리를 만든 뒤 **Git Clone**을 내려받습니다.

**dir /b** 명령으로 파일 탐색 결과 *school* 디렉토리에서 작업한 내용이 잘 반영되어 있음을 알 수 있습니다.

## 5. home 디렉토리 내 파일 수정, 삭제, 추가 후 Push
### A) 파일 수정, 삭제, 추가
![img](../0803_Git생성및활용/10_modFirstFile.PNG "Modify file1.txt")
*file1.txt*의 내용에 위와 같이 문장을 추가합니다.

![img](../0803_Git생성및활용/11_deleteFile2andCreateFile4.PNG "Delete file2 and Create file4")
그 뒤 *file2.txt*를 제거하고 *file4.txt*를 생성하였습니다.

### B) 해당 내용 Commit and Push
![img](../0803_Git생성및활용/12_secondPush.PNG "Second Push")
**git status** 명령 결과 방금의 작업 내용이 Git 작업 공간의 변경 사항으로 노출됩니다.

**git add**와 **git commit**을 진행합니다.

*git commit -a -m이 되는 줄 알았지만 -am 이 맞는 명령이었네요.

![img](../0803_Git생성및활용/13_pushFile4Too.PNG "Add file4.txt")
위 실수로 빼먹게 된 *file4.txt*도 잊지 않고 넣어줍니다.

만일 스테이지 등록과 커밋을 한 번에 하고 싶다면

    git commit -am "comment"

와 같은 형태로 활용 가능합니다. 다만 위 방법은 한 번이라도 커밋 한 적이 있는 프로젝트에 한해서 동작합니다.

### C) 결과 Github
![img](../0803_Git생성및활용/14_resultOfSecondPush.PNG "Result of second push")
Github 새로고침 결과, 파일 1의 커밋 코멘드가 바뀌어 있고 파일 2는 삭제, 4가 새로 생긴 것을 확인 가능합니다.

## 6. school 디렉토리 git pull 후 반영 여부 확인
![img](../0803_Git생성및활용/15_firstPullOnSchool.PNG "Pull on school")
터미널에서 작업 디렉토리를 *school*로 변경한 뒤, **git pull** 명령을 통해 원격지 저장소의 내용을 로컬 작업소에 내려받았습니다.

업데이트 코드와 함께 변경 내역을 확인할 수 있으며, **dir /b** 명령으로 변경된 파일 역시 확인 가능합니다.

## 7. school 디렉토리 내 수정, 삭제, 생성
### A) 작업 수행
위 home 디렉토리의 작업 내용과 동일하기에 해당 과정 캡쳐는 생략하고 설명으로 대신하겠습니다.

1. file1.txt 삭제
2. file3.txt 내용 수정
3. file5.txt 새로 생성

![img](../0803_Git생성및활용/16_thirdPush.PNG "Third push")
위 작업을 수행한 뒤 터미널에서 **git status** 명령을 수행하니, 스테이지에 등록되지 않은 변경 사항들이 출력됩니다(빨간색 문자).

해당 변경 사항을 **git add --all** 명령과 **git commit -m "School works,,"** 명령을 통해 커밋한 뒤 **git push** 작업을 수행하였습니다.

결과 커밋 코드와 함께 성공적으로 Push 되었다는 내용이 출력됩니다.

### B) Github 결과
![img](../0803_Git생성및활용/17_resultOfThirdPush.PNG)
다시 Github project 창을 확인해 보니, 해당 작업 내용 역시 성공적으로 반영되었음을 커밋 메세지와 파일 내용을 통해 확인 가능합니다.

## 8. home 디렉토리에서 pull 작업 후 변경 내용 확인
### A) home 디렉토리 git pull
![img](../0803_Git생성및활용/18_secondPullOnHome.PNG "Pull on home")
터미널의 작업 공간을 *home* 디렉토리로 변경한 뒤, **git pull** 명령을 통해 원격지 저장소의 내용을 다시 내려받습니다.

### B) home 디렉토리 결과 창
![img](../0803_Git생성및활용/19_lastResult.PNG "Home result")
최종적으로 *home* 디렉토리 확인 결과 기존 파일들에서 *school* 디렉토리에서 변경한 내용으로 변경되어 있는 것을 확인 가능합니다.