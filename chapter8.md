## 📄 병합과 충돌

> **1. 병합**


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

> **4. 브랜치 삭제**
