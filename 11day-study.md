1. instance 와 static, 접근제한자에 대한 개념
    - instance는 객체를 생성한다.
    - private는 다른 클래스에서 사용할수 없지만, 매개변수가 있는 생성자를 이용하여 쓸수가 있다.
    - private로 되어있는 필드를 생성자로 초기화 하면 메소드로 확인할수있다. (get사용)
  → 리턴유형 get필드명(){
     return 필드명;
     }
     
  	String name = mem2.getName(); 
	System.out.println(name);
    
    void set필드명(타입 필드명){
     this.필드명=필드명;}
     
2. 접근제한자.
    - public (클래스,맴버) 모두다 가능.
    - private (맴버) 자신의 클래스만
    - default (클래스,맴버) 동일 패키지
    - protected (맴버) -동일패키지 이거나, 다른패키지면서 상속관계시(객체 생성으로는 안된다.)
  
3. 상속필드.
     - 부모클래스로부터 상속받은 필드가 있다.
