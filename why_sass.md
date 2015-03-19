#Why Sass? 왜 Sass인가?

원문 : [http://alistapart.com/article/why-sass](http://alistapart.com/article/why-sass)

by [DAN CEDERHOLM](http://alistapart.com/author/dancederholm)

이를테면 나는 좀 머뭇거리는 Sass 신자였습니다. 나는 하드코딩으로 스타일시트를 작성했습니다. 도움이 필요 없었고 내 워크플로우에 복잡한 무언가가 침입하는 것을 원치 않았습니다. 

어쨋든 진실은 Sass가(또는 다른 CSS 전처리기) 우리의 워크플로우에 쉽게 추가하여 사용할 수 있는 매우 강력한 동맹이 될 수 있다는 것입니다. 나의 경우에는 좀 돌아돌아서 여기까지 왔지만 그래도 좋습니다.

이것이 내가 이 작은 책([Sass For Web Designers](http://www.abookapart.com/products/sass-for-web-designers))을 쓰게 된 이유입니다.  지난 십년 간 CSS를 작성해오면서 만들어진 익숙한 나의 프로세스를 Sass로 더 편하게 만들 수 있었던 방법에 대해 공유하려고 합니다. 처음에는 Sass에 대해 많은 오해들 때문에 Sass를 시작해보려는 시도가 좌절되었습니다. 그것을 사용하기 시작하면 제가 쓰고 관리하던 스타일 시트를 완전히 다른 방식으로 바꿔야 한다고 생각했기 때문에 두려웠습니다. CSS는 매우 깨지기 쉬운 예민한 것이기 때문에 자신의 창조물에 대해 보호받을만한 무언가를 가진 저자가 그렇게 생각하는 것은 이해할만한 일입니다. 동감이 되시나요? 음흠.

그래서 나는 Sass가 여러분의 프로세스와 작업흐름에 방해가 되지 않고 여러분의 삶을 더 쉽게 만드는지 보여주려고 합니다. 나는 Sass의 여러 측면, 어떻게 설치하고 어떻게 사용하고 어떻게 우리의 프로젝트에서 나를 도와주는지에 대해 데모를 보여줄 것입니다. 뿐만 아니라 운이 좋다면 나는 여러분이 Sass의 신자가 되게 할 수도 있습니다.

#The Sass elevator pitch

말하자면 당신의 스타일시트를 바꿔야한다고 했을 때 그 값을 여러번 찾기 바꾸기를 해왔겠죠? CSS에서는 아래와 같이 하나의 값 변경으로 전체 값을 변경할 수 없습니다.

	$brand-color: #fc3;
	a{
		color : $brand-color;
	}
	nav {
		background-color: $brand-colr;
	}

무엇이 하나의 값 변경으로 전체 값을 변경할 수 있게 만들까요? Sass로 그것을 할 수 있습니다.

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

만약 우리가 소프트웨어 엔지니어링의 세계를 통해 본다면 우리는 복잡한 시스템을 세우는 사람들의 작업에 어떻게 구조, 변수, 상수 등이 베어있는지를 쉽게 알 수 있을 것입니다.

You may have heard of the “don’t repeat yourself” (DRY) principle. Coined and defined by Andy Hunt and Dave Thomas in their book, The Pragmatic Programmer (http://bkaprt.com/sass/1/), DRY declares:

여러분은 “don’t repeat yourself”(DRY) 원리를 들어본적이 있을지도 모르겠습니다. Dry 선언은 Andy Hunt와 Dave Thomas가 그들의 책 The Pragmatic Programmer([http://bkaprt.com/sass/1/](http://bkaprt.com/sass/1/))에서 새롭게 정의한 것입니다:

	Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

	모든 지식의 조각은 시스템 내에서 단 하나의, 명확하고 권위있는 표현이어야 한다.

The idea is that duplicating code can cause failure and confusion for developers ([http://bkaprt.com/sass/2/](http://bkaprt.com/sass/2/)). It’s common sense as well: write commonly-repeated patterns once, and reuse those bits throughout the application. It’s more efficient and far easier to maintain code this way.

이 생각은 중복 코드가 개발자들에게 실패와 혼란을 야기할 수 있음을 말합니다([http://bkaprt.com/sass/2/](http://bkaprt.com/sass/2/)). 이것은 상식이기도 합니다: 반복되는 패턴은 한 번만 작성하고 이 조각을 어플리케이션 안에서 재사용하십시요. 이 방법이 코드를 유지하는데 더 효율적이고 쉽습니다.

CSS is anything but DRY. At times, it drips with repeated rules, declarations, and values. We’re constantly writing the same snippets of code for colors, fonts, and frequently-used patterns of style throughout our stylesheets. One look through a decent-sized CSS file, and a DRY software developer will weep, first with bewilderment, then frustration.

[프로그래밍에 비하면]CSS는 아무것도 아닐 수 있지만 CSS는 DRY적 입니다. CSS는 반복되는 규칙, 선언, 값들로 넘쳐납니다. 우리는 색상, 폰트, 자주 사용되는 스타일 패턴들을 위한 동일한 코드조각들을 끊임없이 작성합니다. 적당한 크기의 CSS파일을 한 번 보면 DRY 소프트웨어 개발자는 울지도 모르겠습니다. 처음에는 어리둥절하다가 혼란에 빠지게 됩니다.

“How the !@#$ do you maintain this?!” they’ll ask.

“너 썅 이거 어떻게 유지보수 하는 거니”라고 그들은 물어올 겁니다.

“Have I also told you about IE bugs?” you’ll reply with a bit of self-loathing.

“내가 너에게 IE버그들에 대해서도 말한적이 있니?” 여러분은 약간 자조적인 답변을 하겠지요.

##SO WHY IS CSS SO DIFFICULT TO WORK WITH? 왜 CSS 작업은 어려운가?

We can gather a hint of understanding why CSS has had its syntax limitations over the years from an essay by CSS co-inventor, Bert Bos (http://bkaprt.com/sass/3/):

우리는 CSS 공동 발명자 Bert Bos가 쓴 에세이([http://bkaprt.com/sass/3/](http://bkaprt.com/sass/3/))로부터 왜 CSS가 지난 수 년간 구문 한계를 가지고 있었는지를 이해할 수 있는 힌트를 얻을 수 있습니다.

	CSS stops short of even more powerful features that programmers use in their programming languages: macros, variables, symbolic constants, conditionals, expressions over variables, etc. That is because these things give power-users a lot of rope, but less experienced users will unwittingly hang themselves; or, more likely, be so scared that they won’t even touch CSS. It’s a balance. And for CSS the balance is different than for some other things.

	CSS는 프로그래머가 그들의 프로그래밍 언어에서 사용하는 좀 더 강력한 기능들까지 도입하는 것을 꺼려했습니다: 매크로, 변수, 상수, 조건문 등등. 그 기능들이 파워유저들을 많이 구원해줄 수는 있으나 더 경험이 적은 유저들에게는 스스로 목을 메는 꼴이 될 거라는 이유때문입니다; 또는 겁을먹고 CSS를 건드리기 무서워 할 가능성이 많습니다. 그것은 균형입니다. 그리고 CSS에 대해서 그 균형은 다른 것들과는 조금 다릅니다.

The original architects of CSS were concerned with adoption. They (rightfully) wanted as many people as possible creating websites. They wanted CSS to be powerful enough to style web pages and separate content from presentation, while being easy to understand and use. I can certainly respect that. At the same time, we have work to do, and that work is getting more complicated, more nuanced, and more challenging to maintain and to future-proof. 

CSS의 원래 설계자들은 많은 사람들에게 채택되는데에 더 관심이 많았습니다. 그들은 가능한한 더 많은 사람들이 웹사이트를 만들 수 있기를 원했습니다. 그들은 CSS가 이해하기 쉽고 사용하기 쉬우면서도, 웹페이지에 스타일을 입히고 내용과 표현을 분리하는 작업을 하는데 강력한 도구가 되기를 바랬습니다. 저는 그점을 확실히 존중할 수 있습니다. 동시에 우리는 일을 하고 있고 그 일은 점점 더 복잡미묘해지고, 유지와 미래경쟁력을 위해 더 노력해야합니다.

Fortunately, there are options to help us out here, and one of them is Sass.

다행이도 그것을 도와주는 여러 옵션들이 있고 그 중 하나가 Sass입니다.

#What is Sass?

Sass is a CSS preprocessor—a layer between the stylesheets you author and the .css files you serve to the browser. Sass (short for Syntactically Awesome Stylesheets) plugs the holes in CSS as a language, allowing you to write DRY code that’ll be faster, more efficient, and easier to maintain.

Sass는 CSS 전처리기 입니다— 여러분이 만든 스타일시트와 브라우저에 전송되는 .css파일 사이에 존재하는 층입니다. Sass(Syntactically Awesome Stylesheets)는 더 빠르고 효율적이고 쉽게 유지하게하는 DRY코드를 작성할 수 있도록 CSS와 결합하여 사용하는 언어입니다.

The Sass website ([http://sass-lang.com/](http://sass-lang.com/)) describes itself succinctly:

Sass 웹사이트([http://sass-lang.com/](http://sass-lang.com/))에서는 자신을 다음과 같이 간결하게 설명합니다:

	Sass is a meta-language on top of CSS that’s used to describe the style of a document cleanly and structurally, with more power than flat CSS allows. Sass both provides a simpler, more elegant syntax for CSS and implements various features that are useful for creating manageable stylesheets.

	Sass는 CSS 상위에 있는 메타 언어입니다. 그것은 CSS가 허용하는 것 보다 더 강력하게 문서를 깔끔하고 구조적으로 표현하는데 사용합니다. Sass는 더 단순하고 우아한 구문작성을 가능하게 하고 관리 가능한 스타일 시트를 만드는데 유용한 다양한 기능들을 구현할 수 있습니다. 

So while normal CSS doesn’t yet allow things like variables, mixins (reusable blocks of styles), and other goodies, Sass provides a syntax that does all of that and more—enabling “super functionality” in addition to your normal CSS. It then translates (or compiles) that syntax into regular ol’ CSS files via a command-line program or web-framework plugin.

일반 CSS가 재사용 가능한 스타일 블록을 심어 넣을 수 있는 변수와 다른 좋은 기능들을 허용하지 않는데 반하여 Sass는 일반 CSS가 그런 슈퍼 기능들이 가능하도록하는 모든 것들을 수행하는 구문을 제공합니다. Sass는 command-line 프로그램이나 웹 프레임워크 플러그인을 통해 그 구문을 일반 CSS파일로 번역(혹은 컴파일)합니다.

More specifically, Sass is an extension of CSS3, and its SCSS (“Sassy CSS”) syntax—which we’ll talk about in just a moment—is a superset of CSS3. Meaning, any valid CSS3 document is a valid SCSS document as well. This is integral to Sass being something you can “ease into.” Getting started with Sass syntax is painless, and you can use as little or as much as you’d like. Which also means converting an existing stylesheet from CSS to SCSS can be done in stages, as you learn and pick up more of Sass’s functionality.

더 구체적으로는 Sass는 CSS3의 확장이며 SCSS(“Sassy CSS”)라고 부르는 CSS3의 상위 집합입니다. 어떤의미냐면, 유효한 CSS3문서는 모두 유효한 SCSS문서라는 것입니다.  Sass 구문을 시작하는 것은 고통스럽지 않습니다. 원하는 만큼 적게 혹은 많이 사용할 수도 있습니다. 또한 이미 존재하는 CSS파일을 Sass의 기능들을 배우는 단계로서 SCSS로 변환할 수도 있습니다.

Later, when you’ve become fluent with Sass (and it won’t take long), it really does feel like a natural extension of CSS—as if it’s filling holes we all wish were filled by the CSS spec itself. This is why, once I started using Sass, I never once thought it was awkward or laborious—it just feels like CSS should feel. Once you try it, you’ll likely stick with it permanently.

나중에 여러분이 Sass를 잘 다룰 수 있게 되면(그렇게 되기까지 그리 오래걸리지 않을 거예요.), 자연스럽게 그것이 CSS의 확장이라는 느낌이 들겁니다—이것은 마치 우리가 바래왔던것처럼 CSS의 공백을 채워가는 것과 같습니다. 이것이 내가 Sass를 사용하기 시작하게된 이유이고 나는 결코 어색하거나 힘들다고 생각해본적이 없습니다—CSS가 그렇게 느껴지듯이 말입니다. 한 번 해보시길 바랍니다. 여러분은 아마 계속 그걸 고수하게 될 것입니다.

#Sass misconceptions Sass에 대한 오해

I mentioned earlier that I was reluctant to try Sass. This was partly due to a lot of misconceptions I had prior to using it. Do I need to know Ruby or advanced command-line shenanigans? Will I need to completely change the way I’ve been writing stylesheets? Will the CSS it outputs be bloated and unreadable?

앞서서 나는 Sass를 꺼려했었다고 언급했습니다. 이것은 부분적으로 내가 그것을 사용하기 전에 가지고 있던 많은 오해들 때문이었습니다. 루비나 커맨드라인 고급기술이 필요한거 아닌가요? 내가 작성해왔던 방식을 완전히 바꿔야 하는거 아닌가요? CSS가 비대해지고 읽을 수 없는 형태로 출력되는거 아닌가요?

Thankfully, the answer is “nope” for each of those questions, of course—but I do hear them pop up whenever someone mentions Sass on various internet channels. Let’s clear up a few things.

고맙게도 그 질문들에 대한 답은 물론 “아니요”입니다—그러나 나는 누군가 Sass에 대해서 언급할 때마다 그 질문들이 떠올랐습니다. 이제 몇 가지를 분명하게 정리 합시다.

##I’M AFRAID OF THE COMMAND LINE! 나는 Command line이 두렵다구!

I am by no means a command-line expert, but I’ve learned a bit here and there over the years—just enough to get me into trouble. I’m not afraid to traverse the file system with it or use Git commands, etc.

나는 Command-line 전문가는 아니지만 여기 저기서 조금씩 배웠다. Command-line을 사용해 파일 시스템을 돌아다니고 Git 명령어를 사용하는 데에는 두려움이 없다.

That said, I sympathize with designers and front-end developers who don’t want to go there. There’s a command-line phobia that exists among some folks. For Sass, there’s very little command-line action required—in fact, a single command is all you need to grasp. Additionally, there are apps and web frameworks that will obviate the need for the command line. (I’ll be introducing those in the next chapter).

그 말은, 내가 다시 그곳(콘솔창)으로 가고싶지 않아 디자이너들과 front-end 개발자들에게 공감했다는 것이다. 보통 사람들사이에 command-line 공포증이라는게 있다. Sass에서는 아주 약간의 Command-line 작업이 요구된다—사실 여러분이 숙지해야할 명령어는 단 하나에 불과하다. 또한, 명령어가 필요없도록 해주는 앱과 웹 프레임워크들이 있다.  

So, if you’re a command-line avoider, don’t let that stop you from trying Sass!

자, 여러분이 Command-line 기피자라고 하더라도 Sass를 포기하지 마십시요. 

##I DON’T WANT TO CHANGE THE WAY I WRITE CSS! 나의 CSS작성 방법을 바꾸고 싶지 않다구!

This was the misconception that I suffered from. I’m particular about the way my stylesheets are set up and organized. There’s a certain amount of craft that goes into the document. But remember, since the SCSS syntax is a superset of CSS3, you don’t have to change anything about the way you write CSS. Commenting, indenting, or not indenting, all your formatting preferences can remain the same when working in .scss files. Once I realized this, I could dive in without fear.

이것은 제가 겪었던 오해입니다. 저는 저만의 스타일 시트를 설정하고 정리하는 방법에 신경을 많이 씁니다. 그것은 꽤 공을 들여 문서화됩니다. 그러나 기억할 것은, SCSS 구문은 CSS3의 상위구문이기 때문에 여러분이 작성하는 방식을 조금도 바꾸지 않아도 됩니다. 주석달기, 들여쓰기, 또는 들여쓰지 않든 모든 여러분의 모든 서식 환경설정을 .scss 파일에 작업시 동일하게 유지할 수 있습니다. 저의경우 이것을 깨닫고 나서부터 두려움을 없이 뛰어들 수 있었습니다.

##I DON’T WANT SASS TO CHANGE THE WAY I DESIGN! 나는 내가 설계하는 방식을 바꾸고 싶지 않다구!

On the flip side, Sass won’t solve all of your problems or cure your bad habits. Inefficient, bloated stylesheets can be just as inefficient and bloated when using Sass. Good organization and smart thinking still apply here. In fact, there are instances where Sass can magnify bad practices, and we’ll go into that a bit as well. But when used properly and intelligently, Sass can be such a massive assist in creating websites.

다른 측면에서 보면, Sass가 여러분의 모든 문제를 해결해준다거나 여러분의 나쁜 습관들을 고쳐주는것은 아닙니다. 비효율적으로 비대해진 스타일시트는 Sass를 사용하더라도 비효율적이고 비대해질 수 있습니다. 좋은 구성과 스마트한 사고가 여전히 요구됩니다. 사실, Sass가 나쁜 관행을 확대할 가능성이 있고 우리모두 그렇게 될 가능성이 있을 겁니다. 그러나 우리가 적절하고 현명하게 사용한다면 Sass는 웹사이트를 만들때 대단한 조력자가 될 수 있을 것입니다.

Okay. Now that we have the particulars out of the way, let’s start having some fun. I think you’ll be amazed at what Sass can do. In the next chapter, we’ll set up our workflow—how Sass can fit into your process and how easy it is to use the command-line or apps. Let’s get Sassing, people.

좋습니다. 이제 세부적인 준비가 끝났으니 재미있는 일만 남았군요. 저는 여러분이 Sass가 무엇을 할 수 있는지 알게되면 매우 놀라게 될거라고 생각합니다. 다음 챕터에서 우리는 워크플로우 설정을 하게 될 것입니다—어떻게 Sass를 여러분의 작업프로세스에 맞추고 얼마나 Command-line을 사용하거나 앱을 사용하는 것이 얼마나 쉬운지 알 수 있습니다. 자 이제 여러분 Sass하세요!