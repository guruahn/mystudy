#What’s New in AngularJS 2.0

원문 : [What’s New in AngularJS 2.0](http://www.sitepoint.com/whats-new-in-angularjs-2/)

AngularJS has become one of the most popular open source JavaScript frameworks in the world of web application development. Since its inception, it has witnessed phenomenal growth in terms of adoption and community support—both from individual developers and corporations. 

AngularJS는 웹 어플리케이션 세계에서 자바스크립트 프레임워크 중 가장 인기있는 오픈소스중 하나가 되었습니다. 그것이 시작된 이래, 개인과 독립 사업자 둘 모두의 커뮤니티와 채택이라는 측면에서 경이로운 성장을 입증했습니다. 

From humble beginnings, Angular has matured into a client-side MVW framework (that’s Model-View-Whatever) for the building of complex single-page applications. It places equal importance on application testing and application writing, while simplifying the development process.

ANgularJS는 복잡한 단일 페이지 어플리케이션을 구축하기위한 클라이언트 측 MVW(Model-View-Whatever) 프레임워크로 성숙해갔습니다. 개발프로세스가 단순화 되면서 어플리케이션 테스트와 작성 둘 모두를 중요한 것으로 자리매김 시킵니다.

The current version of Angular is 1.3. This version is both stable and performant and is used by Google (the framework’s maintainers) to power a great many of their applications (it’s estimated that that there are over 1600 apps inside of Google running on Angular 1.2 or 1.3).

Angular의 현재 버전은 1.3입니다. 이 버전은 안정적이고 그것을 만든 구글이 수많은 훌륭한 어플리케이션을 작동시키기에 충분한 성능을 갖추었습니다.(구글 내부에 1.2 또는 1.3 버전에서 실행되는 응용 프로그램이 1600개가 넘게 있다는 것으로 추정됩니다)

Angular 2.0 was officially announced at the ng-conference in October, 2014. This version won’t be a complex major update, rather a rewrite of the entire framework and will include breaking changes!

Angular 2.0은 공식적으로 2014년 10월 ng-conference에서 발표되었습니다. 이 버전은 복잡한 주요 업데이트라기 보다는 전체 프레임워크를 제작성한것이며 단절적인 변화를 포함할 것입니다.

#Why Angular 2.0? 왜 Angular 2.0인가?

Before getting into further discussion about Angular 2.0 (which has an estimated release date of the end of 2015), let’s briefly consider the philosophy behind the new version. Angular 2.0 development was started to address the following concerns:

Angular 2.0에 대해 자세한 논의에 들어가기 전에 새 버전의 뒤에 있는 철학에 대해 간단히 살펴보겠습니다.(이 새 버전은 2015년 말 쯤 출시가 예상됩니다.) Angular 2.0 개발은 다음의 문제를 다루기 시작했습니다:

##Mobile

The new Angular version will be focused on the development of mobile apps. The rationale is that it’s easier to handle the desktop aspect of things, once the challenges related to mobile (performance, load time, etc.) have been addressed.

새 버전은 모바일 앱 개발에 초점을 맞출 것입니다. 그 근거는 모바일(성능, 로드 시간 등)에 관련된 이슈들이 해결된 이후에 테스크탑 측면이 다뤄지기 더 쉬울거라는 점입니다.

##Modular 모됼

Various modules will be removed from Angular’s core, resulting in better performance. These will find their way into Angular’s ever-growing ecosystem of modules, meaning you’ll be able to pick and choose the parts you need.

성능 개선의 결과로 다양한 모듈들이 Angular의 핵심에서 제거될 것입니다. 계속 증가하는 Angular의 모듈 생태계에서 여러분이 원하는 부분을 선택하고 가져올 수 있을 것입니다.

##Modern 현대화

Angular 2.0 will target ES6 and “evergreen” modern browsers (those automatically updated to the latest version). Building for these browsers means that various hacks and workarounds that make Angular harder to develop can be eliminated allowing developers to focus on the code related to their business domain.

Angular 2.0은 ES6와 “늘 싱싱한” 모던 브라우저(이들은 최종버전이 자동으로 업데이트 된다.)들을 타켓으로 삼을 것입니다. 이것은 개발을 더 어렵게 만드는 다양한 핵들과 2차 해결책들을 제거함으로서 개발자들이 자신의 비즈니스 도메인에 관련된 코드에만 집중할 수 있도록 해줍니다.

#What’s the Controversy? 논란

During the ng-conference there was no mention of a migration path to version 2.0. It was also pointed out that the jump to 2.0 version will lead to broken Angular 1.3 apps, as there won’t be any backwards compatibility. Since then, the developer community has been abuzz with uncertainty and speculation, with some developers questioning if it’s even worth starting a new Angular 1.3 project.

ng-conference 동안 버전 2.0으로 마이그레이션하는 방법에 대한 언급은 없었습니다. 그것은 또한 2.0버전으로 그대로 점핑할 경우 이전 버전과 어떠한 호환성도 없을 것이기 때문에 Angular 1.3 어플리케이션들이 깨질 수 있음을 의미합니다. 이 이후에 개발자 커뮤니티에서는 새로운 Angular 1.3 프로젝트를 시작할 가치가 있는지에 대한 몇몇 개발자들의 의문 제기에 대해 불확실성과 추측이 난무해왔습니다. 

#What Are the Changes? 어떤 변화가 있는가?

##AtScript

AtScript is a superset of ES6 and it’s being used to develop Angular 2.0. It’s processed by the Traceur compiler (along with ES6) to produce ES5 code and uses TypeScript’s type syntax to generate runtime type assertions instead of compile time checks. However, AtScript isn’t compulsory—you will still be able to use plain JavaScript/ES5 code instead of AtScript to write Angular apps.

AtScript는 ES6의 확대집합이며 Angular 2.0을 개발하는데 사용되었습니다. 이것은 ES5 코드를 생성하기 위해 Traceur 컴파일러로 처리되며 컴파일 시간 체크 대신 런타임 형식 (진위형)구문을 생성하는 데 TypeScript의 형식 구문을 사용합니다. 그러나 AtScritp는 필수가 아닙니다—여러분은 여전히 Angular 어플리케이션을 작성하기 위해 AtScrit 대신 일반 자바스크립트/ES5 코드를 사용할 수 있습니다.

##Improved Dependency Injection (DI) 의존성 주입 향상

Dependency injection (a software design pattern in which an object is passed its dependencies, rather than creating them itself) was one of the factors that initially differentiated Angular from its competitors. It is particularly beneficial in terms of modular development and component isolation, yet its implementation was plagued with problems in Angular 1.x. Angular 2.0 will will address these issues, as well as adding missing features such as child injectors and lifetime/scope control.

의존성 주입(그 자신 자체가 아니라 객체에 의존성을 전달하는 소프트웨어 디자인 패턴입니다)은 Angular의 다른 경쟁자들과 근본적으로 다른 이유중 하나입니다. 이것은 특히 모듈개발과 컴포넌트 분리의측면에서 유리합니다. 그러나 Angular 1.x에서 이것을 구현하는 데에 문제가 많았습니다. Anuglar 2.0은 이런 문제를 해결할 뿐만 아니라 자식요소 주입, lifetime/scope 제어와 같은 기능들도 추가될겁니다.

###Annotations 주석석

AtScript provides tools for associating metadata with functions. This facilitates the construction of object instances by providing the required information to the DI library (which will check for associated metadata when calling a function or creating an instance of a class). It will be also easy to override parameter data by supplying an Inject annotation.

AtScript는 함수와 메타데이터를 연결하는 도구를 제공합니다. 이것은 DI 라이브러리(함수를 호출하거나 클래스의 인스턴스를 생성 할 때 DI 라이브러리는 관련 메타 데이터를 확인합니다)에 필요한 정보를 제공함으로써 객체 인스턴스의 구성을 용이하게합니다. Inject 주석을 제공함으로서 파라미터 데이터를 쉽게 오버라이드 할 수 있을 것입니다.

###Child Injectors

A child injector inherits all the services of its parent with the capability of overriding them at the child level. According to requirement, different types of objects can be called out and automatically overridden in various scopes.

child injector는 자식레벨에 오버라이딩 할 수 있는 능력을 가지고 부모의 모든 서비스를 상속합니다. 요구에 따라 여러 타입의 객체에서 호출될 수 있고 자동으로 다양한 scope에서 오버라이드 됩니다.

###Instance Scope 

The improved DI library will feature instance scope control, which will become even more powerful when used with child injectors and your own scope identifiers.

향상된 DI 라이브러리는 인스턴스 스코프 제어를 특징으로 할 것입니다. 이것은 child injectors와 자기 자신의 scope 지시자를 함께 사용하면 더욱 강력해질 것입니다.

##Templating and Data Binding 템플릿과 데이터 바인딩

Let’s take a look at templating and data binding as they go hand in hand when developing apps.

애플리케이션을 개발할 때 함께가는 템플릿화와 데이터 바인딩에 대해서 알아봅시다.

###Dynamic Loading 동적 로딩

This is a feature which is missing from the current version of Angular. It will be addressed by Angular 2.0, which will let developers add new directives or controllers on the fly.

이것은 Angular의 현재 버전에서 누락된 사항입니다. 이것은 Angular 2.0에서 해결될 것이며 개발자들이 즉각 즉각 새로운 디렉티브들과 컨트롤러들을 추가할 수 있게 할 것입니다.

###Templating 템플릿

In Angular 2.0, the template compilation process will be asynchronous. As the code is based on the ES6 module spec, the module loader will load dependencies by simply referencing them in the component definition.

Angular 2.0에서 템플릿 컴파일 과정은 비동기적일 것입니다. 코드 ES6 모듈 사양을 기반으로, 모듈 로더는 단순히 구성 요소 정의들을 참조하여 의존성을 로드할 것입니다.

###Directives 디렉티브

In Angular 2.0 there will be three kinds of directives: Angular 2.0에서는 세 가지 종류의 디렉트브들이 있을 것입니다.

 -Component Directives – These will create reusable components by encapsulating logic in JavaScript, HTML or an optional CSS style sheet.
 - 컴포넌트 디렉티브 - 이것은 자바 스크립트, HTML 또는 선택 사양 인 CSS 스타일 시트에 로직을 캡슐화하여 재사용 가능한 구성 요소를 작성합니다.
 -Decorator Directives – These directives will be used to decorate elements (for example adding a tooltip, or showing/hiding elements using ng-show/ng-hide).
 - 장식적 디렉티브 - 이 디렉티브는 (툴팁이나 ng-show/ng-hide를 사용한 토글 요소와 같은) 장식적인 요소들을 사용하게 될 것입니다.
 -Template Directives – These will turn HTML into a reusable template. The instantiating of the template and its insertion into the DOM can be fully controlled by the directive author. Examples include ng-if and ng-repeat.
 - 템플릿 디렉티브 - 이것은 HTML을 제사용 가능한 템플릿으로 변환할 것입니다. 템플릿을 인스턴스화하고 그것을 DOM에 주입하는 것이 완전히 디렉티브 작성자에 의해 컨트롤되어질 것입니다. 예를 들면 ng-if 및 ng-repeat을 포함됩니다.

#Routing Solution 라우팅 솔루션

The initial Angular router was designed to handle just a few simple cases, yet as the framework grew, more and more features were bolted on. The router in Angular 2.0 has been reworked to be simple, yet extensible. It will include the following basic features:

초기 Angular 라우터는 단지 몇 가지 단순한 케이스를 처리할 수 있도록 설계되었습니다. 그러나 프레임워크가 성장함에 따라 더 많은 기능들이 묶여지게 되었습니다. Angular 2.0에서의 라우터도 역시 단순하게 설계되었지만 확장가능합니다. 이것은 아래의 단순한 기능들이 포함되어있습니다:  

 -Simple JSON-based Route Config
 -Optional Convention over Configuration
 -Static, Parameterized and Splat Route Patterns
 -URL Resolver
 -Query String Support
 -Use Push State or Hashchange
 -Navigation Model (For Generating a Navigation UI)
 -Document Title Updates
 -404 Route Handling
 -Location Service
 -History Manipulation

Now, let’s check out the features which make the improved router a catalyst to take Angular 2.0 to new heights.



##Child Router

The child router will convert each component of the application into a smaller application by providing it with its own router. It will help encapsulate entire feature sets of an application.

##Screen Activator

This will give developers finer control over the navigation lifecycle, via a set of can* callbacks:

 -canActivate – Allow/Prevent navigating to the new controller.
 -activate – Respond to successful navigation to the new controller.
 -canDeactivate – Allow/Prevent navigation away from the old controller.
 -deactivate – Respond to successful navigation away from the old controller.
 -These callbacks will allow the developer to return Boolean values, a Promise for that value, or a Navigation Command (for a lower level control).

##Design

All of this logic is built using a pipeline architecture which makes it incredibly easy to add one’s own steps to the pipeline or remove default ones. Moreover, its asynchronous nature will allow developers to a make server request to authenticate a user or load data for a controller, while still in the pipeline.

#Logging

Angular 2.0 will contain a logging service called diary.js—a super useful feature which measures where time is spent in your application (thus enabling you to identify bottlenecks in your own code).

#Scope

$scope will be removed in Angular 2.0 in favor of ES6 classes.

#Conclusion

There is a lot of excitement and buzz around Angular 2.0 at the moment and this will only heighten as its release date nears. The beginning of March will see the next ng-conf take place where it’s likely that more details of the next version will emerge.

Meanwhile opinion remains divided as to whether breaking change is a good thing. Proponents claim there are hard limits on the improvements that can be made to 1.x, whilst opponents are understandably nervous at the apparent lack of a migration plan.
