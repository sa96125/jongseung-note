# 클래스

자바 프로그램의 기본 단위로 <mark style="color:blue;">객체(사물)를 정의하는 설계도</mark>입니다. 클래스는 객체의 상태(state)와 행위(behavior)를 정의하며, 이를 이용하여 객체를 생성할 수 있습니다. 즉, 실행할 코드를 작성합니다. 코드 작성자가 원하는 개념을 정리 및 구현하는 곳이라 말할 수 있습니다. 최소 하나 이상으로 구성될 수 있습니다.





_<mark style="background-color:yellow;">클래스는 객체를 생성하는 블루프린트, 설계도라고 알고 있는데,</mark>_\
_<mark style="background-color:yellow;">항상 객체 지향이라는 수식어가 붙어서 조금 어려워요. 객체 지향 언어가 도대체 뭘까요?</mark>_

_**"실제 세계는 사물로 이루어져 있으며, 발생하는 모든 사건들은 사물간의 상호작용이다"**_

오래전, 과학자들은 모의 실험을 위해 실제 세계와 유사한 가상 세계를 컴퓨터 속에 구현하려 노력했습니다. 이러한 노력으로 객체지향이론을 탄생시켰고, 가상세계를 구현하여 모의실험을 함으로서 많은 시간과 비용을 절약할 수 있었습니다. 객체 지향언어는 어떠한 프로그래밍언어와 다른 전혀 새로운 것이 아니라, 프로그래밍 언어에 몇 가지 새로운 규칙을 추가한 보다 발전된 형태를 말합니다. 즉, 현실 세계의 객체를 모델링하여 프로그래밍하는 방법입니다

{% code overflow="wrap" %}
```
🔍 객체 지향 언어의 주요 특징으로는 캡슐화(Encapsulation), 상속성(Inheritance), 다형성(Polymorphism)이 있습니다. 캡슐화는 객체의 상태를 객체 내부에 숨기고, 외부에서 직접 접근할 수 없도록 보호하는 것을 말합니다. 상속성은 부모 클래스에서 자식 클래스로 속성과 기능을 상속하는 것을 말합니다. 다형성은 같은 이름의 메소드가 서로 다른 동작을 수행할 수 있도록 하는 것을 말합니다.

🔍 객체 지향 언어의 대표적인 예시로는 Java, C++, Python 등이 있으며, 현재 대부분의 프로그래밍 언어에서 객체 지향 프로그래밍의 개념과 원리를 적극적으로 적용하고 있습니다. 객체 지향 프로그래밍은 코드의 재사용성, 유지보수성, 확장성 등의 이점을 제공하므로 현대적인 소프트웨어 개발에 필수적인 기술이라 할 수 있습니다.
```
{% endcode %}







_<mark style="background-color:yellow;">어떻게 이론을 코드로 정의하고 사용하는 걸까요?</mark>_\
_<mark style="background-color:yellow;">실제 자동차를 클래스로 정의하는 예시코드를 만들어 보겠습니다.</mark>_

앞서 살펴보았듯이, 객체지향이론의 관점에서는 클래스는 객체를 생성하기 위한 템플릿(틀) 역할을 합니다. 클래스는 멤버 변수와 메소드로 구성되며, 객체 생성 시 생성자를 통해 멤버 변수에 값을 할당하고, 메소드를 호출하여 해당 객체의 행동을 결정합니다.

프로그래밍적인 관점에서는 데이터 처리를 위한 데이터 저장형태의 발전형태로 생각할 수 있습니다. 그동안 데이터와 함수가 서로 관계가 없는 것처럼 데이터는 데이터끼리, 함수는 함수끼리 따로 다루어져 왔지만, 자바와 같은 객체지향언어에서는 변수와 함수를 하나의 클래스에 정의하여 서로 관계가 깊은 변수와 함수들을 함께 다룰 수 있게 되었습니다.

