#Grid System Comparison: Bootstrap 3 vs. Foundation 5

원문 링크 : [http://www.sitepoint.com/grid-system-comparison-bootstrap-vs-foundation/](http://www.sitepoint.com/grid-system-comparison-bootstrap-vs-foundation/)

by [George Martsoukos](http://www.sitepoint.com/author/gmartsoukos/), 번역 [gongjam](http://gongjam.co.kr/)

Bootstrap and Foundation are two of my favorite front-end frameworks, especially for rapid website prototyping. Both come with ready-to-use components that speed up my workflow. Beyond their small differences, most of their fundamental features look similar to me. Bootstrap과 Foundation 둘 모두 내가 좋아하는 프론트엔드 프레임워크들이며 특히 웹사이트 프로토타입을 빠르게 만들 수 있습니다. 두 가지 프레임워크 모두 나의 워크플로우 속도를 향상시켜줄 수 있도록 바로 사용할 수 있는 컴포넌트들이 미리 구성되어 있습니다. 내가 보았을때 이 둘은 약간의 차이를 제외하면 기본적인 특징들은 대부분 유사합니다.

In this article, I’ll cover the basics of their grids. First, I’ll show you how they’re structured, describing their key components, and how they differentiate depending on the screen size. Then, I’ll go over a real example that will help you put the knowledge gained into practice. 이 글에서는 두 프레임워크의 기본 그리드 시스템에 대해 다룰 것입니다. 먼저 두 프레임워크가  그리드를 어떻게 구성하는지, 그리고 스크린 사이즈에 어떻게 의존하고 있는지 차이점을 얘기하겠습니다. 그리고 실제 예제를 통해 연습할 수 있도록 하겠습니다.

자 시작해봅시다.

##미디어 쿼리

Before analyzing Bootstrap’s and Foundation’s grid structure, let’s first look at the breakpoints that both offer for responsive layouts. These are used to set the number of the available grids that each framework offers. Bootstrap과 Foundation의 그리드 시스템을 분석하기 전에 먼저 각각이 제공하는 중단점을 살펴보겠습니다. 중단점은 각 프레임워크에서 제공하는 그리드를 설정하는데 사용됩다.

Bootstrap specifies four pixel-based media query breakpoints. The table below shows them: Bootstrap은 픽셀 기반의 미디어쿼리 중단점을 4가지 제공합니다. 아래 테이블을 보면:

|       Screens       |  Viewport Size | Container Width | Class Prefix |
|:-------------------:|:--------------:|:---------------:|:------------:|
| Extra small screens |    ＜ 768px    |       auto      |   .col-xs-*  |
|    Small screens    |    ≥ 768px    |      750px      |   .col-sm-*  |
|    Medium screens   |    ≥ 992px    |      970px      |   .col-md-*  |
|    Large screens    |    ≥ 1200px   |      1170px     |   .col-lg-*  | 

Foundation includes five em-based media queries. These are shown in the following table: Foundation은 em 기반의 미디어쿼리 중단점을 5가지 제공합니다. 아래 테이블을 보면 : 

|     Screens     |     Viewport Size    | Class Prefix (Default Grid) | Class Prefix(Block Grid) |
|:---------------:|:--------------------:|:---------------------------:|:------------------------:|
|  Small screens  |        ＜ 768px       |     .small-* .column(s)     |    .small-block-grid-*   |
|  Medium screens |        ≥ 768px       |     .medium-* .column(s)    |   .medium-block-grid-*   |
|  Large screens  |        ≥ 992px       |     .large-* .column(s)     |    .large-block-grid-*   |
|  XLarge screens |       ≥ 1200px       |        Not Activated        |       Not Activated      |
| XXLarge screens | ≥ 120.063em (1921px) |        Not Activated        |       Not Activated      |

미디어쿼리가 어떻게 동작하는지 보여주는  [Bootstrap demo]와 [Foundation demo]를 보길 권합니다. 여전히 조금 혼란스럽더라도 다음 섹션을 보면 분명해질 것입니다.

##그리드 구조

Bootstrap and Foundation each offer a mobile-first 12-column grid consisting of rows and columns. Columns are nested inside a row. They scale up to 12 for each row. Rows can be nested within the columns as well. Bootstrap과 Foundation은 행과 열로 구성된 12열 그리드를 제공합니다. 행은 열을 감싸게 되고 열은 12개까지 확대될 수 있습니다. 하나의 열도 여러 행들을 감쌀 수 있습니다.

Both frameworks come with many predefined classes you can use to set the size of your columns. As mentioned above, Bootstrap includes four media query breakpoints and Foundation has five. For each grid, there’s a different class prefix that can be used to set the size of the columns (see the two tables). 두 프레임워크 모두 열들의 크기들을 정할 수 있는 미리 정의된 클래스들을 가지고 있습니다. 위에서 언급한 것처럼 Bootstrap은 4개의 미디어쿼리 중단점을 가지고 있고 Foundation 은 5개의 중단점을 가지고 있습니다. 각 그리드에는 열의 크기를 정할 수 있는 클래스 prefix가 있습니다.

Bootstrap’s grid also requires a wrapper element for rows. This should have a class of either container or container-fluid. An element with the container class has a fixed width, which varies depending on the viewport (see the first table above), while an element with a class of container-fluid expands to fill the entire width of the browser window. Bootstrap의 그리드는 행들을 감싸는 Wrapper을 추가적으로 요구합니다. 이것은 container 또는 container-fluid 클래스를 가지고 있어야 합니다. container클래스를 가진 요소는 뷰포트에 따라 바뀌는 고정된 너비(상단의 표 Container Width 참고)를 가지고 container-fluid 클래스를 가진 요소는 브라우저 창의 전체 너비로 확장됩니다.

##Columns != 12?

It’s possible the number of columns in a grid is not exactly 12. In such a case, Bootstrap will float the last column to the left, while Foundation will float it to the right. If you want to override Foundation’s default behavior, add the end class to the last column. 그리드 안의 열 수가 정확히 12개가 아닐 수 있습니다. 이런 경우에 Bootstrap은 마지막 열을 왼쪽으로 float시킵니다. 반면에 Foundation은 오른쪽으로 float시킵니다. 만약 Foundation의 이런 기본 설정을 재정의하고 싶다면 마지막 열에 클래스를 추가하십시오.

To see this difference in action, you can take a look at a Bootstrap example and a Foundation example. 이런 서로 상이한 액션에 대해서는 [Bootstrap example](http://codepen.io/SitePoint/pen/raMZNJ)와 [Foundation example](http://codepen.io/SitePoint/pen/ogzPNm)을 보면 자세히 알 수 있습니다.

##Utility Classes

Both frameworks offer extra classes that give you great flexibility to customize their grids. 두 프레임워크는 그리드를 매우 유연하게 커스터마이징 할 수 있도록 추가적인 클래스들을 제공합니다.

Visibility classes let you show or hide content based on specific screen sizes. Offset classes allow you to center incomplete columns or adjust the amount of spacing between them. There are also classes that specify the order of columns across different devices. Visibility 클래스들은 여러분의 컨텐츠를 특정 스크린 사이즈에 기반하여 보이게하거나 감추게할 수 있습니다. Offset 클래스들은 불완전한 열들을 가운데로 정렬시키거나 그들 사이의 공백을 조정하도록 합니다. 서로 다른 기기에서 열에 특정 순서를 지정할 수 있는 클래스들도 있습니다.

Examples of all these different classes can be shown in this Bootstrap demo and this Foundation demo. [Bootstrap demo](http://codepen.io/SitePoint/pen/RNGYwX)와 [Foundation demo](http://codepen.io/SitePoint/pen/GgjXgR)에서 이 클래스들의 예제를 보실 수 있습니다.

##Block Grid

Beyond the default grid, Foundation supports another grid feature, called block grid. This allows you to create equal-sized columns with minimal markup. In order to use it, define the row as a ul element and the columns within it as li elements. Then specify the column sizes by applying the related classes (see the 2nd table above) to the ul element. Foundation은 그본 그리드 말고도 [block grid](http://foundation.zurb.com/docs/components/block_grid.html)라는 특별한 그리드를 제공합니다. 이것은 최소한의 마크업으로 같은 사이즈의 열들을 생성하도록 도와줍니다. 이것을 사용하기 위해서는 ul엘리먼트로 행을 정의하고 li엘리먼트로 열을 정의해야합니다. 그렇게 하면 열의 크기를 ul엘리먼트에 관련된 클래스(위 두 번째 표 참조)를 적용하여 열 크기를 지정합니다.

이쯤에서 여러분은 도대체 일반 그리드와 무슨 차이가 있는지 생각할 것입니다. 아래 두 가지 를 잠시 보겠습니다.

1. max-width가 각 행에 적용되는 일반 그리드와 다르게 block그리드는 전체 창 너비를 항상 가득 채웁니다.
2. block그리드는 같은 사이즈의 아이템에만 사용할 수 있습니다.

To better demonstrate how the grids differentiate, here’s a demo. 두 그리드의 차이점을 더 잘설명한 [demo](http://codepen.io/SitePoint/pen/WbGgbo)를 참고하십시요.

--------------------------

번역은 여기까지 입니다. 더 자세한 example은 아래 원문을 통해 보실 수 있습니다.

원문 링크 : [http://www.sitepoint.com/grid-system-comparison-bootstrap-vs-foundation/](http://www.sitepoint.com/grid-system-comparison-bootstrap-vs-foundation/)