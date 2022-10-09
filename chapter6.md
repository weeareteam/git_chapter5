## 📄 브랜치

> **1. 새로운 작업**

> **2. 실습 준비**

> **3. 브랜치 생성**

> **4. 브랜치 확인**

> **5.브랜치 이동**

> **6.브랜치 공간**

- **git log --graph --all** : 현재까지 작업한 로그 기록 확인 및 브랜치 흐름 보기

  - **git show-branch --more=숫자** :  출력될 커밋 개수 제한 

<img width="717" alt="git log --graph --all" src="https://user-images.githubusercontent.com/114068529/194696589-5ec21fe4-a911-4792-9341-1e93b6360c16.PNG">

- 브랜치를 이동하면 변경된 각자 브랜치의 마지막 워킹 디렉토리 상태로 변경 (브랜치에 따라 두 파일의 차이 확인 가능)

<img width="539" alt="브랜치 소스 확인" src="https://user-images.githubusercontent.com/114068529/194696727-470b9bb8-dc5e-4077-bc7b-01c5acee2cf2.PNG">
<br>

> **7.HEAD 포인터**

- **마지막 커밋**

  - HEAD : 작업 중인 브랜치의 마지막 커밋 아이디를 가리키는 참조 포인터

  - git은 HEAD를 부모 커밋으로 대체하여 사용
  
  - 현재 작업하는 브랜치를 가리킴
  
  - 다양한 명령어를 입력할 때 기준점으로 사용
<img width="719" alt="마지막 커밋" src="https://user-images.githubusercontent.com/114068529/194696852-10e53ed2-0bc3-4c61-ac2b-53f97acb5ca3.PNG">
<br>

- **브랜치 HEAD**

  - 브랜치 이동 시 head 포인트도 이동

  - 각각의 브랜치마다 마지막 커밋이 다르기 때문 

  - 위의 footer 브랜치와 비교했을 때 HEAD 위치 변화를 확인 가능
<img width="643" alt="브랜치 HEAD" src="https://user-images.githubusercontent.com/114068529/194696942-b6585365-036f-4a23-bdd5-3e9384a27fda.PNG">
<br>

- **상대적 위치**

  - 상대적 커밋 위치를 지정 시 ^(~)를 사용

  - HEAD를 기준으로 몇 번째인지 상대적 위치 지정
  
  - ex) HEAD^ : HEAD 포인터 바로 이전의 커밋을 가리킴

  - ex) HEAD^^^(=HEAD^3) : HEAD 기준으로 3개 전 커밋을 가리킴
<br> 

- **AHEAD, BHEAD** 

  - 원격 저장소를 연동해 git 관리시 브랜치마다 HEAD 2개 존재 (로컬 저장소 HEAD, 원격 저장소 HEAD)

  - 원격 저장소와 로컬 저장소는 물리적으로 다르기 때문에 마지막 커밋 위치가 서로 다를 수 있음 <br>
  
    (= 서로 다른 커밋을 가리키는 HEAD 포인터를 가짐)
    
  - AHEAD : 서버로 전송되지 않은 로컬 커밋이 존재  **-->** 로컬 브랜치에 있는 커밋 개수 > 원격 커밋 개수

  - BHEAD : 로컬 저장소로 내려받지 않은 커밋 존재  **-->** 로컬 브랜치에 있는 커밋 < 원격 커밋 (= 원격이 로컬보다 최신)
<br>

> **8.생성과 이동**

- **자동 이동 옵션**

  - git checkout -b 브랜치 이름 : 브랜치 생성과 이동을 동시에 실행 
  
<img width="537" alt="git checkout-b" src="https://user-images.githubusercontent.com/114068529/194697586-68282ab9-a827-4843-96c6-093b512b2aa0.PNG">
<br>

- **커밋 이동**

  - 브랜치 이름 = 커밋 해시키 

  - 브랜치 이름 대신 커밋 해시키를 통해 checkout 가능
  
<img width="729" alt="커밋 이동" src="https://user-images.githubusercontent.com/114068529/194697663-19ee5949-2fab-4dbb-9f94-a576dc1d3e5e.PNG">
<br>

- 돌아오기 

  - git checkout - : 다시 현재 시점으로 체크아웃 
<img width="537" alt="git checkout -" src="https://user-images.githubusercontent.com/114068529/194697718-b6cba186-7037-4507-b760-1d84abff4182.PNG">
<br>

> **9.원격 브랜치**

> **10.브랜치 전송**

> **11.브랜치 삭제**
   
   - 먼저 현재 자신이 있는 브랜치는 삭제할 수 없습니다.
   - git branch -d +<b>현재있는 브랜치</b> = 자신의 브랜치 삭제
<img width=500 alt="오류 사항" src="https://user-images.githubusercontent.com/101091207/194764475-a1344a69-f62d-4be4-85eb-e8d32c5dc474.png">
  
  - 일반적인 삭제 방법 (스테이지가 깔끔한 상태에서만 삭제를 허용합니다!)
  -git branch -d +<b>삭제할 브랜치 이름</b> = 병합되지않고, 스테이지가 깔끔한 브랜치 삭제
<img width=500 alt="일반적인 상황" src="https://user-images.githubusercontent.com/101091207/194764613-acfdd7e3-f41e-4baa-a880-fde17ecf0ae9.png">

  - 강제로 삭제하기(워킹 디렉토리 또는 추가 커밋 작업이 있으면 삭제가 되지않아서 이럴 경우 사용합니다)
  - git branch -D <b>+삭제할 브랜치 이름</b> = 대문자 D를 통해 강제 브랜치 삭제
  <img width=500 alt="강제삭제" src="https://user-images.githubusercontent.com/101091207/194765012-e2df9639-5c05-41e7-a9c7-83c22b4632ba.png">
  
  - 소스트리에서 삭제하는 방법
  - 삭제할 브랜치 우클릭 후 feature 삭제 메뉴 클릭 =소스트리에서의 브랜치 삭제
 <img width=500 height=300 alt="소스트리 삭제" src="https://user-images.githubusercontent.com/101091207/194765324-b54ccecd-673e-4366-8cd9-374ba3d00540.jpg">
 
 - 리모트 브랜치 삭제하는 방법
 - git push origin -- delete <b>+리모트 브랜치 이름</b>
<img width=500 src="https://user-images.githubusercontent.com/101091207/194765722-cf1c59e2-174d-4bc4-9f8f-d22b78fa8746.png">
<br>

> **12. 정리**

  - 6장에서는 브랜치의 개념과 브랜치 생성부터 이동, 작업방법, 삭제까지 전반적인 내용을 담았습니다.

  - 브랜치는 기존의 코드를 분리하고, 분리된 브랜치는 서로 간섭없이 별개 작업을 수행할 수 있습니다.

  - 다른 개발자와의 협업을 통해 프로젝트를 진행하고, 분리된 코드를 병합 할 수도 있습니다.
