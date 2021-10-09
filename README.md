# TIL-WIL
### 절차지향,객체지향,관점지향은 ****[패러다임](https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%ED%8C%A8%EB%9F%AC%EB%8B%A4%EC%9E%84)****을 뜻하는 단어로써,

어떠한 견해나 관점을 용어로 만든 것 뿐이다.

절차지향 언어를 사용한다면, 말 그대로 **실행 순서, 즉 절차**가 더 중점이 되고,

객체지향 언어를 사용한다면, 필요한 **객체들의 종류와 속성** 등이 더 중점이 된다.

---

### **절차지향(Procedural Programming)이란**,

프로그램의 실행 절차에 중점을 둔 프로그래밍의 일종 입니다.

다른 프로그래밍 보다 프로그램이 순차적으로 동작하는 것에 큰 의미를 뒀습니다.

절차지향 언어는 대표적으로 C언어가있습니다.

> 장점
> 

1. 개인 프로젝트에 적합한 언어입니다.

2. 객체지향 프로그래밍과 비교하여 속도가 빠른편입니다.

(컴퓨터의 처리구조와 유사하기 때문)

> 단점
> 

1. 유지보수가 어렵습니다.

2. 코드의 순서가 바뀌면 의도한 대로 프로그램이 동작하지 않을 수 있습니다

3. 프로그램의 분석과 디버깅이 어렵습니다.

4. 위와 같은 단점들로 인해 대형 프로젝트에는 부적합합니다.

---

### **객체지향(Object Oriented Programming)이란,**

객체지향 프로그래밍에서는 **데이터와 절차를 하나의 덩어리로 묶어서 생각**하게 됩니다. 

이는 마치 컴퓨터 부품을 하나씩 사다가 컴퓨터를 조립하는 것과 같은 방법입니다.

객체지향 언어는 **어떤 모듈에 있는 하나의 기능만 필요하더라도 모듈 전체를 가져와야 하기 때문에 절차지향 프로그래밍보다 프로그램 사이즈가 더 커질 수도 있습니다.** 

또한 데이터에 대한 접근도 상대적으로 절차지향식보다 느려질 가능성이 많습니다. 

**메소드를 통해서만 접근이 가능하기 때문에 절차지향식처럼 특정 함수에 접근할 수 없고, 식으로만 접근이 가능해 속도적인 측면에서 불이익**이 있습니다.

---

**객체지향(Object Oriented Programming) 특성**

- **캡슐화(Encapsulation)****객체를 캡슐로 싸서 그 내부를 보호하고 볼 수 없게 하는 것으로 객체의 가장 본질적인 특징**입니다.
    
    > **JAVA로 예를 들면**, **클래스(Class)는 객체의 모양을 선언한 틀**이며,
    > 
    
    > **클래스 모양 그대로 생성된 실체(Instance)가 객체** 가 됩니다.
    > 
    
    > 자바는 **필드(Field)와 Method(Method)를 클래스 내에 모두 구현하고 캡슐화를 통해 객체 내 필드에 대한 외부로부터의 접근을 제한**합니다. (ex) public,private
    > 
    
     
    
- **상속(Inheritance)****상위 개체의 속성이 하위 개체에 물려져서, 하위 개체가 상위 개체의 속성을 모두 가지는 관계**입니다.
    
    > **JAVA로 예를 들면,** 자식 클래스가 부모 클래스의 속성을 물려받아 부모 클래스에 기능을 **확장(Extends)**하는 개념입니다.
    > 
    
    > 상속은  필드와 메소드를 물려받음으로써 **코드의 중복 작성을 방지**하고, **코드를 재사용**함으로써 코드 작성에 드는 시간과 비용을 줄입니다.
    > 
    
- **다형성(Polymorphism)****같은 이름의 메소드가 클래스 혹은 객체에 따라 다르게 구현**되는 것을 말합니다.
    
    > **JAVA로 예를 들면**, 슈퍼 클래스에 구현된 메소드를, 서브 클래스에서
    > 
    
    > 자신의 특징에 맞게 동일한 이름으로 다시 구현하는 이른바 **메소드 오버라이딩(Overriding)**으로 부르고,
    > 
    
    > 클래스 내에서 같은 이름의 메소드를 여러 개 만드는 **메소드 오버로딩(Overloading)**이 있습니다.
    > 
    
    ---
    

> 장점
> 
- **코드의 재활용성이 높습니다.**
- **코딩이 절차지향보다 간편**합니다.
- **디버깅이 쉽습니다.**

> 단점
> 
- **처리속도가 절차지향보다 느립니다.**
- **설계에 많은 시간 소요**가 들어갑니다.

---

**절차지향 프로그래밍(C)의  예시**

```c
//프로브와 일벌레의 몸체 역할을 하는 구조체
typedef struct 유닛 {
	char 유닛명[10];
	int 체력;
	int 공격력;
	void(*공격)(struct 유닛*, struct 유닛*); //공격 함수 포인터
	void(*사망)(struct 유닛*); //사망 함수 포인터
} 유닛;
```

