## 📄 브랜치

> **1. 새로운 작업**

- **브랜치 작업**

  - **브랜치** : 프로젝트를 독립적으로 관리하는데 사용 (개발자는 항상 안정된 코드상태 유지,개발 중인 작업과 구분)
  
  - 깃 사용시 기존 코드와 분리해서 작업가능 

  - 가상의 작업 폴더, **공통된 커밋을 가리키는 지점**
<br>

- **브랜치 특징**

  - **가상 폴더** : 깃의 브랜치는 작업폴더를 실제로 복사하지 않고, 가상폴더에 생성 (물리적으로 복제된 구조보다 유연하게 처리 가능)
  
  - **독립적인 동작** : 브랜치 이용 시 원본 폴더와 분리하여 독립적으로 개발수행 가능(분리된 브랜치에서 명령만 수행하면 됨)
  
  - **빠른 동작** : 깃의 브랜치 기능은 다른 버전 관리 도구보다 가볍고, 브랜치 전환이 빠른 것이 특징
   
  - 깃의 Blob 개념을 도입하여 내부를 구조화(Blob는 포인트와 유사한 객체)
       
  - 브랜치 명령을 사용시 내부적으로 커밋을 하나 생성하여 브랜치
<br>

> **2. 실습 준비**

- **저장소 생성 및 초기화**

  - 초기화 명령어를 실행 시 저장소가 초기화되면 창에 현재 브랜치이름이 같이 출력

<img width="466" alt="new repository" src="https://user-images.githubusercontent.com/114068529/194824692-578513df-f2bc-4dd1-877e-1828a3b935e9.PNG">
<br>

- **기본 브랜치**

  - 깃은 최소한 브랜치가 1개 이상 필요 따라서 저장소를 초기화 시 master 브랜치 하나가 자동으로 생성
  
  - On branch master : 브랜치 작업 위치(깃에서는 항상 현재 작업하는 브랜치 위치를 확인하는것이 중요)

<img width="614" alt="original branch" src="https://user-images.githubusercontent.com/114068529/194825899-399caad2-a154-4103-8f92-0e98c0071bfa.PNG">
<br>

> **3. 브랜치**

- **브랜치 생성**

  - 브랜치 생성 : 기본적으로 제공되는 main 브랜치 이외에 사용자가 직접 정의한 **사용자 브랜치** 생성  
  
  - **git branch 브랜치이름 커밋ID** : 깃에서 또 하나의 **개발 분기점** 생성시 사용
  
  - 코드 저장후 커밋 하나 추가. 커밋이 있는 상태에서 새로운 브랜치 생성

  - 마지막 커밋ID(**100644**)를 기준으로 브랜치 생성 및 추가
  
![1](https://user-images.githubusercontent.com/115402800/194763878-fb857834-410d-47b6-90d6-05c101db517e.png)

<br>

- **브랜치 이름**

  - 브랜치 이름은 슬래시(/)를 사용, 계층적인 구조로 만들어서 사용 가능

  - 작성 규칙
 
  1) 기호(-), 마침표(.)로 시작 불가능
  
  2) 연속적인 마침표(..), 빈칸, 공백 문자, 물결(~), 캐럿(^), 물음표(?), 별표, 대괄호([]) 등은 포함 불가능
  
  3) 아스키 제어 문자는 포함 불가능
  
  - 📌 **브랜치 이름은 중복을 피해야 한다**
  