1. 변수 : 하나의 데이터를 저장할 수 있는 공간
2. 배열 : 같은 종류의 여러 데이터를 하나의 집합으로 저장할 수 있는 공간
3. 구조체 : 서로 관련된 여러 데이터를 종류에 관계없이 하나의 집합으로 저장
4. 클래스 : 데이터와 함수의 결합(구조체 + 함수)



아래는 실제 자동차를 클래스로 정의한다음 인스턴스를 생성하는 예시 코드입니다.&#x20;

{% code lineNumbers="true" %}
```java
public class Car {
  // 멤버 변수
  String brand; // 브랜드
  String model; // 모델
  int year; // 연도

  // 생성자
  public Car(String brand, String model, int year) {
    this.brand = brand;
    this.model = model;
    this.year = year;
  }

  // 메소드 멤버 변수와 연관된 로직
  public void start() {
    System.out.println("Engine started");
  }

  public void stop() {
    System.out.println("Engine stopped");
  }
}

Car myCar = new Car("BMW", "320i", 2022);
```
{% endcode %}



특이한 점은 멤버 변수 brand의 경우, 자료형 타입 String으로 문자열을 다루고 있습니다. 문자열을 단순히 문자의 배열로 정의한 이유는 문자열과 문자열을 다루는데 필요한 함수들을 함께 묶기 위해서합니다. 이렇게 함으로서 변수와 함수가 서로 유기적으로 연결되어 작업이 간단하고 명료해집니다 :)

{% code overflow="wrap" %}
```
🔍 인스턴스를 생성할 때, 단계별 과정을 살펴보자면,
1. 먼저, Car 클래스타입의 참조변수 myCar을 선언하면, 메모리에 참조변수를 위한 공간이 마련됩니다. 
2. new 연산자에 의해 Car클래스의 인스턴스가 메모리의 빈 공간에 생성됩니다. 만약 생성자가 없다면 인스턴스의 속성은 디폴트 값으로 채워지는데, String은 참조형이므로 null, boolean은 false, int는 0으로 초기화됩니다.
3. 대입연산자(=)에 의해 인스턴스의 주소값이 참조변수 myCar에 저장됩니다. 이후, 참조변수를 통해 car 인스턴스에 접근할 수 있습니다. 인스턴스를 다루기 위해서는 참조변수가 반드시 필요하다는 것을 알 수 있어요.
```
{% endcode %}







_<mark style="background-color:yellow;">프로그래밍을 하다가 참조변수를 실수로 변경해버릴 수 있을 것 같은데,</mark>_\
_<mark style="background-color:yellow;">참조변수에 수정이 일어나게 되면 어떤일이 발생할까요?</mark>_

인스턴스의 참조 변수가 없는 상황에서 해당 인스턴스는 메모리 상에서 더 이상 참조되지 않는 상태가 됩니다. 이러한 인스턴스는 더 이상 접근할 수 없으며, 이를 "쓰레기 객체(Garbage Object)" 라고 합니다.



프로그램의 성능을 최적화하기 위해서는 쓰레기 객체가 생성되는 것을 최소화하는 것이 좋습니다. 이를 위해서는 인스턴스를 생성할 때, 해당 인스턴스의 참조 변수를 적절히 관리해야 합니다. 예를 들어, 인스턴스를 생성한 후, 해당 인스턴스를 사용하는 코드 블록이 종료될 때, 인스턴스의 참조 변수를 null로 초기화하여 더 이상 참조되지 않도록 하는 것이 좋습니다. 이를 통해 쓰레기 객체의 생성을 최소화하고, 프로그램의 성능을 최적화할 수 있습니다.

{% code overflow="wrap" %}
```java
public class Example {
    public void doSomething() {
        // 인스턴스 생성
        MyClass myObject = new MyClass();
        
        // myObject를 사용하여 여러 작업을 수행
        //...
        
        // 사용한 후에는 참조 변수를 null로 초기화하여 가비지 컬렉터에 의해 자동으로 메모리에서 해제
        myObject = null;
    }
}

```
{% endcode %}

