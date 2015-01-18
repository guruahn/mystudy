#Grid System Comparison: Bootstrap 3 vs. Foundation 5

원문 링크 : [http://www.sitepoint.com/grid-system-comparison-bootstrap-vs-foundation/](http://www.sitepoint.com/grid-system-comparison-bootstrap-vs-foundation/)

by [George Martsoukos](http://www.sitepoint.com/author/gmartsoukos/), 번역 [gongjam](http://gongjam.co.kr/)

Bootstrap and Foundation are two of my favorite front-end frameworks, especially for rapid website prototyping. Both come with ready-to-use components that speed up my workflow. Beyond their small differences, most of their fundamental features look similar to me. Bootstrap과 Foundation 둘 모두 내가 좋아하는 프론트엔드 프레임워크들이며 특히 웹사이트 프로토타입을 빠르게 만들 수 있습니다. 두 가지 프레임워크 모두 나의 워크플로우 속도를 향상시켜줄 수 있도록 바로 사용할 수 있는 컴포넌트들이 미리 구성되어 있습니다. 내가 보았을때 이 둘은 약간의 차이를 제외하면 기본적인 특징들은 대부분 유사합니다.

In this article, I’ll cover the basics of their grids. First, I’ll show you how they’re structured, describing their key components, and how they differentiate depending on the screen size. Then, I’ll go over a real example that will help you put the knowledge gained into practice. 이 글에서는 두 프레임워크의 기본 그리드 시스템에 대해 다룰 것입니다. 먼저 두 프레임워크가  그리드를 어떻게 구성하는지, 그리고 스크린 사이즈에 어떻게 의존하고 있는지 차이점을 얘기하겠습니다. 그리고 실제 예제를 통해 연습할 수 있도록 하겠습니다.

자 시작해봅시다.

##미디어 쿼리

Bootstrap과 Foundation의 그리드 시스템을 분석하기 전에 먼저 