![2](https://user-images.githubusercontent.com/115402800/194763869-fcb091f3-206d-4d26-9e9c-08a03bc11cf4.png)
<br>

- **소스트리 브랜치**

  - 소스트리를 이용하여 새로운 브랜치 생성 
  
![3](https://user-images.githubusercontent.com/115402800/194763858-8f06e9c8-029f-421a-8825-89f54c2a301e.png)

![4](https://user-images.githubusercontent.com/115402800/194763856-5f278201-ef13-4d3f-934e-40d51755e14e.png)

  - 소스트리에서 **커밋을 선택**하여 브랜치를 생성하는 것은 **지정한 커밋을 기준으로 브랜치를 생성**한다를 의미
  
  - main의 최종 커밋(HEAD)을 기준으로 브랜치를 생성할 때는 **작업 사본 부모** 항목을 선택
  
  - 브랜치가 생성되고, 생성된 브랜치 feature로 ⚪ **마크**가 이동한 것을 확인할 수 있고, 이는 현재의 브랜치는 feature라는 것을 나타냄
    
  - 작업 사본 부모는 HEAD를 기준으로 생성하는 것이고, 명시적 커밋은 특정 커밋으로 브랜치를 생성하는 것
<br>

>**4. 브랜치 확인**

- **간단 브랜치 목록**

  - **branch 명령어는 단독으로도 실행 가능**
  
  - branch 명령어를 단독으로 입력하면 목록만 출력

  - git brach 명령어를 실행하면 현재 모든 브랜치가 나열되고  *표시가 된 브랜치로 자동으로 이동

  - *는 현재 선택된 브랜치를 의미한다.
  
![5](https://user-images.githubusercontent.com/115402800/194763843-3ebc8d94-3e4c-4386-a147-05c73683f33e.png)

<br>

- **브랜치 해시**

  - 브랜치는 특정한 **커밋의 해시 값(SHA1)** 을 가리킨다.
  
  - **git log** : 커밋의 해시 값(SHA1)을 확인 가능  
  
  - **git rev-parse footer(브랜치명)** :  footer 브랜치의 커밋 해시(SHA1)를 확인
  
  ![6](https://user-images.githubusercontent.com/115402800/194763822-fb07fd24-86a7-4d8d-af6c-646b646edb7d.png)
  
- **브랜치의 해시 값과 브랜치를 생성한 기준 커밋의 해시 값이 동일**

   - 브랜치가 커밋의 해시를 기준으로 생성된다는 것을 확인할 수 있다.
<br>

- **브랜치 세부 사항 확인**

  - git branch -v (-verbose) : 브랜치 이름, 커밋 ID, 커밋 메시지 등 상세한 출력 결과 확인 가능
  
![7](https://user-images.githubusercontent.com/115402800/194763813-c292010b-a8ea-4171-8531-9591791d7cd2.png)
<br>

> **5. 브랜치 이동**

- 브랜치를 생성했다고 해서 자동으로 생성된 브랜치로 이동하지 않는다.

- **checkout**

  - **git checkout 브랜치명** : 현재 브랜치를 떠나 새로운 브랜치로 이동

  - **git checkout -- 파일이름** : 파일로 체크아웃 (이중 대시(--)를 사용해 파일 이름을 정확히 지정하여 브랜치 변경 가능)
  
  - 주의점 : **깃은 하나의 워킹 디렉터리만 가지고 있다.**
  
    - 따라서 다른 브랜치에서 작업하기 위해 **브랜치를 변경하여 워킹 디렉터리 재설정 필요
  
![8](https://user-images.githubusercontent.com/115402800/194763799-e9f3904d-71ec-4b01-8757-36752435cd2c.png)


- 브랜치 목록을 확인해보면 별표가 footer 브랜치 이름 앞으로 변경된 것을 확인할 수 있다.

![9](https://user-images.githubusercontent.com/115402800/194763793-2166b485-8ce5-40d1-8f26-00a39c0db6ac.png)
  
<br>

- **브랜치 동작 원리**

- checkout 명령어로 브랜치가 변경되면 깃은 내부적으로 몇 가지 동작을 수행한다.

  - HEAD가 브랜치의 마지막 커밋을 의미해서 **브랜치가 이동되면 HEAD 포인터도 함께 이동**
  
  - 변경된 브랜치로 새로운 작업을 할 수 있도록 워킹 디렉터리를 변경
  
  - 브랜치를 변경하려면 기존 브랜치의 **워킹 디렉터리 정리** 필요
<br>

- **소스트리**

- 소스트리에서 브랜치를 변경하기 실습

  - 현재 브랜치 위치를 main 브랜치로 변경하기

  - main 브랜치로 변경되면 main 브랜치 앞으로 ⚪ 마크가 이동

![10](https://user-images.githubusercontent.com/115402800/194763777-6690eebc-d7ca-446d-b344-7d4498853eb2.png) ![11](https://user-images.githubusercontent.com/115402800/194763767-f572b18a-78dd-4aac-95ed-5f8bd2a266c5.png)
<br>

- **이전 브랜치**

- 리눅스에서 **대시(-) 기호는 이전 디렉터리를 의미**

  -  **git branch -v** 명령어를 실행해 footer 브랜치에서 main 브랜치로 변경합니다.
  
![12](https://user-images.githubusercontent.com/115402800/194763751-26ceb827-31a0-4d34-8be5-c89b880c3052.png)

  - **git checkout -** : 이전 브랜치로 이동 
  
![13](https://user-images.githubusercontent.com/115402800/194763741-0dcce79c-a9d8-4ba7-8202-da23667e01e5.png)

- 이전 브랜치인 footer 브랜치로 되돌아간 것을 확인 가능 
<br>

- **워킹 디렉터리 정리**

- 1) main 브랜치에서 코드를 수정하기 위해 체크아웃을 사용하여 브랜치를 이동한다.
  
  - 현재작업하고 있는 워킹 디렉터리를 먼저 정리하기!

  - 📌 저장하지만 **커밋은 하지 않는다**

![14](https://user-images.githubusercontent.com/115402800/194763708-e4fe9eea-063d-4add-a990-6663811d014e.png)

- 2) status 명령어로 확인

![15](https://user-images.githubusercontent.com/115402800/194763696-cdc33bf7-ccea-4f86-bead-63974e1c7243.png)

- 3) 현재의 상태에서 브랜치를 footer로 변경

![16](https://user-images.githubusercontent.com/115402800/194763681-336546a2-94c1-4005-83f7-c35da751635e.png)

- 깃은 향후 **충돌을 방지하려고 워킹 디렉터리에 작업이 남아 있다면 경고 메시지를 보여 주고 브랜치를 변경할 수 없게 제한** 

  - 브랜치 간에 정상적으로 이동하려면 남은 작업들 정리 필요  
  
  - 이전으로 돌아가 수정된 내용을 커밋
  
![17](https://user-images.githubusercontent.com/115402800/194763669-f73b8750-901c-4b6a-a14c-aed283c32b9a.png)
<br>

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

  6장에서는 브랜치의 개념과 브랜치 생성부터 이동, 작업방법, 삭제까지 전반적인 내용을 담았습니다.

  - 브랜치는 기존의 코드를 분리하고, 분리된 브랜치는 서로 간섭없이 별개 작업을 수행할 수 있습니다.

  - 다른 개발자와의 협업을 통해 프로젝트를 진행하고, 분리된 코드를 병합 할 수도 있습니다.