{% code overflow="wrap" %}
```
🔍 Java에서는 가비지 컬렉터(Garbage Collector)를 통해 메모리 관리를 수행합니다. 가비지 컬렉터는 더 이상 참조되지 않는 객체를 검사하고, 해당 객체의 메모리를 해제하여 프로그램의 메모리 사용량을 최적화합니다. 따라서, 인스턴스의 참조 변수가 없어져도 메모리 누수(Memory Leak)가 발생하지는 않습니다.
```
{% endcode %}







_<mark style="background-color:yellow;">어떤 예제에 클래스를 보면 변수앞에 생소한 키워드(static/private)가 붙어있는 경우가 있더라구요.</mark>_\
_<mark style="background-color:yellow;">이게 정확히 뭘 의미하는 걸까요?</mark>_

클래스 내부에 static 키워드가 결합된 변수는 클래스의 모든 인스턴스에서 공유되는 변수입니다. 즉, 클래스 변수는 클래스 자체에 속하며, 클래스의 모든 인스턴스가 클래스 변수를 공유합니다. 클래스 변수는 클래스 내에서 정의되며, 클래스 변수에 접근하기 위해서는 클래스 이름을 통해 접근할 수 있습니다. 즉, 인스턴스를 생성하지 않아도 데이터, 메서드에 접근할 수 있게 됩니다.



그외에 변수는 클래스의 인스턴스마다 독립적으로 유지되는 변수입니다. 즉, 인스턴스 변수는 객체의 속성을 나타내며, 인스턴스가 생성되었을 때, 생성되며 수명과 함께 유지됩니다. 인스턴스 변수는 인스턴스 메서드에서 사용되며, self를 통해 접근할 수 있습니다. 따라서, 클래스 변수는 클래스 레벨에서 정의되고 모든 인스턴스가 공유하는 반면, 인스턴스 변수는 인스턴스 레벨에서 정의되고 각각의 인스턴스가 각자의 값을 가집니다.



인스턴스 변수 앞에는 private 키워드 즉, 제어자를 사용할 수 있습니다. 사실 데이터에는 실제 사물을 모델링을 전제로 하기때문에 제약조건이 붙을 수 밖에 없습니다. 예를들어, 시간은 시, 분, 초는 모두 0보다 크거나 같아야한다는 점, 시의 범위는 0\~23, 분과 초의 범위는 0\~59인 조건을 변수에 반영해줘야 하는 것이죠. 객체 지향언어에서는 제어자와 메서드를 이용하여 이러한 조건들을 코드에 쉽게 반영할 수 있습니다.

```java
public class Time {
  private int hour;
  private int minute;
  private int second;

  public Time(int hour, int minute, int second) {
    if (!isValidTime(hour, minute, second)) {
      throw new IllegalArgumentException("유효하지 않은 시간입니다.");
    }
    this.hour = hour;
    this.minute = minute;
    this.second = second;
  }

  public int getHour() {
    return hour;
  }

  public void setHour(int hour) {
    if (!isValidTime(hour, this.minute, this.second)) {
      throw new IllegalArgumentException("유효하지 않은 시간입니다.");
    }
    this.hour = hour;
  }

  public int getMinute() {
    return minute;
  }

  public void setMinute(int minute) {
    if (!isValidTime(this.hour, minute, this.second)) {
      throw new IllegalArgumentException("유효하지 않은 시간입니다.");
    }
    this.minute = minute;
  }

  public int getSecond() {
    return second;
  }

  public void setSecond(int second) {
    if (!isValidTime(this.hour, this.minute, second)) {
      throw new IllegalArgumentException("유효하지 않은 시간입니다.");
    }
    this.second = second;
  }

  private boolean isValidTime(int hour, int minute, int second) {
    if (hour < 0 || hour > 23) {
      return false;
    }
    if (minute < 0 || minute > 59) {
      return false;
    }
    if (second < 0 || second > 59) {
      return false;
    }
    return true;
  }

  // 시간 추가 메서드 생략
  // toString() 메서드 생략
}

Time time = new Time(13, 45, 30); // 유효한 시간
time.setHour(25); // 유효하지 않은 시간
```







