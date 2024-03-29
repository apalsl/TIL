# 객체지향의 사실과 오해


## 협력하는 객체들의 공동체

### 객체지향의 목표
> 객체지향의 목표는 고객과 사용자를 만족시킬 수 있는 신세계를 창조하는 것.
```
객체지향 프로그래밍이란 현실 속에 존재하는 사물을 최대한 유사하게 모방해 소프트웨어 내부로 옮겨오는 작업이다.  
그 결과인 객체지향 소프트웨어는 실세계의 투영이며, 현실세계에 존재하는 사물에 대한 추상화이다.
```

### 객체지향을 실세계를 모방해 객체지향으로
> 협력하는 사람들 - 커피 공화국의 아침 (실세계)
```
1. 샐러리맨 출근을 하고 카페에 가서 커피를 주문한다. 
2. 캐시어는 주문을 받고 영수증과 진동벨을 전달하고 주문내역을 바리스타에게 알린다. 
3. 바리스타는 캐시어에게 주문내역을 받고 음료를 제조, 전달한다.
4. 캐시어는 음료를 받고 진동벨을 울려 샐러리맨에게 음료를 제공한다.
```


위 커피 공화국의 아침을 객체지향의 세계로 생각해보면 객체지향의 특징을 쉽게 알 수 있다.


> 역할, 책임, 협력 관계로 살펴보는 커피 공화국의 아침

사람의 역할을 **객체**로, 요청과 응답을 **메시지**로, 처리하는 방법을 **메서드**로 바꿔보자

```
1. 샐러리맨은 주문을 해야 할 책임이 있는 객체이며, 캐시어에게 커피를 요청한다.
2. 캐시어는 샐러리맨의 요청을 받고, 바리스타에게 커피를 요청할 책임이 있는 객체이다.
3. 바리스타는 캐시어의 요청을 받고, 커피를 제조 및 캐시어에게 응답해줄 책임이 있다.
4. 캐시어는 바리스타로부터 응답을 받고, 샐러리맨에게 커피를 응답해준다.
```

> 커피 공화국의 아침에서 알 수 있는 객체지향의 특징
+ 여러 객체가 동일한 역할을 수행할 수 있다.
    - 샐러리맨의 입장에서는 꼭 특별한 캐시어가 주문받지 않아도 문제되지 않는다.
    - 캐시어 입장에서는 특별한 바리스타가 필요하지 않다. 커피를 제조할 수 있는 객체면 된다.
+ 역할은 대체 가능성을 의미한다.
    - 샐러리맨의 입장에서는 어떠한 캐시어가 주문을 받아도 상관이 없다.
    - 중요한 점은 주문을 받고 커피를 제공해주는 것일뿐, 캐시어가 둘이여도 문제되지 않는다.
+ 책임을 수행하는 방법은 자율적으로 선택할 수 있다.
    - 바리스타는 커피만 제조하면 된다. 자신만의 레시피가 있어도 커피를 제공하면 문제되지 않는다.
+ 하나의 객체가 동시에 여러 역할을 수행할 수 있다.
    - 만약 캐시어의 능력이 뛰어나다면 바리스타를 고용하지 않고 캐시어가 커피를 제조할 수 있다.


위 글에서 실세계를 객체지향의 세계로 전환하여 객체지향의 특징을 알게 되었다. \
그렇다면 객체가 갖춰야 할 특징은 무엇인가?


#### 객체지향에서의 객체가 갖춰야 할 덕목
> 객체는 충분히 '협력적' 이어야 한다.
```
객체는 요청에 응답해야 한다.
```
> 객체는 충분히 '자율적' 이어야 한다.
```
캐시어는 손님이 주문을 요청해야 시작하지만, 손님을 대하는 태도, 주문 내역을 전달하는 방법은
스스로 판단하고 결정하고 행동하는 자율적인 존재다.
```
> 상태와 행동을 함께 갖춰야 한다.
```
커피를 제조하는 바리스타가 제조 방법을 모른다는 것은 말이 안된다.
행동을 하기 위해 필요한 상태를 알아야 한다. 상태를 기반으로 스스로 행동해야 한다.
다른 객체가 무엇을 수행하는지 상태인지 알 수 있지만 어떻게 행동하는지 알 수 없다.
```


### 객체지향의 본질
> 위의 내용을 종합한 객체 지향의 개념을 간략하게 정리한다면

- 객체지향이란 시스템을 상호작용하는 **자율적인 객체**들의 공동체로 바라보고 객체를 이용해 시스템을 분할하는 방법이다. 
- 자율적인 객체란 **상태**의 **행위**를 함께 지니며 스스로 자기 자신을 책임지는 객체를 의마한다. 
- 객체는 시스템의 행위를 구현하기 위해 다른 객체와 **협력**한다. 
- 각 객체는 협력 내에서 정해진 역할을 수행하며 **역할**은 관련된 **책임**의 집합이다.
- 객체는 다른 객체와 협력하기 위해 **메시지**를 전송하고, **메시지**를 수신한 객체는 메시지를 처리하는 데 적합한 **메서드**를 자율적으로 선택한다

```
객체지향의 핵심은 클래스가 아니다. 핵심은 적절한 책임을 수행하는 역할 간의 유연하고
견고한 협력 관계를 구축하는 것이다. 클래스는 객체를 만드는데 필요한 구현 메커니즘일 뿐이다.
```



## 이상한 나라의 객체

### 앨리스 객체
> 앨리스 객체로 객체를 상태, 행동, 식별자를 지닌 실체로 보자.
```
앨리스는 시계를 들고있는 토끼를 따라 뛰다 천장이 낮은 긴 통로 위로 떨어진다.
앨리스는 주변을 살피다 40cm정도의 작은 문을 발견하고 문 뒤에 아름다운 정원을 발견한다.
앨리스는 몸을 커지게 하는 케이크를 찾아먹고 몸을 작아지게 하는 부채를 찾아 부채질을 한다.
앨리스의 몸은 커지고 작아지기를 반복하고 마침내 작은문을 통과해 아름다운 정원으로 이동한다.
```

> 앞의 이야기에서 앨리스가 작은 문을 통과하기 위해 겪은 변화에 초점을 맞춰보자.
```
앨리스는 문을 통과하기에 적당한 상태로 자신의 키를 계속해서 변화 시켰다.
키가 크면 부채질을 하여 키를 줄였다. 
```
















