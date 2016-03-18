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

h1과 p의 margin-bottom값이 왜 다르게 계산된 것일까? 이런 현상은 *1em이 현재의 font-size를 의미*하기 때문이다. h1의 font-size는 2em으로 세팅되어있다. 때문에 다른 프로퍼티는 1em을 h1의 font-size인 32px로 계산한다. 따라서 h1의 margin-bottom값은 32px과 동일한 값을 가진다.

