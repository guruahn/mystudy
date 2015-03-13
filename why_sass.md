#Why Sass? 왜 Sass인가?

원문 : [http://alistapart.com/article/why-sass](http://alistapart.com/article/why-sass)

by [DAN CEDERHOLM](http://alistapart.com/author/dancederholm)

이를테면 나는 좀 머뭇거리는 Sass 신자였습니다. 나는 하드코딩으로 스타일시트를 작성했습니다. 도움이 필요 없었고 내 워크플로우에 복잡한 무언가가 침입하는 것을 원치 않았습니다. 

어쨋든 진실은 Sass가(또는 다른 CSS 전처리기) 우리의 워크플로우에 쉽게 추가하여 사용할 수 있는 매우 강력한 동맹이 될 수 있다는 것입니다. 나의 경우에는 좀 돌아돌아서 여기까지 왔지만 그래도 좋습니다.

이것이 내가 이 작은 책([Sass For Web Designers](http://www.abookapart.com/products/sass-for-web-designers))을 쓰게 된 이유입니다.  지난 십년 간 CSS를 작성해오면서 만들어진 익숙한 나의 프로세스를 Sass로 더 편하게 만들 수 있었던 방법에 대해 공유하려고 합니다. 처음에는 한 번 해보려고 하는 시도를 막았던 Sass에 대해 많은 오해들이 있었습니다. 나는 내가 쓰고 관리하던 스타일 시트를 완전히 다른 방식으로 바꿔야 한다고 생각하고 두려워했습니다. CSS는 매우 깨지기 쉬운 예민한 것이기 때문에 자신의 창조물에 대해 보호받을만한 무언가를 가진 저자가 그렇게 생각하는 것은 이해할만한 일입니다. 동감이 되시나요? 음흠.

그래서 나는 Sass가 여러분의 프로세스와 작업흐름에 방해가  되지 않고 여러분의 삶을 더 쉽게 만드는지 보여주려고 합니다. 나는 Sass의 여러 측면, 어떻게 설치하고 어떻게 사용하고 어떻게 우리의 프로젝트에서 나를 도와주는지에 대해 데모를 보여줄 것입니다. 뿐만 아니라 운이 좋다면 나는 여러분이  Sass의 신자가 되게 할 수도 있습니다.

#The Sass elevator pitch

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

#CSS is hard

Let’s face it: learning CSS isn’t easy. Understanding what each property does, how the cascade works, which browser supports what, the selectors, the quirks, and so forth. It’s not easy. Add on top of that the complexity of the interfaces we’re building these days, and the maintenance that goes along with that and—wait, why are we doing this again? It’s a puzzle, and some of us enjoy the eventual completion.

현실 직시하기: CSS를 배우는 것은 쉽지 않습니다. 각 요소가 무엇을 하고, 어떻게 종속이 이루어 지는지, 브라우저가 어떤 선택자를 지원하는지 이해하는 것은 쉽지 않습니다. 우리가 구축하고 있는 인터페이스 위에 복잡성을 추가해야하는 것 뿐 아니라 이것들이 함께 유지되어야 합니다. 그리고..잠깐, 왜 우리가 이것을 반복해야 할까요? 그것은 퍼즐입니다. 우리중 누군가는 그것의 궁극적 완성을 즐길겁니다.

Part of the problem is that CSS wasn’t originally designed to do the things we do with it today. Sure, progress is moving along at a nice clip thanks to rapid browser innovation and implementation of CSS3 and beyond. But we still need to rely on techniques that are, for all intents and purposes, hacks. The float property, for example, was designed to simply align an image within a block of text. That’s it. Yet we’ve had to bend that property to lay out entire interfaces.

CSS의 또 다른 문제는 원래 CSS가 이것들을 함께 할 수 있도록 설계된 것이 아니라는 것입니다. 물론 브라우저의 혁신과 CSS3의 구현덕분에 발전이 빠르게 이루어지고 있습니다. 그러나 여전이 우리는 사실상의 hacks 기술에 의존하고 있습니다. 예를 들어 float 속성은 단순히 텍스트 블록내의 이미지 정렬을 위해 설계되어있습니다. 좋습니다. 그러나 우리는 전체 인터페이스 설계를 위해서는 그 속성을 왜곡시켜야 합니다.

Our stylesheets are also immensely repetitive. Colors, fonts, oft-used groupings of properties, etc. The typical CSS file is an extremely linear document—the kind of thing that makes an object-oriented programmer want to tear their hair out. (I’m not an object-oriented programmer, but I have very little hair left. Read into that as you may).

또한 우리의 스타일시트는 매우 반복적입니다. 색상, 폰트, 자주 사용되는 속성 그룹들, 등등. 일반적인 CSS 파일은 극단적으로 선형적인 문서입니다—이것은 객체 지향 프로그래머가 머리를 쥐어 뜯게 만드는 것입니다. (나는 객체 지향 프로그래머는 아니지만 머리가 조금밖에 남아있지 않습니다. 머리얘기는 너무 진지하게 받아들이지 마시길.) 
As interfaces and web applications become more robust and complex, we’re bending the original design of CSS to do things it never dreamed of doing. We’re crafty like that. Fortunately, browser makers adopt new CSS features far more rapidly these days, with more efficient and powerful properties and selectors that solve the problems today’s web poses. Features like new layout options in CSS3, border-radius, box-shadow, advanced selectors, transitions, transforms, animation, and so on. It’s an exciting time. And yet, there’s still a lot missing from CSS itself. There are holes to be plugged, and the life of a stylesheet author should be a lot easier.

인터페이스와 웹 어플리케이션들이 점점 견고해지고 복잡해짐으로서 우리는 원래 CSS가 할 수 없었던 일들을 구현하기위해 본래의 CSS 디자인을 왜곡시키고 있습니다. 운이 좋게도 브라우저 업체들은 오늘날 웹상에서의 새로운 문제들을 해결하기위한 효과적이고 강력한 속성과 선택자들과 함께 새로운 CSS 기능들을 더 빠르게 채택하고 있습니다. 그 새로운 기능들은 CSS3의 새로운 옵션들, border-radious, box-shadow, advanced selectors, transitions, transforms, animation 등등이 있습니다. 매우 흥분되는 일입니다. 그리고 아직 여전히 CSS 자체에서 누락된 것들이 많습니다. 

##THE DRY PRINCIPLE 
##DRY 원리

If we peer into the world of software engineering (and I much prefer to peer than hang out and get comfortable there), we can quickly see how organization, variables, constants, partials, etc., are an ingrained, crucial way of working for folks building complex systems.

만약 우리가 소프트웨어 엔지니어링의 세계를 통해 본다면 우리는 복잡한 시스템을 세우는 사람들의 작업에 어떻게 구조, 변수, 상수, 등이 베어있는지를 쉽게 알 수 있을 것입니다.

You may have heard of the “don’t repeat yourself” (DRY) principle. Coined and defined by Andy Hunt and Dave Thomas in their book, The Pragmatic Programmer (http://bkaprt.com/sass/1/), DRY declares:

여러분은 “don’t repeat yourself”(DRY) 원리를 들어본적이 있을지도 모르겠습니다. Dry 선언은 Andy Hunt와 Dave Thomas가 그들의 책 The Pragmatic Programmer([http://bkaprt.com/sass/1/](http://bkaprt.com/sass/1/))에서 새롭게 정의한 것입니다:

	Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.