#REM vs EM

원문 : [REM vs EM – The Great Debate](http://zellwk.com/blog/rem-vs-em/)

##EM

EM은 타이포그래피의 단위로서 `font-size`와 동일하다. 선택자의 font-size가 20px이라면 1em은 20px이다.

그럼 아래와 같은 경우 h1의 font-size는 얼마일까?

	html { font-size: 100% }  /* This means 16px by default*/
	h1 { font-size: 2em } /* 16px * 2 = 32px */

h1의 font-size를 알기위해서는 상위 요소의 font-size를 알아야 한다. 위 예시에서는 상위 요소인 html의 font-size가 16px로 설정되어있으므로 h1은 16px을 상속받으며, 2em에 의해 32px로 계산된다.

em은 font-size외에 다른 프로퍼티들을 위한 값으로 사용할 수도 있다. margin과 padding이 보통 em단위로 사이징하는 대표적인 프로퍼티들이다.

사람들은 이것 때문에 em값에 대한 혼란을 격곤 한다. 아래 코드를 살펴보자. 

	h1 {
	  font-size: 2em; /* 1em = 16px */
	  margin-bottom: 1em; /* 1em = 32px */
	}

	p {
	  font-size: 1em; /* 1em = 16px */
	  margin-bottom: 1em; /* 1em = 16px */
	}

h1과 p의 margin-bottom값이 왜 다르게 계산된 것일까? 이런 현상은 **1em이 현재의 font-size를 의미**하기 때문이다. h1의 font-size는 2em으로 세팅되어있다. 때문에 다른 프로퍼티는 1em을 h1의 font-size인 32px로 계산한다. 따라서 h1의 margin-bottom값은 32px과 동일한 값을 가진다.

REM은 무엇인가?

rem은 루트의 em을 의미한다. 즉 1rem은 <html>의 font-size와 항상 동일하다.
	
	h1 {
	  font-size: 2rem;
	  margin-bottom: 1rem; /* 1rem = 16px */
	}

	p {
	  font-size: 1rem;
	  margin-bottom: 1rem; /* 1rem = 16px */
	}

만약 html의 font-size를 변경하지 않았다면 위와 같이 1rem은 항상 16px일 것이다.

REM이냐 EM이냐?

어떤 개발자들은 rem이 모듈화를 어렵게 만들기 때문에 완전히 피한다. 또 다른 이들은 rem이 단순하기 때문에 항상 rem만을 사용한다.

사실 rem과 rm은 서로 장단점을 가지고 있으며 상황에 따라 다르게 사용되어야 한다.

나는 두 가지 규칙을 가지고 있다.

1. font-size에 따라 확장성을 가지는 요소는 em을 사용한다.
2. 그외의 크기는 rem을 사용한다.

[view demo](https://jsfiddle.net/guruahn/zdytd52L/4/)

rem으로만 사용한 헤더 스타일을 보자.

	.header {
	  font-size: 1rem;
	  padding: 0.5rem 0.75rem;
	  background: #7F7CFF;
	}

아직까지는 문제가 없다. 하지만 이 헤더의 큰사이즈 버전을 추가해보자.

	.header {
	  font-size: 1rem;
	  padding: 0.5rem 0.75rem;
	  background: #7F7CFF;
	}

	.header--large {
	  font-size: 2rem;
	}


이 경우 헤더의 padding은 그대로 이고 font-size만 두 배로 커졌다. 커진 font-size만큼 padding을 조정하려면 아래와 같이 수정해야할 것이다.

	.header {
	  font-size: 1rem;
	  padding: 0.5rem 0.75rem;
	  background: #7F7CFF;
	}

	.header--large {
	  font-size: 2rem;
	  padding: 1rem 1.5rem;
	}

[view demo](https://jsfiddle.net/guruahn/zdytd52L/3/)

우리는 또 다른 헤더를 확장할 때마다 padding값을 다시 조정해야할 것이다. padding은 font-size에 따라 확장되는 속성이기 때문에 아래와 같이 em을 사용하면 padding값을 재선언할 필요가 없어진다.

	.header {
	  font-size: 1rem;
	  padding: 0.5em 0.75em;
	  background: #7F7CFF;
	}

	.header--large {
	  font-size: 2rem;
	}

##오직 em만을 사용할 경우

아래와 같이 em만을 사용하여 헤더와 큰 헤더를 정의한다.

	.header {
	  font-size: 1em;
	  padding: 0.5em 0.75em;
	  background: #7F7CFF;
	}

	.header--large {
	  font-size: 2em;
	}

그런데 우리는 웹사이트에서 헤더요소 하나만 사용하는 경우는 거의 없을 것이다. 다른 요소들과의 상호작용도 고려해야할 것이다. 다음과 같은 상황을 고려해보자.


	<div class="header header--large">A Header Element</div>
	<p>A paragraph of text</p>
	<p>A paragraph of text</p>
	<div class="header">A Header Element</div>
	<p>A paragraph of text</p>

단락의 좌우에도 헤더 좌우에 적용된 padding값과 동일한 margin을 적용해보면

	p {
	  margin-left: 0.75em;
	  margin-right: 0.75em;
	}

[view demo](https://jsfiddle.net/guruahn/kuoo2q5o/)

생각과는 다르게 보인다. 헤더의 왼쪽 padding과 단락의 왼쪽 margin은 똑같이 0.75em인데도 헤더의 여백이 훨씬 크다. em이 font-size에 기반하여 계산되기 때문이다. 이럴때 rem을 사용하여 헤더와 단락의 크기가 같은 루트의 사이즈에 기반하여 계산되도록 하면 동일한 값을 얻을 수 있다.

	.header {
	  padding: 0.5em 0.75rem;
	  font-size: 1em;
	  background: #7F7CFF;
	}

	.header--large {
	  font-size: 2em;
	}

[view demo](https://jsfiddle.net/guruahn/kuoo2q5o/1/)
