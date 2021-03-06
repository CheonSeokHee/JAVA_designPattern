# JAVA_designPattern
자바 디자인패턴 인프런 강의 공부ing


# --------------생성 패턴------------

builder 패턴
- 어떤 구조를 가지고 있는 큰것을 구축해 나간다.
  각 부품을 하나씩 만들어가는 방식
- 객체를 생성하는 방법과 구현하는 방법을 분리함
- 코드/읽기, 유지보수에 용이
- 객체 생성을 깔끔하게 가능
ex)setXXX 이런식으로 인수를 부여해 직관적이고 개발하기 용이


factoryMethod 패턴
- 상위 클래스에서 객체를 생성하는 인터페이스를 정의 후 하위에서 인스턴스를 생성하는 방식
  상위에선 인스턴스를 만드는 방법만 결정하고, 하위에선 그 데이터의 생성을 책임지고 조작하는
  함수들을 오버로딩 하여 인터페이스와 실제 객체를 생성하는 클래스를 분리하는 구조


prototype 패턴
- 원형을 만들어 놓고, 복사한 후 필요한 부분만 수정하여 사용
- 기존 객체를 복제함으로써 객체를 생성
 
abstract Factory 패턴
- 구체적인 클래스에 의존하지 않고, 서로 연관 되거나 의존적인 객체들의 조합을 만드는 인터페이스를
   제공하는 패턴
- 동일한 주제의 다른 팩토리 묶음


singleton 패턴
-private 으로 외부 접근 제한
- 전역 변수를 사용하지 않고 하나의 객체만 생성하여 참조할 수 있도록 하는 구조
- 한 클래스에는 한 객체만 존재
- 사전:Eager- 클래스 로딩 시 인스턴스 생성 , 늦:lazy - 실제 사용시 인스턴스 생성 방법
- 최초 한번의 new 연산자를 통해서 고정된 메모리 영역을 사용하기 때문에 추후 객체 접근 시 메모리 낭비 방지
- 다른 클래스 간에 데이터 공유가 쉽다
- 동기화 문제를 해결해야하고 테스트하기가 어렵다.


# --------------구조 패턴--------------

bridge 패턴
- 기능 / 구현 의 클래스 계층을 연결 후 구현부에서 추상 계층을 분리하여 추상 부분과 실제 구현 부분을
   독립적으로 확장할 수 있는 구조
- 구현, 추상 모두 변경 해야할 시 활용



decorator 패턴
- 기존에 구현되어 있는 클래스에 필요한 기능을 추가하여 수정하고 조합해 나가는 패턴
   객체 간의 결합을 통해 동적으로 유연하게 확장 해줌
- but 클래스가 많아질 수 있다는 단점



facade 패턴
- 복잡한 시스템에 단순한 인터페이스를 제공 시스템간 결합도를 낮추어 시스템 구조에 대한 파악가능
  오류에 대해서 단위별로 확인 가능
- 통합된 인터페이스 제공


flyweight 패턴
- 클래스 경량화가 목적
- 가상 인스턴스로 메모리 절감


proxy 패턴
- 실제 객체에 대한 대리 객체 
- 실제 객체에 대한 접근 이전에 필요한 행동을 취할 수 있음 --> 메모리 용량을 아낄 수 있음 + 정보은닉


composite 패턴
- 객체들의 관계를 트리 구조로 구성하여 부분-전체 계층을 표현하는 패턴
   단일 객체 + 복합 객체 모두 동일하게 다루도록 하는 패턴 


adapter
- 기존 클래스를 재사용할 수있도록 중간에서 맞춰주는 역할의 인터페이스 생성 패턴
- 1. 상속을 이용하는 클래스 패턴 = 클래스
  2. 위임을 이용하는 인스턴스 패턴 형태
- 타 클래스의 인터페이스를 기존 인터페이스에 덧 씌움




# --------------행위 패턴-----------------

command
- 요구사항을 객체로 캡슐화
- 주어진 여러 기능을 실행할 수 있는 재사용성이 높은 클래스를 설계하는 패턴
- 스택, 큐

memento
- 클래스 설계 관점에서 객체의 정보를 저장할 필요가 있을 때 적용하는 패턴
- 객체 이전 상태로 복구 가능 Undo 기능을 개발할 때 사용

observer
- 변화 시 객체의 의존하는 다른 객체들에게 통보해주는 패턴을 구현한 것
- 일대다 의존 개발
- List 사용


strategy
- 알고리즘을 각각 하나의 클래스로 캡슐화 한 다음, 필요 시 서로 교환하여 사용
- 행위 객체를 클래스로 캡슐화해서 동적으로 변환하고 직접 변경하지 않고, 전략만 변경
- 객제지향의 꽃


templateMethod
- 전체 구조는 바꾸지 않고 작업을 처리해야할 부분만 서브 클래스로 캡슐화하여 수행하는 패턴
- 상위 클래스에 추상 메서드를 만들고 하위 클래스의 처리해할 메서드를 만들어 유지보수에 용이하게함
- 히어로 클래스면 무조건




## 디자인 패턴 요약


🚩 생성
1) Builder : 생산 단계를 캡슐화 하여 구축 공정을 동일하게 이용하도록 하는 패턴
2) Prototype : 복사하여 새 개체를 생성할 수 있도록 하는 패턴
3) Factory Method : 객체를 생성하기 위한 인터페이스를 정의하여 어떤 클래스가 인스턴스화 될 것인지는 서브 클래스가 결정하도록 하는 패턴
4) Abstract Method : 생성군들을 하나의 모아놓고 팩토리 중에서 선택하게 하는 패턴
5) Singleton : 유일한 하나의 인스턴스를 보장하도록 하는 패턴

🚩 구조
1) Bridge : 추상과 구현을 분리하여 결합도를 낮춘 패턴
2) Decorator : 소스를 변경하지 않고 기능을 확장하도록 하는 패턴
3) Facade : 하나의 인터페이스를 통해 느슨한 결합을 제공하는 패턴
4) Flyweight : 대량의 작은 객체들을 공유하는 패턴
5) Proxy : 대리인이 대신 그 일을 처리하는 패턴
6) Composite : 개별 객체와 복합 객체를 클라이언트에서 동일하게 사용하도록 하는 패턴
7) Adapter : 인터페이스로 인해 함께 사용하지 못하는 클래스를 함께 사용하도록 하는 패턴

🚩 행위
1) Interpreter : 언어 규칙 클래스를 이용하는 패턴
2) Template Method : 알고리즘 골격의 구조를 정의한 패턴
3) Chain of Responsibility : 객체들끼리 연결 고리를 만들어 내부적으로 전달하는 패턴
4) Command : 요청 자체를 캡슐화하여 파라미터로 넘기는 패턴
5) Iterator : 내부 표현은 보여주지 않고 순회하는 패턴
6) Mediator : 객체 간 상호작용을 캡슐화한 패턴
7) Memento : 상태 값을 미리 저장해 두었다가 복구하는 패턴
8) Observer : 상태가 변할 때 의존자들에게 알리고, 자동 업데이트하는 패턴
9) State : 객체 내부 상태에 따라서 행위를 변경하는 패턴
10) Strategy : 다양한 알고리즘 캡슐화하여 알고리즘 대체가 가능하도록 한 패턴
11) Visitor : 오퍼레이션을 별도의 클래스에 새롭게 정의한 패턴







