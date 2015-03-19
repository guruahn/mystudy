#What’s New in AngularJS 2.0

원문 : [What’s New in AngularJS 2.0](http://www.sitepoint.com/whats-new-in-angularjs-2/)

AngularJS has become one of the most popular open source JavaScript frameworks in the world of web application development. Since its inception, it has witnessed phenomenal growth in terms of adoption and community support—both from individual developers and corporations. 

AngularJS는 웹 어플리케이션 세계에서 자바스크립트 프레임워크 중 가장 인기있는 오픈소스중 하나가 되었다. 그것이 시작된 이래, 개인과 독립 사업자 둘 모두의 커뮤니티와 채택이라는 측면에서 경이로운 성장을 입증했다. 

From humble beginnings, Angular has matured into a client-side MVW framework (that’s Model-View-Whatever) for the building of complex single-page applications. It places equal importance on application testing and application writing, while simplifying the development process.

ANgularJS는 복잡한 단일 페이지 어플리케이션을 구축하기위한 클라이언트 측 MVW(Model-View-Whatever) 프레임워크로 성숙해갔다. 개발프로세스가 단순화 되면서 어플리케이션 테스트와 작성 둘 모두를 중요한 것으로 자리매김시킨다.

The current version of Angular is 1.3. This version is both stable and performant and is used by Google (the framework’s maintainers) to power a great many of their applications (it’s estimated that that there are over 1600 apps inside of Google running on Angular 1.2 or 1.3).

Angular의 현재 버전은 1.3이다. 이 버전은 안정적이고 그것을 만든 구글이 수많은 훌륭한 어플리케이션을 작동시키기에 충분한 성능을 갖추었다.(구글 내부에 1.2 또는 1.3 버전에서 실행되는 응용 프로그램이 1600개가 넘게 있다는 것으로 추정된다)

Angular 2.0 was officially announced at the ng-conference in October, 2014. This version won’t be a complex major update, rather a rewrite of the entire framework and will include breaking changes!

Angular 2.0은 공식적으로 2014년 10월 ng-conference에서 발표되었다. 이 버전은 복잡한 주요 업데이트라기 보다는 전체 프레임워크를 제작성한것이며 단절적인 변화를 포함할 것이다.

#Why Angular 2.0? 왜 Angular 2.0인가?

Before getting into further discussion about Angular 2.0 (which has an estimated release date of the end of 2015), let’s briefly consider the philosophy behind the new version. Angular 2.0 development was started to address the following concerns:

Angular 2.0에 대해 자세한 논의에 들어가기 전에 새 버전의 뒤에 있는 철학에 대해 간단히 살펴보자.(이 새 버전은 2015년 말 쯤 출시가 예상된다.) Angular 2.0 개발은 다음의 문제를 다루기 시작했다:

##Mobile

The new Angular version will be focused on the development of mobile apps. The rationale is that it’s easier to handle the desktop aspect of things, once the challenges related to mobile (performance, load time, etc.) have been addressed.

새 버전은 모바일 앱 개발에 초점을 맞출 것이다. 그 근거는 모바일(성능, 로드 시간 등)에 관련된 이슈들이 해결된 이후에 테스크탑 측면이 다뤄지기 더 쉬울거라는 점이다.

##Modular 모됼

Various modules will be removed from Angular’s core, resulting in better performance. These will find their way into Angular’s ever-growing ecosystem of modules, meaning you’ll be able to pick and choose the parts you need.

성능 개선의 결과로 다양한 모듈들이 Angular의 핵심에서 제거될 것이다. 계속 증가하는 Angular의 모듈 생태계에서 여러분이 원하는 부분을 선택하고 가져올 수 있을 것이다.

##Modern 현대화

Angular 2.0 will target ES6 and “evergreen” modern browsers (those automatically updated to the latest version). Building for these browsers means that various hacks and workarounds that make Angular harder to develop can be eliminated allowing developers to focus on the code related to their business domain.

Angular 2.0은 ES6와 “늘 싱싱한” 모던 브라우저(이들은 최종버전이 자동으로 업데이트 된다.)들을 타켓으로 삼을 것이다. 이것은 개발을 더 어렵게 만드는 다양한 핵들과 2차 해결책들을 제거함으로서 개발자들이 자신의 비즈니스 도메인에 관련된 코드에만 집중할 수 있도록 해준다.

#What’s the Controversy? 논란

During the ng-conference there was no mention of a migration path to version 2.0. It was also pointed out that the jump to 2.0 version will lead to broken Angular 1.3 apps, as there won’t be any backwards compatibility. Since then, the developer community has been abuzz with uncertainty and speculation, with some developers questioning if it’s even worth starting a new Angular 1.3 project.

ng-conference 동안 버전 2.0으로 마이그레이션하는 방법에 대한 언급은 없었다. 그것은 또한 2.0버전으로 그대로 점핑할 경우 이전 버전과 어떠한 호환성도 없을 것이기 때문에 Angular 1.3 어플리케이션들이 깨질 수 있음을 의미한다. 이 이후에 개발자 커뮤니티에서는 새로운 Angular 1.3 프로젝트를 시작할 가치가 있는지에 대한 몇몇 개발자들의 의문 제기에 대해 불확실성과 추측이 난무해왔다. 

#What Are the Changes? 어떤 변화가 있는가?

##AtScript

AtScript is a superset of ES6 and it’s being used to develop Angular 2.0. It’s processed by the Traceur compiler (along with ES6) to produce ES5 code and uses TypeScript’s type syntax to generate runtime type assertions instead of compile time checks. However, AtScript isn’t compulsory—you will still be able to use plain JavaScript/ES5 code instead of AtScript to write Angular apps.

AtScript는 ES6의 확대집합이며 Angular 2.0을 개발하는데 사용되었다. 

Improved Dependency Injection (DI)

Dependency injection (a software design pattern in which an object is passed its dependencies, rather than creating them itself) was one of the factors that initially differentiated Angular from its competitors. It is particularly beneficial in terms of modular development and component isolation, yet its implementation was plagued with problems in Angular 1.x. Angular 2.0 will will address these issues, as well as adding missing features such as child injectors and lifetime/scope control.

Annotations

AtScript provides tools for associating metadata with functions. This facilitates the construction of object instances by providing the required information to the DI library (which will check for associated metadata when calling a function or creating an instance of a class). It will be also easy to override parameter data by supplying an Inject annotation.

Child Injectors

A child injector inherits all the services of its parent with the capability of overriding them at the child level. According to requirement, different types of objects can be called out and automatically overridden in various scopes.

Instance Scope

The improved DI library will feature instance scope control, which will become even more powerful when used with child injectors and your own scope identifiers.

Templating and Data Binding

Let’s take a look at templating and data binding as they go hand in hand when developing apps.

Dynamic Loading

This is a feature which is missing from the current version of Angular. It will be addressed by Angular 2.0, which will let developers add new directives or controllers on the fly.

Templating

In Angular 2.0, the template compilation process will be asynchronous. As the code is based on the ES6 module spec, the module loader will load dependencies by simply referencing them in the component definition.

Directives

In Angular 2.0 there will be three kinds of directives:

Component Directives – These will create reusable components by encapsulating logic in JavaScript, HTML or an optional CSS style sheet.
Decorator Directives – These directives will be used to decorate elements (for example adding a tooltip, or showing/hiding elements using ng-show/ng-hide).
Template Directives – These will turn HTML into a reusable template. The instantiating of the template and its insertion into the DOM can be fully controlled by the directive author. Examples include ng-if and ng-repeat.