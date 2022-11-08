## 📄 병합과 충돌

> **1. 병합**
- 분리된 브랜치를 한 브랜치로 합치는 작업
- 실습준비
	- 작업공간 생성
	<img width="560"  src="https://user-images.githubusercontent.com/101091207/200317441-d6f57a83-c351-40e9-bb4b-d3fb2b755953.png">
	
	- index.htm 파일 작성
	<img width="560" src="https://user-images.githubusercontent.com/101091207/200317957-ae99edb2-e23f-4701-a60d-6134ecc0401e.png">
	
	- 커밋
	<img width="560" src="https://user-images.githubusercontent.com/101091207/200318922-52bb4f8b-fd20-4b48-8c9c-38a43b428c89.png">
> **2. Fast-Forward 병합**

- 순차적 커밋에 맞추어 병합을 처리하는 방법

- 브랜치 생성과 수정 

  - **git rev-parse [브랜치명]** : 포인터(커밋이력)를 확인 
  
  <img width="596" alt="git rev-parse" src="https://user-images.githubusercontent.com/114068529/199978570-d7a64ce3-935c-4f8d-8621-5086f8143d13.PNG">
  <br>
  
  -  브랜치 경로가 일직선으로 1개 있는 것을 확인 가능 
  
  <img width="596" alt="git log --oneline" src="https://user-images.githubusercontent.com/114068529/199979023-f4f536c0-fd3a-4398-adb5-0104912aacba.PNG">

  ⭐ **해당 모양의 브랜치에서 병합 작업 시 Fast-Forward 알고리즘 적용**
<br>

- **병합 위치** 

  - **git merge [브랜치명]** : 현재 브랜치를 기준으로 다른 브랜치의 모든 커밋을 병합 

  - Fast-Forward 병합 : 작업한 브랜치의 시작 커밋을 원본 브랜치 이후의 커밋으로 가리킴 
  
  - = 병합할 하나의 브랜치 파일을 기준 브랜치로 복사하여 수정된 파일을 원본에 그대로 적용 

  - 원본에 추가된 내용이 없다는 가정하에 변경한 파일 대체
<br>

- **git merge 후 상태변화**

  - **BEFORE** 
  <img width="368" alt="git log 그래프 병합 전" src="https://user-images.githubusercontent.com/114068529/199980444-f8a869a0-f90b-4666-8ecb-e48a2ef06a59.PNG">

  - **AFTER**
  <img width="540" alt="병합 후 변화" src="https://user-images.githubusercontent.com/114068529/199980482-100d2e7a-d809-4c8d-a149-029c2fec0794.PNG">
<br>

> **3. 3-way 병합**

- **브랜치 생성과 수정 작업**

- **마스터 변경**

- **공통 조상**

  - 두 브랜치를 병합하려면 먼저 분할인 공통 커밋을 찾아야 함(=공통 조상 커밋)
  
  - 공통 조상 커밋을 포함하는 브랜치와 새로운 두 브랜치를 3개를 하나로 병합해야함(=3-way병합)
  
  - 깃은 3-way 병합을 할 때 공통 조상 커밋을 자동으로 찾아줌
  
  - 그래서 다른 VCS들 보다 서로 다른 브랜치를 편리하게 병합가능한 것이 깃의 장점
<br>

- **병합 커밋**

  - 3-way 병합은 두 브랜치에서 공통 조상 커밋을 자동으로 찾아주며, 공통 조상 커밋을 기준으로 병합
  
  - 병합을 성공적으로 완료한 후에는 새로운 커밋을 추가로 하나 생성 (새로 생성된 커밋 = **병합 커밋**)

  - 병합 커밋 특징 : 부모 커밋이 2개임 ex)	브랜치 A(부), 브랜치 B(부)
<br>

- **병합 메시지**

  - 3-way 병합은 Fast-Forward 병합과 달리 병합 메시지가 필요 (깃은 두 브랜치를 병합한 후에 새로운 커밋을 하며 동시에 메시지 자동생성)
  
  - **git merge [브랜치이름] --edit** : 자동으로 작성되는 메시지 외에 직접 커밋 메시지를 작성가능
	
  - **git reset --hard head^** : 바로 앞의 병합 취소
<br>

> **4. 브랜치 삭제**

- **병합 후 삭제**

  - **git branch -d [브랜치이름]** : 병합을 완료한 브랜치 삭제 
  
  - **git branch -D [브랜치이름]** : 병합을 완료하지 않은 브랜치 삭제

  <img width="596" alt="git branch -d" src="https://user-images.githubusercontent.com/114068529/200566316-57f7fa82-f73b-4902-ae58-df33414cd77a.PNG">
