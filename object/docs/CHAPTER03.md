# 오브젝트 - 3장 <역할, 책임, 협력>
- 객체지향 패러다임의 관점에서 핵심은 `역할(role), 책임(responsibility), 협력(collaboration)`이다.
- 클래스, 상속, 지연 바인딩도 중요하지만 구현 측면에 치우쳐 있기 때문에 객체지향 패러다임의 본질과는 거리가 멀다.

## 목차
1. 협력(collaboration)
2. 책임(responsibility)
3. 역할(role)

## 이번 장의 목표
- 객체지향 패러다임의 핵심인 `역할(role), 책임(responsibility), 협력(collaboration)`을 이해한다.


## 읽으면서 쓴 단어들
1. 협력
> #객체 #협력 #상호작용 #책임 #역할
> #객체는 사회적인 존재다. #메시지 #전적으로 위임 #스스로 선택
> #상태 #행동 #문맥

2. 책임
> #하는 것(doing) #아는 것(knowing)
> #정보 전문가 #책임 주도 설계 #데이터 주도 설계

3. 역할
> #책임 #동일한 책임 #슬롯 #추상화  
> #불필요한 코드 중복을 제거하는 근거

## 정리
0. 도입부
- 객체지향의 본질은 협력하는 객체들의 공동체를 창조하는 것이다.
- 객체지향 설계의 핵심은 협력을 구성하기 위해 적절한 객체를 찾고 적절한 책임을 할당하는 과정에서 드러난다.
> 애플리케이션의 기능을 구현하기 위해 어떤 협력이 필요하고 협력을 위해 어떤 역할과 책임이 필요한지 고민해보자.

1. 협력
- 객체들이 애플리케이션의 기능을 구현하기 위해 수행하는 상호작용을 `협력`
- 객체가 협력에 참여하기 위해 수행하는 로직을 `책임`,
- 객체들이 협력 안에서 수행하는 책임들이 모여 객체가 수행하는 `역할`을 구성
- 1장부터 일관성있게 저자가 주장해오던 자율성을 강조하는 것같다.
- 구현하고 싶은 애플리케이션이 있으면 객체 간의 협력 관계를 설계하다보면 자연스럽게 행동과 상태가 나온다.
  - 이는 구현에서 클래스와 멤버 변수와 밀접한 연관이 있다.

> 역시 여기서도 객체의 자율성을 강조하는구나!!  
> 자율성이 훼손되는 것이 가장 큰 문제라고까지 말하고 있어

2. 책임  
책임: 협력에 참여하기 위해 객체가 수행하는 행동
- 적절한 협력 -> 적절한 책임 -> 적절한 객체에 할당
- 객체지향 설계에서 가장 중요한 것은 책임이다.
- 객체의 구현 방법은 책임을 결정한 다음 고민해도 늦지 않다.
<br><br>
- 메시지가 객체를 결정한다.
  - 어떤 객체의 책임은 객체로부터 나오는 것이 아니라
  - 메시지가 객체를 선택하고 그것으로부터 객체의 책임이 나오는 것이다.

- 행동이 상태를 결정한다.

> 메시지가 가장 자아가 있는 아이인 것처럼 느껴졌다.  
> 메시지가 객체를 선택하는 기준은 정보 전문성이라고 봐도 되는 걸까?  
> 나는 `메시지`를 함수의 이름 정도로 생각하고 이 메시지가 객체를 결정한다,  
> 그 함수가 기능을 하기 위해 필요한 변수들을 `상태`정도로 생각했다.

3. 역할  
역할: 객체가 어떤 특정한 협력 안에서 수행하는 책임의 집합
- ㅁ

> 역할은 한 클래스에서 함수들의 집합으로 생각했다.  
> 역할을 나누고 다른 객체에 도움을 요청...
> - 내가 할 수 있을까? 예를 들면 Movie에서 DiscountPolicy에 요청.. DiscountPolicy를 생각하지 못했다면?
> - DiscountPolicy라는 객체를 만든 근거는..?

> `역할은 다른 것으로 교체할 수 있는 책임의 집합이다[Wirfs-Brock03]`  
> `역할이 다양한 종류의 객체를 수용할 수 있는 일종의 슬롯이자 구체적인 객체들의 타입을 캡슐화하는 추상화`
> - 슬롯은 바꿔 끼울 수 있는 것! 다형성과 밀접한 관련이 있다! *시오 짱!*



## 새롭게 다가온 부분
- p.77
  - 객체의 행동을 결정하는 것이 협력
  - 객체의 상태를 결정하는 것은 행동
  - 객체의 상태는 그 객체가 행동을 수행하는 데 필요한 정보가 무엇인지로 결정
- > 이 부분을 어떻게 코드에 녹여낼 수 있을까?  
  > 이 다음 줄을 읽으니까 이해가 되는 것같다!

- p.79
  - 객체는 자신이 맡은 책임을 수행하는 데 필요한 정보를 알고 있을 책임이 있다.
  - 또한 객체는 자신이 할 수 없는 작업을 도와줄 객체를 알고 있을 책임이 있다.
- > Movie가 calculateMovieFee 메시지를 수신할 수 있고 fee와 discountPolicy를 속성으로 가지는 이유  
  > Screening이 movie를 인스턴스 변수로 포함하는 이유

- p.88
  - AmountDiscountPolicy 객체와 PercentDiscountPolicy 객체가 참여하는 협력을 개별적으로 만들지 않는 근거
- > 객체가 아닌 책임에 초점을 맞춘다.  
  > 책임의 관점에서 두 협력을 바라보면 할인 요금 계산이라는 `동일한 책임`을 수행

- p.89
  - 역할을 구현하는 가장 일반적인 방법은 `추상 클래스`와 `인터페이스`를 사용하는 것이다.
  - 책임의 집합!


> 저자가 영화 예매 시스템에서 DiscountPolicy는 추상 클래스로, DiscountCondition은 인터페이스로 구현한 근거
> - DiscountPolicy는 역할을 수행할 수 있는 모든 객체들이 공유하는 상태와 행동의 기본 구현이 존재
> - DiscountCondition은 공통의 구현이 필요없고 단지 책임의 목록만 정의


- 정보 전문가


## 개념
- 책임 주도 설계(Responsibility-Driven Design, RDD)
  - 책임을 찾고 책임을 수행할 적절한 객체를 찾아 책임을 할당하는 방식으로 협력을 설계하는 방법
  1. 시스템이 사용자에게 제공해야하는 시스템 책임을 파악한다.
  2. 시스템 책임을 더 작은 책임으로 분할한다.
  3. 분할된 책임을 수행할 수 있는 적절한 객체 또는 역할을 찾아 책임을 할당한다.
  4. 객체가 책임을 수행하는 도중 다른 객체의 도움이 필요한 경우 이를 책임질 적절한 객체 또는 역할을 찾는다.
  5. 해당 객체 또는 역할에게 책임을 할당함으로써 두 객체가 협력하게 한다.

## 한 줄 정리
> Object is FREE
+ 의식하면서 코드에 적용하려고 하다보면 억지로 끼워맞춰서 구현을 하게될 수도 있을 것같다는 생각이 들었다.  
+ 시뮬레이션을 통해 체화를 시키는 과정이 필요할 것같다.