_<mark style="background-color:yellow;">자바에서 프로그램을 구현하기 위해서는 클래스가 필수적인거 같네요.</mark>_\
_<mark style="background-color:yellow;">그런데, 그냥 함수하나 만들어서 실행하면 될 것을,</mark>_ \
_<mark style="background-color:yellow;">어떤 로직을 실행할때마다 클래스를 거쳐야하면 오히려 번거러운거 아닌가요?</mark>_

지금까지는 main메서드 안에 모든 문장을 넣는 식으로 프로그램을 작성해왔습니다. 길어야 100줄 정도 밖에 안되는 작은 프로그램을 작성할 때는 이렇게 해도 별 문제가 없지만, 몇 천줄, 몇 만줄이 넘는 프로그램도 이런식으로 작성할 수는 없습니다. 큰 규모의 프로그램에서는 문장들을 작업단위로 나눠서 여러 개의 메서드에 담아 프로그램의 구조를 단순화시키는 것이 필수적입니다. 이렇게 <mark style="color:blue;">프로그램의 전체 흐름에 한눈에 들어올 수 있게 구조화</mark>해놓으면 추후에 문제가 발생하더라도 해당 부분을 쉽게 찾아서 해결할 수 있습니다.



클래스, 메서드를 통해서 얻는 이점은 여러 가지가 있습니다. 당장 다음에 나열하는 장점들이 잘 와 닿지 않을 수도 있지만, 이 장점들을 염두에 두고 있으면 객체 지향에 대해 더 깊게 이해하는데 도움이 될 것입니다.

1. 코드의 재사용성\
   클래스를 작성하면 해당 클래스를 여러 곳에서 사용할 수 있습니다. 이는 코드의 재사용성을 높이는데 도움이 됩니다. 예를 들어, 자주 사용하는 수학 함수들을 모아놓은 Math 클래스는 프로그래머들이 이를 자유롭게 사용할 수 있도록 해줍니다.
2. 코드의 가독성\
   클래스를 사용하면 코드의 가독성을 높일 수 있습니다. 클래스 내부에 필드와 메서드가 모여 있기 때문에, 관련된 기능들이 한데 묶여 있어 코드의 구조를 이해하기 쉽습니다. 또한, 클래스 이름을 통해 해당 클래스가 어떤 역할을 하는지 파악할 수 있습니다.
3. 유지보수 용이성\
   클래스를 사용하면 코드를 수정하거나 추가하는 작업이 용이해집니다. 클래스를 작성하면 해당 클래스의 메서드를 수정하거나 추가함으로써, 해당 클래스를 사용하는 모든 곳에서 수정된 내용이 반영됩니다. 이는 코드의 유지보수를 용이하게 해줍니다.
4. 객체지향 프로그래밍 지원\
   자바는 객체지향 프로그래밍을 지원합니다. 클래스를 작성하면 객체를 생성할 수 있습니다. 객체는 클래스의 인스턴스이며, 객체를 사용하여 프로그래밍을 할 수 있습니다. 객체지향 프로그래밍은 코드의 재사용성, 유지보수 용이성 등을 향상시켜줍니다.
5. 캡슐화\
   클래스를 작성함으로써 캡슐화를 구현할 수 있습니다. 캡슐화는 데이터와 메서드를 하나로 묶는 것을 의미합니다. 이는 데이터를 보호하고, 오류 발생 시 코드 수정이 용이하게 만들어줍니다. 클래스 내부의 필드와 메서드를 캡슐화하여, 해당 클래스를 사용하는 다른 클래스에서는 필드에 직접 접근할 수 없도록 하고, 메서드를 통해 필드에 접근할 수 있도록 해줍니다.







_<mark style="background-color:yellow;">클래스명이랑 동일한 생성자라고 하는 메서드가 가끔 정의되어 있던데,</mark>_\
_<mark style="background-color:yellow;">생성자가 하는 역할은 무엇이고 언제 실행되는 건가요?</mark>_