```c
int main() {
	//구조체 생성
	유닛* 프로브 = malloc(sizeof(유닛));
	유닛* 일벌레 = malloc(sizeof(유닛));

	//구조체 초기화
	strcpy(프로브->유닛명, "프로브");
	strcpy(일벌레->유닛명, "일벌레");
	프로브->체력 = 40;
	일벌레->체력 = 30;
	프로브->공격력 = 5;
	일벌레->공격력 = 7;
	프로브->공격 = 공격; //함수 포인터도 초기화해야 한다.
	일벌레->공격 = 공격;
	프로브->사망 = 사망;
	일벌레->사망 = 사망;

	//일벌레 체력이 0일때까지 반복한다.
	while (1) {
		프로브->공격(프로브, 일벌레);

		//일벌레 체력이 0이라면, 사망플래그를 알린다.
		if (일벌레->체력 <= 0) {
			일벌레->사망(일벌레);
			break;
		}
	}
}
```

왜 이렇게 코드가 길어? 라고 생각한 사람도 있을 것이다.

코드를 길게 만든 주범은, 바로 구조체에 값들을 넣어주는 초기화 과정이다.

구조체는 멤버함수가 없어 생성자도 없기에,

**생성 시점과 별도로 멤버변수를 초기화**해주는 과정이 필요하다.

구조체 안에 있던 **함수포인터도,**

**만들어 둔 공격 함수와 사망 함수를 가리키게끔 초기화**해주어야 한다.

---

**객체지향 프로그래밍(C++)의 예시**

```cpp
class 유닛 {
private: //객체의 밖에서 접근할 수 없다.
	string 유닛명 = "이름없음";
	int 체력 = 0;
	int 공격력 = 0;

public: //객체의 밖에서도 접근할 수 있다.
    //멤버함수들. 함수의 선언만 해두었다.
	유닛(string 유닛명, int 체력, int 공격력); //생성자
	void 공격(유닛* 타겟);
	int getHP();
	~유닛(); //소멸자, 사망 함수를 대신한다.
};

//객체의 멤버변수를 초기화시켜주는 생성자 정의
유닛::유닛(string 유닛명, int 체력, int 공격력) {
	this->유닛명 = 유닛명;
	this->체력 = 체력;
	this->공격력 = 공격력;
}

//객체의 '체력'이라는 멤버변수를 가져오는 함수 정의
int 유닛::getHP() {
	return this->체력;
}
```

```cpp
int main() {
	//객체 생성
	유닛* 프로브 = new 유닛("프로브", 40, 5);
	유닛* 일벌레 = new 유닛("일벌레", 30, 7);

	//일벌레 체력이 0일때까지 반복한다.
	while (1) {
		프로브->공격(일벌레);

		//일벌레 체력이 0이라면, 사망플래그를 알린다.
		if (일벌레->getHP() <= 0) {
			delete 일벌레;
			break;
		}
	}
}
```

**생성과 동시에 객체의 멤버가 초기화**된다.

코드의 길이가 상당히 줄어들고, 깔끔해진 것을 볼 수 있다.

---

### 관점지향 프로그래밍- **AOP ( Aspect Oriented Programming )**

**어떤 로직을 기준으로 핵심적인 관점, 부가적인 관점으로 나누어보고 그 관점을 기준으로 각각 모듈화하겠다.**

> **모듈화 : 어떤 공통된 로직이나 기능을 하나의 단위로 묶는 것**
> 

> **핵심적인 관점 ( Core Concerns ) : 업무 로직을 포함하는 기능 ( 우리가 적용하고자 하는 핵심 비즈니스 로직 )**
> 

> **부가적인 관점 ( Cross-cutting Concerns ) : 핵심 기능을 도와주는 부가적인 기능 ( 핵심 로직을 실행하기 위해서 행해지는 데이터베이스 연결, 로깅, 파일 입출력 등**
> 

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/93c5d091-b81e-4580-a8fb-3e8a35728000/Untitled.png)

AOP에서 각 관점을 기준으로 로직을 모듈화 한다는 것은 

핵심기능과 부가기능의  **관점(Aspect), 관심이 다름**

**코드들을 부분적으로 나누어서 모듈화한다는 것**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8bcc722a-01d3-4063-975a-a583bb269249/Untitled.png)

**[ 간단한 소스 코드로 AOP 살펴보기 ]**

```java
classA {
	methoda() {
    	AAAA

        method a가 하는 일들

        BBBB
    }

    methodb() {
    	AAAA

        method b가 하는 일들

        BBBB
    }
}

classB {
	methodc() {
    	AAAA

        method c가 하는 일들

        BBBB
    }
}
```

**위와 같이 동일한 일을 하는 코드 AAAA, BBBB가 여기저기서 사용되고 흩어져있으면 코드 변경이 필요한 경우 하나씩 다 찾아서 바꿔야 한다.**

**AOP는 중복되는 코드를 떼어내서 분리하고 method a,b,c는 자신이 해야할 작업만 갖고 있자는 개념이다.**

