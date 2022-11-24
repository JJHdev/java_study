### 1. final과 static 차이
static 
1. 클래스에 있다. (객체 구현없이 사용가능)
2. 재정의가 가능하다.

final
1. 객체가 있어야 사용가능
2. 재정의 불가능

### 2. 인터페이스
 [public class 구현클래스명 implements 인터페이스명s{}]
2-1 인터페이스에서 선언된 필드는 모두다 public static final로 자동적으로 컴파일 된다.
- 상수명은 대문자로 통일.

2-2 추상메소드 선언
- public abstract를 생략하더라도 자동적으로 컴파일시 붙는다.

2-3. 디폴트메소드
2-4. 스텍틱메소드

 > 다형성은 부모타입의 참조변수안에 자식의 여러 객체가 들어갈수있습니다.
   상위클래스명 참조변수 = new 하위클래스명();


### 3. 컬렉션프레임워크
package cho15_Collection;


//java.lang패키지를 제외한 그 외 패키지는 import해야한다
//Object클래스, wrapper클래스,...
import java.util.ArrayList;
import java.util.Date;
//import 패키지명.Date;
/*collection Framework(컬렉션프레임워크)
-3가지 인터페이스
-List:순서유지,중복허용 예)대기자list
-Set:순서x,중복허용x
-Map:key와 value가 한 pair
	 key는 중복허용x
	 value는 중복허용
*/
public class A_ArrayList01 {

	public static void main(String[] args) {
		/*java.util.ArrayList   list =
				new java.util.ArrayList();*/
		ArrayList list = new ArrayList();
		System.out.println(list);
		System.out.println(list.toString());
		
		//size():리스트안에 저장된 요소(item)의 개수를 리턴
		//참고> .length:배열(array)에 저장된 요소(item)의 개수를 리턴
		//Returns the number of elements in this list.
		int size = list.size();
		System.out.println("list.size()="+size);//0
		
		//.add() : value추가
		//List에는 다양한 타입의 value을 추가할 수 있구나
		//비교> 배열(array)에는 동일한 타입의 value을 추가
		list.add("홍길동");
		list.add(new String("서울시 강남구"));
		list.add("hid");
		list.add("h123");
		list.add(20); //int ->Integer
		list.add(182.9); //double ->Double
		list.add('남');//char->Character
		list.add(true);//boolean->Boolean
		list.add( new Date() );//현재 날짜와 시간 객체생성
		System.out.println("list.size()="+list.size());//9
		
		//특정위치에 있는 요소(item, element)를 가져오기
		//get(인덱스)
		Object data = list.get(0);
		System.out.println(data);//홍길동
		//String으로 down casting. 강제형변환.
		//(강제형변환)변수
		//여기에서는 String으로 강제형변환하여
		//String클래스의 length()메서드를 호출하였다
		//Object에는 length()메서가 없기때문.
		String strData=(String)data;
		System.out.println("글자길이="+strData.length());//글자길이
		/*
		 * Animal = new Animal(); 
		 * Animal a= new Cat(); a.sound(); 
		 * Animal a= new Dog(); a.sound(); 
		 * Animal a= new Bird(); ((Bird)a).fly();
		 */
		
		Object data1=list.get(1);
		System.out.println(data1);//서울시 강남구
		System.out.println("글자길이="+((String)data1).length());//7
			
		Object data8=list.get(8);
		System.out.println(data8);//Mon Nov 14 16:37:14 KST 2022
		
		//인덱스4,5,6,7에 담긴 value는
		//Object타입의 변수data4에 저장 후 출력
		// instanceof 클래스명 : 특정클래스의 객체이면 true리턴
		Object data4=null;
		String type="";
		for(int i=4;i<8;i++) {
			data4=list.get(i);
			if(data4 instanceof Integer) {			
				type="정수:";//20
			}else if(data4 instanceof Double) {			
				type="실수:";//182.9
			}else if(data4 instanceof Character) {			
				type="Character:";//남
			}else if(data4 instanceof Boolean) {			
				type="Boolean:";//true
			}
			System.out.println(type+data4);
		}
		//integer는 integer.parselnt(String nm) 을 많이쓴다.
	}
}