인스턴스가 생성될 때 호출되는 초기화 메서드입니다. 생성자는 단순히 인스턴스 변수를 초기화하는 조금 특별한 메서드일 뿐이고 몇 가지 특징을 제외하면 일반 메서드와 다르지 않습니다.



생성자를 다룰때 참고해야할 사항은 다음과 같습니다.

1. 생성자의 이름은 클래스의 이름과 같아야 한다.
2. 생성자는 리턴 값이 없기에 생략 할 수 있다.
3. 오버로딩 가능하여 여러개의 생성자가 존재할 수 있다.
4. 생성자가 인스턴스를 생성하는 것은 아니다.(new 연산자가 인스턴스를 생성)&#x20;
5. 생성자에서오버로딩된 다른 생성자를 호출할때는 첫줄에  this()를 사용한다.



오버로딩 생성자가 있을 때, 가끔 중복된 코드가 있을 수 있습니다. 공통으로 수행해야하는 로직이 있다면,  각 생성자마다 코드를 작성하기 보다는 공통적으로 한번만 작성하는 것이 코드를 보다 간결하게 만들 수 있겠지요. 이를 처리하는 곳을 초기화 블럭이라고 말합니다.

```java
class InitBlock {
    static int cv = 1;
           int iv = 1;

    static {
        // 클래스 초기화 블럭  
        cv = 2;
    }

    {
        // 인스턴스 초기화 블럭
        iv = 2;
    }
    
    InitBlock() {
        // 인스턴스 초기화
        iv = 3;   
    }
}
```



위의 코드에서 멤버변수의 초기화 시기와 순서는 다음과 같습니다.

1. cv가 메모리(method area)에 생성되고, cv에는 int형의 기본값인 0이 저장
2. 명시적 초기화에 의해 cv에 1이 저장
3. 클래스초기화 블럭이 수행되어 cv에 2가 저장
4. 인스턴스가 생성되면, iv가 메모리(heap)에 생성, 역시 기본값인 1이 iv에 저장
5. 명시적 초기화에 의해 iv에 1이 저장
6. 인스턴스  초기화 블럭이 수행되어  iv에 2가 저장
7. 마지막으로 생성자가 수행되어 iv에 3이 저장

<pre data-overflow="wrap"><code><strong>🔍 생성자를 정의하지않아도 컴파일러가 자동으로 기본 생성자를 제공하기 때문에 인스턴스를 생성하는데 전혀 문제가 없습니다.
</strong><strong>
</strong><strong>🔍 코드의 중복을 제거하는 것은 코드의 신뢰성을 높여 주고, 오류의 발생가능성을 줄여 준다는 장점이 있습니다. 즉, 재사용성을 높이고 중복을 제거하는 것, 이것이 바로 객체지향프로그래밍이 추구하는 궁극적인 목표라 할 수 있습니다.
</strong></code></pre>







_<mark style="background-color:yellow;">클래스를 정의가 완벽하지 않는 경우에는 어떻게 설계를 해야할까요?</mark>_

그동안 클래스를 설계도라고 표현했었는데, 추상클래스는 <mark style="color:blue;">미완성 설계도로 하나 이상의 추상 메서드를 포함하고 있는 클래스</mark>입니다. 실제 동작을 수행하는 코드는 하위 클래스에서 구현해야 합니다. 추상 클래스는 하위 클래스에서 공통된 속성과 메서드를 상속받아 재사용성을 높일 수 있는 장점이 있습니다.

* 추상클래스(미완성 설계도)로는 인스턴스를 생성할 수 없다.
* 미완성 메서드가 존재한다. 고로 하위 클래스에서 메서드를 완성해야 한다.
* 주석을 통해 어떤 기능을 수행할 목적으로 작성하였는지 설명한다.



추상 클래스는 `abstract` 키워드를 사용하여 정의합니다.

