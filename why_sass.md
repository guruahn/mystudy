#Why Sass? 왜 Sass인가?

원문 : [http://alistapart.com/article/why-sass](http://alistapart.com/article/why-sass)

by [DAN CEDERHOLM](http://alistapart.com/author/dancederholm)

이를테면 나는 좀 머뭇거리는 Sass 신자였습니다. 나는 하드코딩으로 스타일시트를 작성했습니다. 도움이 필요 없었고 내 워크플로우에 복잡한 무언가가 침입하는 것을 원치 않았습니다. 

어쨋든 진실은 Sass가(또는 다른 CSS 전처리기) 우리의 워크플로우에 쉽게 추가하여 사용할 수 있는 매우 강력한 동맹이 될 수 있다는 것입니다. 나의 경우에는 좀 돌아돌아서 여기까지 왔지만 그래도 좋습니다.

이것이 내가 이 작은 책([Sass For Web Designers](http://www.abookapart.com/products/sass-for-web-designers))을 쓰게 된 이유입니다.  지난 십년 간 CSS를 작성해오면서 만들어진 익숙한 나의 프로세스를 Sass로 더 편하게 만들 수 있었던 방법에 대해 공유하려고 합니다. 처음에는 한 번 해보려고 하는 시도를 막았던 Sass에 대해 많은 오해들이 있었습니다. 나는 내가 쓰고 관리하던 스타일 시트를 완전히 다른 방식으로 바꿔야 한다고 생각하고 두려워했습니다. CSS는 매우 깨지기 쉬운 예민한 것이기 때문에 자신의 창조물에 대해 보호받을만한 무언가를 가진 저자가 그렇게 생각하는 것은 이해할만한 일입니다. 동감이 되시나요? 음흠.

그래서 나는 Sass가 여러분의 프로세스와 작업흐름에 방해가  되지 않고 여러분의 삶을 더 쉽게 만드는지 보여주려고 합니다. 나는 Sass의 여러 측면, 어떻게 설치하고 어떻게 사용하고 어떻게 우리의 프로젝트에서 나를 도와주는지에 대해 데모를 보여줄 것입니다. 뿐만 아니라 운이 좋다면 나는 여러분이  Sass의 신자가 되게 할 수도 있습니다.

The Sass elevator pitch

말하자면 당신의 스타일시트를 바꿔야한다고 했을 때 그 값을 여러번 찾기 바꾸기를 해왔나요? CSS에서 아래와 같은 방식을 기대하기는 힘듭니다.

	$brand-color: #fc3;
	a{
		color : $brand-color;
	}
	nav {
		background-color: $brand-colr;
	}

무엇이 여러분을 하나의 값 변경으로 전체 값을 변경할 수 있게 만들까요? Sass로 그것을 할 수 있습니다.

또는 스타일시트 전역의 다양한 위치에서 반복적으로 사용하는 스타일 블록은 어떨까요?

	p {
		margin-bottom: 20px; font-size: 14px; line-height: 1.5;
	}
	footer {
		margin-bottom: 20px;
		font-size: 14px;
		line-height: 1.5;
	}

재사용 가능한 블록안에 공유 규칙을 넣으면 환상적이지 않을까요? 다시말하면, 단 한번의 정의로 그것이 필요한 모듯 곳에 넣을 수 있는 것입니다.

	@mixin default-type {
		margin-bottom: 20px;
		font-size: 14px;
		line-height: 1.5;
	}
	p {
		@include default-type;
	}
	footer {
		@include default-type;
	}

역시 Sass에서 가능합니다! 그리고 이 두 극단적으로 단순한 예제는 어떻게 Sass가 스타일시트 제작을 더 빠르고 쉽고 유연하게 만들 수 있는 방법을 힐끗 보여줄 뿐입니다.

CSS is hard

현실 직시하기: CSS를 배우는 것은 쉽지 않습니다. 각 요소가 무엇을 하고, 어떻게 종속이 이루어 지는지, 브라우저가 어떤 선택자를 지원하는지 이해하는 것은 쉽지 않습니다. 