- **여러군데서 사용되는 중복되는 코드 : AOP에서 말하는 aspect**
- **AOP는 부가기능을 애스펙트(Aspect)로 정의하여, 핵심기능에서 부가기능을 분리함으로써 핵심기능을 설계하고 구현할 때 객체지향적인 갈치를 지킬 수 있도록 도와줌**

---

### **3. AOP 특징**

- **프록시 패턴 기반**
    - **spring은 타겟(target) 객체에 대한 프록시를 만들어서 제공**
    - **타겟을 감싸는 프록시는 실행시간(runtime)에 생성**
    - **프록시는 어드바이스를 타켓 객체에 적용하면서 생성되는 객체**
    - **프록시 객체를 쓰는 이유는 접근 제어 및 부가기능을 추가하기 위함**
- **프록시가 호출을 가로챔(Intercept)**
    - **프록시는 타겟 객체에 대한 호출을 가로챈 다음 어드바이스의 부가기능 로직을 수행하고 난 후에 타겟의 핵심기능 로직을 호출함 ( 전처리 어드바이스 )**
    - **타겟의 핵심기능 로직 메서드를 호출한 후에 부가기능(어드바이스)을 수행하는 경우도 있다.(후처리 어드바이스)**
- **메서드 조인 포인트만 지원**
    - **Spring은 동적 프록시를 기반으로 AOP를 구현하므로 메서드 조인 포인트만 지원**
    - **핵심기능(타겟)의 메서드가 호출되는 런타임 시점에만 부가기능(어드바이스)을 적용할 수 있음**
- **반면에 AspectJ같은 고급 AOP 프레임워크를 사용하면 객체의 생성, 필드값의 조회와 조작, static 메서드 호출 및 초기화 등의 다양한 작업에 부가기능을 적용할 수 있음**

> * 프록시 패턴- 어떤 기능을 추가하려 할 때 기존 코드를 변경하지 않고 추가 가능- 어떤 클래스가 String AOP의 대상이라면 그 기존 클래스의 빈이 만들어질 때 Spring AOP가 프록시(기능이 추가된 클래스)를 자동으로 만들고 원본 클래스 대신 프록시 빈으로 등록- 그리고 원본 클래스가 사용되는 지점에서 프록시를 대신 사용
> 

> * 스프링 빈- Spring IoC 컨테이너가 관리하는 자바 객체를 빈(Bean)이라는 용어로 부름- 우리가 new 연산자로 어떤 객체를 생성했을 대 그 객체는 빈이 아니다.- ApplicationContext.getBean()으로 얻어질 수 있는 객체는 빈이다.- 즉 Spring에서의 빈은 ApplicationContext가 알고 있는 객체, 즉 ApplicationContext가 만들어서 그 안에 담고 있는 객체를 의미
> 

---

### **4. AOP 주요 키워드**

- **Target**
    - **핵심 기능을 담고 있는 모듈**
    - **어떤 관심사들과도 관계를 맺지 않음**
    - **Aspect를 적용하는 곳 ( 클래스, 메서드 )**
- **Aspect**
    - **흩어진 관심사를 모듈화한 것 ( 여러 핵심 기능에 적용될 관심사 모듈 )**
    - **구체적인 기능을 구현한 Advice와 Advice가 어디에서 적용될지를 결정하는 PointCut을 포함**
    - **AOP의 기본 모듈싱글톤 형태의 객체로 존재**
- **Advice**
    - **타겟에 제공할 부가기능을 담고 있는 모듈 ( 실질적인 부가기능을 담은 구현체 )**
    - **실질적으로 어떤 일을 해야할 지에 대한 것**
    - **Aspect가 무엇을 언제 적용할지를 정의**
- **PointCut**
    - **공통 기능이 적용될 대상 결정**
    - **어드바이스를 적용할 타겟의 메서드를 선별하는 정규표현식**
    - **JoinPont의 상세한 스펙을 정의한 것**
    - **execution으로 시작하고 메서드의 Signature를 비교하는 방법을 주로 이용**
- **JoinPont**
    - **Advice가 적용될 위치, 끼어들 수 있는 지점**
    - **타겟 객체가 구현한 인터페이스의 모든 메서드는 조인 포인트가 됨**
    - **메서드 진입 지점, 생성자 호출 시점, 필드에서 값을 꺼내올 때 등 다양한 시점에 적용 가능**
- **Advisor**
    - **Advice + Pointcut**
    - **Spring AOP에서만 사용되는 용어**
- **Weaving**
    - **포인트컷에 의해서 결정된 타겟의 조인 포인트에 부가기능(어드바이스)를 삽입하는 과정**
    - **AOP가 핵심기능(타겟)의 코드에 영향을 주지 않으면서 필요한 부가기능(어드바이스)를 추가할 수 있도록 해주는 핵심적인 처리과정**
    - **AOP가 핵심기능(타겟)의 코드에 영향을 주지 않으면서 필요한 부가기능(어드바이스)를 추가할 수 있도록 해주는 핵심적인 처리과정**
