### 1. getter, setter 다시 복습 
### 2. toString 에 대한이해
 public String toString() {
		return "[sno]="+sno+",[grade]="+grade+",[gender]="+gender+",[sname]="+sname+",[major]="+major;
	}
- sno는 int타입이지만 앞에 문자열을 넣음으로써 자동적으로 타입이 변환되어 사용된다.
- 여기서 toString은 최상위클래스인 object인 클래스로 부터 상속받은 메서드 이고, 오버라이딩(재정의) 한 것이다.

#### 3.메소드의 재정의 (@override)
 - 부모 클래스의 상속 메소드 수정해 자식 클래서에서 재정의 하는 것
 
 - 재정의 조건 : 부모 클래스의 메소드와 동일한 시그니처 가져야 함
 
 - 접근제한을 더 강하게 오버라이딩 불가
  > public을 defailt나 private로 수정불가
  > 반대로 default는 public로 수정 가능.
  > 새로운 예외 (Exceprion) thriws불가 (예외처리는 10장 참조)
  
#### 4. @Override 어노테이션
- 컴파일러에게 부모 클래스의 메소드 선언부와 동일한지 검사지시
- 정확한 메소드 재정의 위해 붙여주면 ok
- 효과 : 부모메소드는 숨겨지는 효과 발생
 >재정의된 자식클래스는 잘못 입력시. 컴파일러 표시됨.
 
### 5. 상속
 - 클래스에서는 부모클래스로 부터 상속받은 field와 method가 존재한다.
 - 부모 클래스의 private 접근 갖는 필드와 메소드 제외
 - 부모 클래스가 다른패키지에 있을경우 , default접근도 제외.
 - java는 단일 상속
 - 자식클래스 객체 호출시 부모클래스 객체 부터 생성된다.
 - super();란 부모생성자를 호출해주는 method이고, super.은 부모클래스를 참조하는 참조변수이다.
 - this()는 생성자내에서 첫줄에 작성해야한다.
 
 
### 6. Final
 - final field 수정불가 필드
 - final class 부모로 사용 불가한 클래스
 - final method 자식이 재정의 할 수 없는 메소드
 
 ### 7. 그렇다면 static은?
 - 객체가 없어도 실행가능
 - 블록 내부에 인스턴시 필드, 메소드 사용불가
 - 객체 자신의 참조인 this 사용 불가.
 
  ### 8. 타입변환
 - 상위클래스 참조변수 = new 하위클래스()
 - Animal animal = new Dog()
 - Animal animal = new cat()
  > 다형성
