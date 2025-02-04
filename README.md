<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=cylinder&color=0:be2727,100:502a2a&text=엽기떡볶이&section=header&fontAlignY=48&fontSize=60&height=150&animation=blinking&desc=불닭발%20동대문%20엽기%20떡볶이&descAlignY=76&fontColor=f7cdcd" />
</p>
<br>

## 📚 프로젝트 주제
엽기 떡볶이 배달 어플<br>
1주차 과제 레포지토리입니다.

<br>

## 📜 사용자 메뉴얼
1. 사용자 정보 입력
   - 이름<br>
     ❗️ 예외 상황 : 영어 또는 한글을 제외한 다른 문자일 때 재입력
   
   - 전화번호<br>
     ❗️ 예외 상황 : 숫자, '-'가 아니거나 전화번호가 9자리 미만, 12자리 초과일 시 재입력
   - 카드 잔액<br>
     ❗️ 예외 상황 : 0 미만의 숫자, 숫자가 아닌 문자일 때 재입력
   - 배달 주소<br>
     ❗️ 예외 상황 : 영어, 숫자, 한글을 제외한 다른 문자를 포함할 때 재입력

2. 주문 동의 받기<br>
   ❗️ 예외 상황 : 1, 2 외 다른 숫자나 문자 입력 시 재입력
   1. [1: 예]를 선택하면 다음 3번으로 넘어감
   2. [2: 아니오]를 선택하면 어플을 종료한다는 문구와 함께 프로세스가 종료됨

3. 메뉴 선택
   1. 떡볶이를 선택하였을 경우 추가 선택 진행
      - 매운맛 정도
      - 토핑 선택 최대 3회<br><br>
   2. 사이드를 선택하였을 경우 추가 선택 없음<br>

4. 장바구니 담을지에 대한 여부 선택<br>
   1. [2: 메뉴 다시 담기]를 선택하면 3번 과정으로 돌아감

5. 추가 주문 여부 선택<br>
   1. [1: 예]를 선택하면 3번 과정으로 돌아감
   2. [2: 아니오]를 선택하면 장바구니 목록 출력
  
6. 결제 여부 선택<br>
   1. [1: 예]를 선택하면 결제가 완료되었다는 문구 출력 후 2번으로 돌아감
   2. [2: 아니오]를 선택하면 별도의 문구 출력 없이 2번으로 돌아감
   
❗️ 3번 이후의 공통 예외 상황 : 선택해야 하는 범위의 숫자를 넘어선 숫자나 문자를 입력할 때 재입력 요청

<br>

--- 

<br>

