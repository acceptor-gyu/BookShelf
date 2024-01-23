# 오브젝트 - 1장 <객체, 설계>

## 목차
1. 티켓 판매 애플리케이션 구현하기
2. 무엇이 문제인가
3. 설계 개선하기
4. 객체지향 설계

## 읽으면서 쓴 단어들
1. 티켓 판매 애플리케이션 구현하기
- 1장의 첫 번째 인덱스는 목차 제목 그대로 티켓 판매 애플리케이션을 구현하는 사고 과정과 코드였다.
> 생략

2. 무엇이 문제인가 
> #메소드의 주체와 객체 #상식적인 동작을 하는 코드 #변경하기 쉬운 코드 #의존성 #결합도

3. 설계 개선하기
> #직접 접근 #정보 차단 #자율성 #캡슐화 #응집도 #트레이드오프 #책임

4.
>

5.
>



## 정리
0. 들어가며 <프로그래밍 패러다임>
로버트L. 글래스(Robert L. Glass)는 이론보다 실무가 먼저라고 말했다.
> 프로그램을 만들다 보니 유지보수하기 쉬운 코드를 만들고 싶어졌고 많이 나오는 패턴들을 디자인 패턴이라는 이론으로 만든...
- 이런 것들이 글래스가 말한 이론보다 실무가 먼저라고 말한 거 아닐까? 라는 생각이 들었고 공감이 되었다.

1. 티켓 판매 애플리케이션 구현하기
> 생략

2. 무엇이 문제인가
- 메소드의 주체와 그 동작을 당하는 객체를 생각도서 상식적인 동작을 하는 코드를 작성해야 읽는 사람과 의사소통을 할 수 있다.
- 한 클래스가 다른 클래스의 내부에 대해서 많이 알게 될수록 의존성(dependency)가 높다고 말할 수 있다.
- 의존성은 코드의 확장, 축소 등과 같은 변경과 관련이 있는데 의존성이 높을수록 해당 객체가 의존하는 다른 객체들도 변경될 수 있다.
- 객체지향 프로그래밍 및 설계는 객체들의 상호작용을 통해 구현하는 것이므로 의존성을 없앨 수는 없기 때문에 최소한의 의존성만 가지고 구현하는 것이 목표가 될 수 있겠다.
> 객체들간의 의존성이 높을수록 결합도(coupling)이 높다고 하며 결합도를 낮춰 변경에 용이한, 유지보수하기 쉬운 코드를 작성할 수 있으면 좋겠다.

3. 설계 개선하기




> 1장을 마치며
> - 어떻게 하면 유지보수하기 편하게 설계할 수 있는지 설명하는 장인 것같다.