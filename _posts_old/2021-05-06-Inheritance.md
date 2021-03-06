---
layout: post
title: "상속(Inheritance) - 1"
---

## 1. 상속?

* 의미: 물려준다라는 개념을 그대로 사용된다.
* 프로그래밍에서의 상속은? 서브 클래스가 슈퍼 클래스의 변수, 메소드 등을 물려받아서 사용하는 것을 의미.

## 2. 왜 사용하는가?

* 코드가 간결화
* 유지보수 용이
* 재사용성이 향상

## 3. 상속의 단점

* 서브 클래스는 슈퍼 클래스에 의존성이 높다.
* 슈퍼 클래스가 수정되었을 시 서브 클래스의 코드도 수정되어야 할 경우가 있다.

## 4. JAVA에서의 상속 

* Java에서 상속의 키워드는 extends
  - 클래스는 클래스를 상속받고, 인터페이스는 인터페이스를 상속받을 수 있다.
  - 하나의 서브 클래스는 하나의 슈퍼 클래스만 상속 받을 수 있다. (다중상속 불가)
  - 인터페이스는 다른 여러개의 인터페이스를 상속 받을 수 있다. (인터페이스의 다중상속 가능)

  ```
    class Human {}

    class Student extends Human {}
  ```

  ```
    interface ITest1 {}
    interface ITest2 {}

    interface ITest3 extends ITest1, ITest2 {}
  ```

* 상속에서의 접근제어자 차이점

  | |default|private|protected|public|
  |---|---|---|---|---|
  |같은 패키지내의 다른 클래스|O|X|O|O|
  |다른 패키지내의 다른 클래스|X|X|X|O|
  |같은 패키지내의 서브 클래스|O|X|O|O|
  |다른 패키지내의 서브 클래스|X|X|O|O|

* this, super
  - this: 현재 호출되는 객체를 참조.
  - super: 현재 호출되는 객체의 슈퍼클래스를 참조.

* 오버라이딩: 슈퍼클래스에 존재하는 메소드를 서브클래스에서 재정의하는 것을 의미.
  - 슈퍼 클래스에서 정의되어있는 동작을 무시하고 새롭게 정의내린 동작을 하도록 재정의하는 것.
  - 오버라이딩은 상속관계에서만 사용 가능.
  - 서브클래스에서 재정의되는 메소드는 슈퍼클래스의 메소드와 동일한 이름, 동일한 인자 타입 및 개수, 동일한 리턴타입 이여야한다.
  - 오버라이딩 되었으나 슈퍼 클래스의 메소드를 접근하고 싶으면 super 로 슈퍼 클래스를 접근하여 메소드 호출.

* 오버로딩: 같은 클래스 내 혹은 슈퍼 클래스에 존재하는 메소드의 동일한 이름으로 중복하여 작성하는 것을 의미.
  - 같은 이름의 메소드를 다양한 형태로 정의하여 편리하게 사용을 위한 목적.
  - 메소드의 인자 타입이 다르거나, 인자의 개수가 달라야한다.

[참조] [생활코딩 - JAVA 상속 강의 1편](https://youtu.be/tsgJEm-pq2E)