```java
public abstract class AbstractClass {
    // 추상 메서드 선언
    public abstract void abstractMethod();

    // 일반 메서드 정의
    public void concreteMethod() {
        System.out.println("This is a concrete method.");
    }
}
```



추상 메서드는 메서드 이름 앞에 `abstract` 키워드를 붙여 선언합니다. 추상 클래스는 인스턴스를 생성할 수 없으므로, 하위 클래스에서 상속받아 구현해야 합니다.







_<mark style="background-color:yellow;">근데 내용이 없는 메서드의 선언이 굳이 의미가 있는 건가요?</mark>_

실제 메서드를 작성할 때 실제 작업 내용인 구현부보다 더 중요한 부분이 선언부입니다. 메서드의 이름과 메서드의 작업에 필요한 매개변수, 그리고 어떤 타입의 값을 반환할 것인가를 결정하는 것은 쉽지 않은 일입니다. 오히려, 실제 구현부에서는 선언부의 내용만 알고 있으면 내부로직을 작성하는 일은 쉽습니다. 선언부만 작성해도 메서드의 절반 이상이 완성된 것이라 해도 과언이 아닙니다.







_<mark style="background-color:yellow;">자식클래스에서 오버라이딩해서 함수를 재정의해서 구현하는거나,</mark>_\
_<mark style="background-color:yellow;">추상클래스를 정의해서 사용하는거나 기능적으로는 똑같지 않나요?</mark>_

굳이 추상클래스로 작성하는 이유는 <mark style="color:blue;">'반드시' 구현</mark>하도록 강요하기 위해서 입니다. 만일 추상 클래스로 정의 되어 있지 않고 빈 몸통만 가지도록 정의되어 있다면, 상속받는 자식 클래스에서는 이 메서드들이 온전히 구현된 것으로 인식하고 오버라이딩을 통해 자신의 클래스에 맞도록 구현하지 않을 수도 있습니다.&#x20;







_<mark style="background-color:yellow;">내부클래스?</mark>_

내부 클래스는 다른 클래스 내부에 선언되는 클래스입니다. 내부 클래스는 외부 클래스의 멤버 변수 및 메서드에 쉽게 접근할 수 있으며, 외부 클래스의 보안성을 높일 수 있습니다. 내부 클래스는 다음과 같이 선언됩니다.

```java
public class OuterClass {
    private int x = 10;

    // Inner Class
    public class InnerClass {
        public void printX() {
            System.out.println(x);
        }
    }
}
```







_<mark style="background-color:yellow;">익명클래스?</mark>_

익명 클래스는 이름이 없는 클래스로, 클래스를 선언과 동시에 객체를 생성할 때 사용됩니다. 주로 인터페이스나 추상 클래스를 구현하는 경우에 사용됩니다. 익명 클래스는 다음과 같이 선언됩니다.

```java
public class OuterClass {
    public void printMessage() {
        System.out.println("Hello World!");
    }
}

public class Main {
    public static void main(String[] args) {
        // Anonymous Class
        OuterClass anonymousClass = new OuterClass() {
            public void printMessage() {
                System.out.println("Hi there!");
            }
        };

        anonymousClass.printMessage();
    }
}
```



위 코드에서 `OuterClass`는 일반적인 클래스이며, `Main` 클래스에서 `anonymousClass`라는 이름의 익명 클래스를 선언하여 객체를 생성하였습니다. 익명 클래스에서는 `OuterClass`의 `printMessage()` 메서드를 오버라이딩하여, "Hi there!"을 출력하도록 변경하였습니다.



내부 클래스와 익명 클래스는 모두 클래스를 중첩해서 사용하는 것으로 코드의 모듈화를 증가시키고, 유지보수성을 높이는 효과가 있습니다. 하지만, 내부 클래스는 외부 클래스와의 결합도가 높아지고, 코드가 길어지는 단점이 있습니다. 반면에 익명 클래스는 간단하게 클래스를 구현할 수 있지만, 클래스의 정의와 생성을 한 번에 수행하기 때문에 재사용성이 떨어지는 단점이 있습니다.
