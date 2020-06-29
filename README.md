# 왜 자바에는 없는거야? 아니! 코틀린이나 C#이나 C++, PHP(버전마다 달랐던 듯)에는 있는데?

아참! javascript도 없지.    

뭐가 없냐면 바로 엘비스 헤어라는 연산자이다.    

코틀린을 예로 들면 바로 ?: 이렇게 생겨 먹은 녀석을 볼 수 있게 된다.    

그럼 저게 뭔데 왜 엘비스 오퍼레이터라고 하는 거지?    

![실행이미지](https://i.stack.imgur.com/hQlrps.png)

이렇게 보면 엘비스 머리 모양이지?    


예전에 C#에서 아마 이게 버전마다 다른걸로 알고 있는데 ?:이런 요상한 것을 보고 한참을 찾다가 알게 된 것이다.

그럼 저게 뭐냐?

코드로 보자.


```

public void testMethod(String a, String b) {

  String a = (a == null) ? "변수없당" : a;
  String b = (b == null) ? "변수없넹" : b;
  .
  .
  .

}


```

이런 코드 많이 짜봤을 것이다. 물론 util같은 것으로 구현해놔도 되긴 한다.

자바스크립트도 마찬가지인데 그럼 코틀린에서는 어떻게 하는지 궁금할 것이다.

```
fun testMethod(a: String?, b: String?) { 
  val test1 = a ?: "변수없당" 
  val test2 = b ?: "변수없넹" 
}

```

엄청 간결하다. ~~롤에서 말하는 나는 뒤가 없는 챔프~~

이외에도 ?. <- 요런것도 제공한다. 
Null sfae Operator라고 하는데 코드를 엄청 간결하게 만들 수 있다.

예들 들면 자바에서

```
String a = null;

a = a.toUpperCase();

```

이러면 바로 '널 보내고 있지'

그래서 널 보내지 않으려면 어떻게 해야겠어?

```
String a = null;
if(a != null) {
  a = a.toUpperCase();
} else {
  a = null;
}

```

무려 5줄을 소비하게 되는거지

그래서 코틀린은요?

```
fun toUpper(a: String?): String = a?.toUpperCase() ?: null;

```

하.. 간결하넹...

자바도 저런거 있었으면 좋겠다.
