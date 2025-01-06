## 내용정리

### 책임

객체가 협력에 참여하기 위해 수행하는 로직은 책임이라고 한다.

객체들이 협력 안에서 수행하는 책임들이 모여 객체가 수행하는 역할을 구성한다.

자율적인 객체란 자신의 상태를 외부로 노출 시키지 않고 직접 다루며, 외부에 노출 시키는 것은 협력 메세지 처리 여부이다.

### 협력 컨텍스트

설계는 협력의 컨텍스트를 반영한다.

Movie객체는 이름만 보았을 때는 재생, 일시정지와 같은 기능이 연상되지만, 중요한 것은 해당 객체가 현재 어떤 협력에 참여하고 있는가에 따라서 책임을 부여해야한다는 것이다. ‘영화 예매하기’라는 컨텍스트에서 Movie라는 객체가 갖게될 책임이 결정된다.

협력은 책임으로 세분화 되고 책임은 특정 객체의 행동을 결정한다. 객체의 행동은 객체 내부적으로 가져야할 상태를 결정한다.

### 역할과 협력

특정 객체가 협력안에서 수행하는 책임의 집합을 역할이라고 부른다.

협력을 모델링 할 때, 특정 작업을 처리할 객체를 생각하기보다. 어떤 역할에게 해당 책임을 할당해야하는지 판단해야한다.

1. 해당 책임을 수행할 적절한 역할은 무엇인가?
2. 역할을 수행할 수 있는 객체에게 책임을 할당한다.

객체가 아닌 역할에 초점을 맞춰야 하는 이유는 해당 방법이 설계에 유연함을 주기 때문이다.

역할은 추상적인 개념으로 다양한 객체들로 구체화될 수 있다. 하지만 객체는 역할보다 정적인 개념이다.

뿐만아니라, 역할을 통한 설계는 객체의 세부사항을 가려 캡슐화를 강제할 수 있다.

### 객체가 역할보다 우선되는 경우

특정 역할을 수행하기 위한 객체가 오직 하나뿐인 경우 역할과 객체가 동일시 될 수 있다.

하지만 이것을 판단하기는 힘든 것 역시 사실이다, 설계의 초반에는 그럴것이 추후에 변경될 수 있기 때문이다.

책에서는 설계초반의 불완정성은 없을 수 없다고 한다. 따라서 설계초반에 가장 중요하게 주목해야할 점은 책임을 세분화하는 것이다. 객체와 역할을 구분짓는 것은 뒷전이다.

반복적으로 책임과 협력을 정제해가며 **필요한 순간에 객체로부터 역할을 분리해내는 것이 현명**하다.

<aside>

정확한 결정을 내리기 어려운 상황이라면 구체적인 객체로 시작해라!

</aside>

## 느낀점(개선할점)

### 책임의 세분화

큰 책임을 작은 책임으로 세분화함으로써 협력 공동체를 형성한다. 특정 책임을 수행할 객체를 선택할 때, 책에서는 정보전문가 즉, 해당 책임을 수행하기에 필요한 정보를 가지고 있을 것 같은 객체에게 책임을 할당하는 것이다.

<aside>

영화를 예매하라는 책임은 “상영시간” 과 “비용”이라는 정보를 필요로한다, 해당 정보를 가질 것 같은 객체는 Screening(상영)객체이다.

</aside>

해당 객체는 사람의 직관에 초점을 둔 객체이다. 

궁금한 점은 상영과 같은 객체가 미리정의되어 있지 않은 상황에서는 어떻게 객체를 떠올려야할까이다.

ChatGPT질문 결과, 요구사항 즉 가장 큰 책임으로부터 어떤 객체들이 필요한지 모델링을 먼저한다. 즉, 도메인 모델링의 일부이다.

어떤 객체가 있고 어떤 데이터를 가질 것이라고 설계가 된 시점에 정보전문가 패턴을 적용해 특정 객체에게 적절한 책임을 할당하는 것이다.

책의 예시의 경우 영화를 예매하려면 ‘상영’이 있어야 하고 ‘영화’도 있어야 한다로 시작할 수 있다.

맞고 틀리다의 문제가 아닌, 다양한 설계가 나올 수 있고 여러 시도를 통해 효과적인 설계를 찾는 것이 중요한 것 같다.