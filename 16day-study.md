1. 컬렉션프레임워크
2. ArraysList
3. 제너릭
4. 박싱 언박싱.
5. LinkedList
6. System클래스
7. set
8. String
9. Map

## 1. 컬렉션프레임워크.
 . List : 순서가 있으며, 중복이 가능하다.    (대기자 명단)
 . Set  : 순서없으며, 중복이 불가능하다.     (집합관계)
 . Map  : key와 value 가 한 pair로 있다.  
 
 ```
	public static void main (String[] args) {
		
		//ArrayList는 List인터페이스의 구현클래스 중의 하나
		//클래스명 참조변수 = new 클래스명();
		//ArratList 객체생성.
		ArrayList list = new ArrayList();
		
		//value 추가  .add(object)
		list.add("피카츄");
		list.add("이슬이");
		list.add("웅이");
		list.add(new String("한지우"));
		
		//저장된 value개수 : size() 
		System.out.println(list.size());
		
		//1번value 꺼내기 Object리턴하는  .get(index)
		System.out.println(list.get(0));
		Object obj = list.get(1);
		String strObj=((String)obj);  //String으로 강제형변환
		int len = strObj.length();   // String으로 변환된 value의 글자길이.
		System.out.println(strObj+"글자길이="+len);
		
		//2번.
		String strObj2=(String)list.get(3);
		System.out.println(list.get(3)+"글자길이="+strObj2.length());
		
		//3번
		System.out.println(list.get(2)+"글자길이="+((String)(list.get(2))).length());
		
```

import = ctrl+shift+o

## 2. 제너릭
 2-1. 제너릭 타입이란?
 타입을 파리미터로 가지는 클래스와 인터페이스 선언 시 클래스 또는 인터페이스 이름 뒤에 <>부호를 붙임 <>사이에는 타입 파라미터 위치
 
 2-2. 타입 파라미터
 일반적으로 대문자 알파벳 한 문자로 표현 개발코드에서는 타입 파라미터 자리에 구체적인 타입을 지정해야.
 
 ## 3. Set
 - ```
package cho15_Collection;

import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;


// ★★★★★ 컬렉션프레임워크의 3가지 인터페이스 종류 & 종류별 특징.
//List : 중복가능, 순서대로 (대기자명단)
//Set  : 중복x , 순서x (집합)
//Map  : 값과 키가 한쌍으로 있음.

public class HashSet01 {

	public static void main(String[] args) {
		
		//HashSet객체생성
		//클래스타입 참조변수 = new 클래스명();
		//HashSet<String> set1 = new HashSet();
		//인터페이스명 참조변수 = new 구현클래스명();
		Set set = new HashSet();
		
		//value 추가
		set.add("홍길동");
		set.add(new String("장길산"));
		set.add("산기슭");
		set.add("슭곰발");
		set.add("h123");
		set.add(20); 
		set.add(182.9); 
		set.add('남');
		
		//value 개수
		System.out.println(set.size());
		
		//value 꺼내기 (while 문 활용)
		Iterator iter = set.iterator();
		while(iter.hasNext()) { //다음 요소가 있다면 true
			Object obj = iter.next();
				System.out.println(obj);
		}
		
		//삭제
			if(set.remove("홍길동")) {
				System.out.println("삭제완료");
			}else
			System.out.println("삭제안됨");
		
		//확인
			if(set.contains("홍길동")) {
				System.out.println("있음");
			}else
				System.out.println("없음");
			
		// 완전삭제 (저장된 모든 객체 삭제) : void clear()
			set.clear();
			System.out.println(set.size());
			
		//컬렉션이 비어있는지 조사 : isEmpty()
			if(set.isEmpty()) {
				System.out.println("컬렉션 없음");
			}else {
				System.out.println("컬렉션 있음");
			}
	}

```
4. map
package cho15_Collection;

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Set;

public class HashMap01 {

	public static void main(String[] args) {

		/*
		List : 중복가능, 순서대로 (대기자명단) (ArrayList, Vector, LinkedList)
		Set  : 중복x , 순서x (집합)		  (HashSet, TreeSet)
		Map  : 값과 키가 한쌍으로 있음.		  (HashMap, HashTable,TreeMap,Properties)
		구현클래스 : 인터페이스에있는 추상메소드및 멤버를 재정의한 클래스
		*/
		
		//HashMap()호출하여 map 생성
		// 인터페이스명 참조변수 = new 구현클래스();
		// 인터페이스명 참조변수 = new HashMap();
		//HashMap map1 = new HashMap();
		Map <String, Integer> map = new HashMap<String, Integer>();
		//Key, value추가 : put(Object key, Object value)
		// Object타입 key가 들어갈수 있지만 편의상 String, Integer사용
		
		//객체저장
		map.put("김", 12);
		map.put("이", 22);
		map.put("박", 32);
		map.put("김", 42);
		
		//value 꺼내기(key를 이용하여)
		//key를 알 경우
		
		int i1 = map.get("이");
		//Integer타입을 int타입의 변수에 저장 > UnBoxing
		
		System.out.println(map.size());
		System.out.println(map.get("김"));
		System.out.println();
		
		//key를 모를경우 모든 key를 꺼내서 사용 > while(몇번을 실행해야할지 몰라서)
		//꺼낸 key 하나하나에 대하여 각각의 key에 대한 value를 꺼내기
		//객체찾기
		Set<String> ks = map.keySet();
		Iterator<String> ki = ks.iterator();
	}
}
