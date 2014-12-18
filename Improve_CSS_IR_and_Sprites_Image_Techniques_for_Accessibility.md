#CSS IR & Sprites Image 기법의 접근성 향상 기술
지난 12월 9일 [한국웹접근성평가센터](http://www.kwacc.or.kr/)에서 주최한 2014 정보접근성동향세미나에 참가하게 되었습니다. 이번 세미나에서 여러 세션들이 있었지만 그 중에서 @yamoo9님이 발표한 내용을 공유하려 합니다. 이야기의 흐름을 좀 더 논리적으로 재구성하였습니다. 

나머지 세션들은 [웹페이지에서 PDF](http://www.kwacc.or.kr/Board/DataFile/Detail?page=1&contentSeq=570)를 읽어보는 것으로 충분할 것으로 생각됩니다. 참고로 yamoo9님의 발표는 PDF에서 43페이부터 시작합니다. yamoo9님이 직접 공유한 [슬라이드만 별도로 보실 수](http://www.slideshare.net/jeehoon/1209-10-2014)도 있습니다.

##HTML 이미지 컨텐츠 : 이미지 VS CSS 배경이미지
이미지 컨텐츠는 img태그를 사용하는 컨텐츠와 CSS 배경이미지로 제작한 컨텐츠로 나눌 수 있습니다. 

이미지 태그를 사용하는 컨텐츠는 상대적으로 디자인과 컨텐츠가 모두 중요하게 담겨있을 수 있으며 alt(alternate text)속성 값으로 접근성을 보완할 수 있으며 배경이미지에 비해 크기 조정이 자유롭습니다. 
    
    <img src="" alt="" />

반면에 배경이미지는 컨텐츠를 담기보다는 디자인적 요소에 치중하여 사용하는 경우가 많습니다. 그리고 크기 조정이 자유롭지 않은 단점이 있습니다. background-size 속성으로 크기를 조정할 수 있지만 CSS3에서 지원하는 속성이므로 모든 브라우져에서 지원하지는 않습니다.(IE9+) 배경이미지 컨텐츠는 Sprites 기법으로 많은 이미지를 한 장의 이미지로 만들어 사용할 수 있는 장점이 있습니다. 오늘 소개하는 내용이 바로 그것입니다. 

## [이미지 Sprites](http://www.w3schools.com/css/css_image_sprites.asp)
이미지 Sprites는 이미지 컨텐츠가 많은 경우 속도 저하되는 문제를 해결하기 위해 컨텐츠를 하나의 이미지에 늘어놓고 <img>태그가 아니라 배경이미지로 처리한 후 배경이미지의 위치조정으로 원하는 내용을 표현하는 기법입니다. 

![최경주재단 GNB 배경이미지](http://www.kjchoifoundation.org/skin/img/common/gnb.png)

위와 같은 이미지를 배경이미지로 지정한 후 배경이미지 위치값을 조정하여 원하는 부분만 보이도록 하고 나머지는 감추도록 하는 방식입니다. 이미지가 저것 뿐일까요. 이런 버튼 이미지들을 모두 별도의 이미지로 제작했다면 컨텐츠가 많은 사이트는 많은 이미지를 다운로드 하느라 버벅댈 것입니다. 

원래 가장 좋은 방법은 컨텐츠를 제작할때 텍스트는 웬만하면 이미지로 대체하지 않는 것입니다. 하지만 여러가지 이유로 국내 웹사이트는 과도하게 이미지를 사용하고 있습니다. 이런 문제점을 기각하더라도 여러 이미지 컨텐츠를 하나의 배경이미지로 처리하는 기법을 알아두면 좋을 것입니다.

###Sprites의 문제점
- 배경이미지를 사용하기 때문에 크기를 자유롭게 조정할 수 없습니다.
- 너무 많고 다양한 요소를 하나의 이미지에 담을 경우 위치값 계산이 복잡해지고 유지보수가 힘들어집니다.
- Retina 디스플레이 환경에 대응하기 어렵습니다.(이 문제는 모든 이미지 컨텐츠가 그렇겠죠.)
- 접근성이 취약합니다.

### 배경이미지 크기 조정을 위한 Polyfill
CSS3를 지원하지 않는 브라우저에서 배경이미지의 크기를 조정하기 위해서는 background-size polyfill을 사용해야합니다. polyfill이란 의미는 어떤 기능을 제공하는 소스코드의 한계(브라우저 호환성)을 메우기 위한 대체코드를 말합니다. 

1.IE8을 위한 polyfill로 Begavior 속성이 있습니다.

    #carousel li {
        display: none;
        height: 100%;
        background-position: center;
        background-repeat: no-repeat;
        background-size: contain;
        -ms-behavior: url(backgroundsize.min.htc);
        begavior: url(backgroundsize.min.htc)
    }
    
그러나 이 polyfill은 아파치 웹 서버 환경에서만 작동합니다.(Apache only / cover, contain만 가능)

2.IE 5.5 - 8 환경에서 가능한 polyfill : MS Filter
이 [링크](http://msdn.microsoft.com/en-us/library/ms532969%28v=vs.85%29.aspx)에서 MS Filter에 대한 자세한 내용을 볼 수 있습니다. 하지만 sprite를 사용하면 문제를 일으킵니다.

###다양하고 많은 이미지

![네이버의 메뉴 Sprites](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/sp_mn20140731.png)

갯수가 많지 않고 크기가 일정한 메뉴들을 하나의 이미지로 합쳐놓은 경우 배경이미지로 사용하기 쉽습니다. 하지만 위의 네이버 Sprites의 경우 간단하지가 않습니다. 이를 위해 쉽게 이미지를 합치면서 각 요소의 위치값을 CSS로 변환하는 다양한 툴을 사용하는 것이 좋습니다. [CSS Sprites generator로 검색](https://www.google.co.kr/webhp?sourceid=chrome-instant&ion=1&espv=2&es_th=1&ie=UTF-8#newwindow=1&q=css%20sprites%20generator)하면 다양한 툴을 보실 수 있습니다.

####아래는 야무가 추천하는 툴

**GUI Tools**
- [spritecow.com](spritecow.com) : 배경이미지 좌표값 얻기. 원하는 부분 드래그하면 - CSS로 변환
- [spriteme.org](spriteme.org) : 기존 웹사이트를 분석하여 제안해줌
- [arnaumarch.com](arnaumarch.com)
- [spritepad.wearekiss.com](spritepad.wearekiss.com) : 이미지 드래그앤드롭하면 자동으로 CSS변환. 단점은 웹 애플리케이션만 지원.(네이버에서 오프라인 프로그램 제공)

**Cml Tools**
1. SASS + Compass
2. Gulp.spritesmith
sprite폴더의 이미지를 가지고 markup과 css 만들어줌
3. Gulp-gulp-retina-sprites
4. git/yamoo9/Improve-IR-Accessible-Tech
    - 고대비 모드 감지
    - ImproveIR.js를 활용한 IR테크닉 접근성 향상
    - 별도로 의존하는 JS라이브러리 없음
    - 사용 간단
발표내용 : yamoo9@naver.com

###Retina 디스플레이 환경에 대응
이와 관련된 내용은 구글 디자이너 [Sebastien Gabriel](http://sebastien-gabriel.com/)의 글[Designer's Guide to DPI](http://sebastien-gabriel.com/designers-guide-to-dpi/home)을 참고하십시요. 번역글은 yamoo9님이 번역한 "[디자이너를 위한 DPI 가이드](https://github.com/yamoo9/PSD2HTML-CSS/blob/master/DesignersGuideToDpi.md)"를 참고하십시요.

###웹 접근성
배경이미지를 사용할때 고려해야할 웹 접근성 문제는 두 가지가 있습니다. 

- 대체텍스트 제공 : KWCAG 2.1, 6p에 의해면 배경 이미지는 제거하더라도 콘텐츠의 이해와 사용에 아무런 영향을 주지 않아야 하며 배경이미지를 제거하는 경우 배경 이미지가 의미하는 정보를 보조 기술로 전달하도록 해야한다고 명시하고 있습니다.
- 고대비 모드에서의 인식 : KWCAG 2.1, 10p에 의하면 고대비 모드 사용자가 인식할 수 있도록 콘텐츠를 제공해야 합니다.

네이버의 경우만 보더라도 이미지를 제거하거나 혹은 비활성화시키거나 고대비 모드일 때 스크린리더가 배경이미지의 정보를 읽을 수가 없습니다.

###CSS IR 기법으로 대체 텍스트 제공
IR기법은 컨텐츠를 배경이미지로 제공할때 CSS를 활용하여 대체 텍스트를 제공하는 기법입니다. 다름(ui.daum.net)에서 권장하는 IR기법은 아래 두 가지 입니다.

- IR기법1 : Phark Method, 권장, 텍스트 숨김(text-indent)
    + 스크린 리더 읽어줌.
    + 추가적인 태그 사용 안 함
    + CSS on/Image off 시 텍스트 안보임 : 오늘 강의의 핵심이 이것을 해결하는 것.
- IR기법2 : WA IR (권장)
    + 스크린 리더 읽어줌
    + CSS on / Images off 시 텍스트 보임
    + 추가적인 태그 사용함
    + position 속성 사용(성능관련이슈)
    + 완벽하지 않다: 상위 레이어가 하위를 감추고 있으므로 상위 레이어의 투명도에 따라 문제생길 수 있음. 또한 상위 레이어의 크기에도 영향을 받음.

##결론
**JS Improve IR Accessible**
yamoo9가 만든 자바스크립트 라이브러리입니다. IR기법을 사용하면서 위와 같은 접근성 문제를 해결해줄 수 있는 스크립트입니다. 고대비모드, CSS활성화, 이미지 활성화 상태를 감지하여 IR&Sprites 기법의 접근성을 향상시켜주는 방식입니다. Sprites 생성 툴과 함께 사용하면 배경이미지로 컨텐츠를 제작하면서 웹접근성도 향상시킬 수 있는 가장 쉬운방법이 아닌가 생각됩니다.

이 라이브러리관련 [슬라이드 자료](http://www.slideshare.net/jeehoon/1209-10-2014)가 공개되어있고 [깃을 통해 소스](https://github.com/yamoo9/Improve-IR-Accessible-Tech)를 받으실 수 있습니다. 