## 👀 실행 결과
![Image](https://github.com/user-attachments/assets/54d3e93e-964b-4aa5-88ca-81a3201b490a)

<br><br>

## 📊 클래스 다이어그램
![Image](https://github.com/user-attachments/assets/cc464b33-2ca8-4967-adce-ccd007d843f9)

<br><br>

## 🤔 설계 및 구현 과정
1. 대충 로직 생각하기
   ![Image](https://github.com/user-attachments/assets/f30bb36c-872c-4bbe-a372-7520aa8a5a4f)
   근데 여기 있는 거 다 하면 진짜 너무 복잡할 것 같아서 몇 개 지우면서 설계해 나갔다.
   
3. 사용자의 선택 시 조건문 없이 객체를 생성하고 반환하는 방법에 대한 자료 조사<br>
   "인터넷에 조건문 없이 선택을 가능하게 하는 디자인 패턴" 이라고 검색했을 때 "전략 패턴"이 많이 나왔다. 하지만 내가 원하는 게 아니었고 작년에 학교에서 수강한 "객체지향설게와패턴"이라는 강의 교안을 가볍게 넘겨보다가 "팩토리 패턴"을 보고 검색했다.

   https://jusungpark.tistory.com/14<br>
   위 사이트에서 어느 정도 원하는 디자인 패턴의 구현 방식을 볼 수 있었으나 조건문을 최소화하여 구현하고 싶었기 때문에 결국 ChatGPT를 조금 사용하였다.
   조건문을 최소화하여 구현하고 싶었던 이유는 강의 중 SOLID, 그 중 OCP원칙을 많이 강조하셨고 switch문이 가장 안 좋다고 말씀해주셨던 기억이 강하게 남아있었기 때문이다.

4. 클래스 다이어그램, 정확히 어떻게 그려야 할까?<br>
   https://velog.io/@codemcd/%EC%9A%B0%EC%95%84%ED%95%9C%ED%85%8C%ED%81%AC%EC%84%B8%EB%AF%B8%EB%82%98-%EC%9A%B0%EC%95%84%ED%95%9C%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5-%EC%9D%98%EC%A1%B4%EC%84%B1%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%B4-%EC%84%A4%EA%B3%84-%EC%A7%84%ED%99%94%EC%8B%9C%ED%82%A4%EA%B8%B0-By-%EC%9A%B0%EC%95%84%ED%95%9C%ED%98%95%EC%A0%9C%EB%93%A4-%EA%B0%9C%EB%B0%9C%EC%8B%A4%EC%9E%A5-%EC%A1%B0%EC%98%81%ED%98%B8%EB%8B%98-vkk5brh7by<br>
   위 벨로그를 통해 우아한 형제들에서 배달의 민족 구현에 적용한 클래스 다이어그램을 확인할 수 있었다.

   ![Image](https://github.com/user-attachments/assets/dc3b1c88-307a-4253-a18f-94cce53dc8b1)
   필요한 클래스를 러프하게 그려보고 연결하였다.
   
5. 구현<br>
   클래스부터 냅다 생성했다. 프론트 구현할 때는 그렇게 해본 적이 없긴 한데 1주차 과제를 하면서 어떤 클래스가 필요한지 전부 써놨기 때문에 전체 80% 정도는 먼저 생성해놨다.
   클래스부터 냅다 전부 생성하는 게 좋은 건지 아니면 하나씩 구현하고 끝나면 다른 클래스 구현을 들어가는 게 좋은 건지 모르겠지만 설계의 영향이 확실히 있는 갓 같다.

   User클래스, Menu 패키지 내에 있는 클래스, Order 순서로 구현을 진행하였다.
   Order 클래스에서 어떻게 객체지향을 적용해야 할지 잘 모르겠어서 Factory 클래스들을 전부 작성한 후 Order에서 구현하려던 Payment로 쪼개 구현하였다.

6. 디버깅 이후의 구현<br>
   몇 번의 디버깅을 하면서 필요한 기능들이 몇 가지 더 보였다.

   우선 Order 클래스에 있던 Cart 클래스를 내용을 분리하였다. Order에 너무 많은 책임이 있어 보였기 때문..<br>
   결제 관련해서도 사용자에게 안내문이나 결과를 출력하는 부분도 필요해 보였다.<br>
   Order 클래스가 중재자 마냥 많은 책임을 떠안은 느낌이 있지만 (특히 order()함수) 사실 어떻게 해결해야 할지 몰라서 최대한 Payment, Cart 등 클래스를 나누려 하였다.

   또한 메뉴얼에 적힌 대로 입력하지 않을 경우애 대비하여 예외처리를 진행하였다.
   특히 결제에서 필요한 예외처리가 살짝 머리를 아프게 했지만 어쩔 수 없기 조건문을 사용하여 구현하였다.

7. 리팩토링<br>
   마지막 단계의 구조 수정도 리팩토링이라 보는 게 맞는지는 모르겠지만... (기능 변화 없으니 대충 리팩토링이라고 보겠다.)<br>
   Scanner나 예, 아니오 선택하는 부분에서 중복되는 코드가 많아보여 InputScanner와 InputCheck 클래스를 구현하였다.<br>
   여기 저기 많았던 Scanner 객체 호출을 InputScanner를 통해 싱글톤으로 구현하였고
   InputCheck 클래스 덕에 InputScanner 호출도 대부분 InputCheck 클래스에 모였다.
   그리고 결제 부분에서 계속 한두 개씩 추가 수정이 필요한 부분들이 보여 수정함.


## 💡 회고
클래스 다이어그램을 설계하는 데 생각보다 오래 걸렸다. 근데 그걸 설계하니 기본적인 기능들 구현하는 틀은 정말 빨리 끝난 기분이었다. 이게 바로 설계의 힘?<br>
연휴에 수강해야 하는 강의와 시기가 겹치다 보니 정신이 없었던 것도 있고 '클래스부터 나열해 보자' 하는 생각까지도 시간이 오래 걸렸다. (어떻게 해야 할지 감이 아예 안 왔던..)
그래서 클래스부터 나열하고 상속 관계만 나열 후 구현을 시작했다. 

사실 구현에 들어가서도 살짝 어디서부터 어떻게 시작해야 할지 막막했다. 그러다가 만만한 User부터 건들고 Order 쪽과는 의존성이 아주 낮을 Menu부터 구현을 시작하였다.
하지만 몇 가지 잘 모르겠는 점은 Factory 클래스들의 위치가 order 패키지가 맞는지에 대한 의문이었다. 사실 팩토리 클래스들의 객체 호출을 거의 order 쪽에서 해서 떡볶이에서 호출하는 SpicyLevelFactory를 제외하고는 전부 order에 넣긴 했는데 이런 구조적인 것도 나한텐 좀 어렵다.<br>
그리고 내가 구현한 게 객체지향적인지도 모르겠다. 이 과제의 구현물이 어느 수준의 개발인지 궁금하다. 거의 처음이니 어느 수준인지 객관화도 안 됨.. 하하

Menu쪽에서 Map을 사용해 Factory 클래스 만드는 걸 한 번 터득하니 너무 편했다.<br>
4번 과정에서 중간에 NoTopping이라는 클래스를 추가하였는데 OCP 원칙을 확 체감할 수 있었다.<br>
그리고 리팩토링 과정에서 InputCheck에 예외처리 함수 추가하면서 구조를 변경했는데 각 클래스의 가독성이 확 올라가는 걸 느꼈다.

CLI 프로그램을 구현한 게 거의 3년 만인 것 같은데 객체 지향을 적용해서 하려고 한 건 또 처음이라 쉽지 않았지만 재미있었다.<br>
3년 전에 한 것도 간단하게 학교에서 c++이용해서 간단하게 만들어라 하는 거였는데 c++을 배웠지, 객체지향을 배우진 않았어서 Main에 절차지향으로 전부 때려박았다.
그때는 코딩이라는 거 자체에 겁도 먹었던 시기인데 지금은 그 정도는 아니어서 다행이다.
어쩌면 정말 백엔드가 나한테 더 맞을지도? 물론 백엔드에 이 과제가 얼마나 차지하는지는 모르겠지만 처음 하는데 이 정도 재미면 앞으로가 기대된다.

아무튼 정말 어제 오늘 거의 내내 밤샐 정도로 재미있는 과제였다.<br>
계속 이렇게 구현하는 과제가 있으면 좋겠다.<br>
다만 언제까지 이렇게 난 느릴까 계속 생각하게 되는 날의 연속이라 혼란스럽기도..~
