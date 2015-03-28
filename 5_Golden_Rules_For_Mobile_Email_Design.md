#5 Golden Rules For Mobile Email Design

원문 : [5 Golden Rules For Mobile Email Design](http://www.sitepoint.com/golden-rules-mobile-email-design/)
저자 : [Massimo Cassandro](http://www.sitepoint.com/author/mcassandro/)
번역 : [공잠](http://gongjam.co.kr)

As I mentioned in my previous article, mobile email design is not only a content choreography issue, but involves many design elements.
제가 이전 기사에서 언급했듯이 모바일 이메일 디자인은 컨텐츠의 배치 문제만이 아니라 많은 디자인 요소의 문제를 포함하고 있습니다.

We should never consider the design for mobile devices a simple matter of catering to “screen size”. Instead we need to have a comprehensive approach that takes into account the very different ways that people use the web — and email in particular — on small devices.
우리는 모바일 기기를 위한 디자인에서 “스크린 크기”를 맞추는 단순한 문제만 고려해서는 안됩니다. 대신에 우리는 사용자들이 작은 기기에서 웹을 사용하는 매우 다양한 방법을 고려한 포괄적인 목표를 가져야 합니다 — 이메일은 특히 그렇습니다.

We’re going to identify some of the key considerations in mobile email composition. These rules are not meant to necessarily answer all the requirements of email design for mobile devices, but they are certainly a very good starting point.
우리는 이제 모바일 이메일 작성에 있어서 중요하게 고려해야하는 몇 가지를 확인할 것입니다. 이 룰들은 모바일 기를 위한 이메일 디자인의 모든 요구사항에 대한 필수적인 답을 의미하는 것은 아닙니다. 하지만 이 룰들이 매우 좋은 출발점을 제시한다는 점은 분명합니다.

#1. Keep email simple 단순함을 유지하라

Complexity kills — especially in email. Always avoid complicated structures that will inevitably fail when rendered on small screens. Remember that many devices simply don't support media queries (Gmail App for example), so you can't count on sophisticated content rearrangement techniques.
복잡성을 제거하세요 — 특히 이메일에서는 말입니다. 작은 스크린에서 랜더링이 제대로 되지 않는 복잡한 구조를 항상 피하십시요. 많은 기기들은(예를 들면 지메일 앱) 미디어 쿼리를 지원하지 않아서 복잡한 컨텐츠를 재배열하는 기술을 고려할 수 없습니다.

A linear and simple layout will deliver the best result in most cases.
선형적이고 단순한 레이아웃이 대부분의 경우에 가장 좋은 결과를 가져다줄 것입니다.

The overall size of the email is also important: your email can be not fully loaded if it over a preset size (around 100Kb). I haven't tested this issue in all clients but both Gmail App and IOS devices exhibit this behaviour (and Gmail web app too).
이메일의 전체 용량도 중요한 고려사항입니다: 여러분의 이메일이 만약 미리 설정된 용량(약 100Kb)을 넘는다면 완전히 로드되지 못할 수도 있습니다. 제가 모든 클라이언트에서 이 이슈를 테스트해보진 않았지만 지메일 앱과 IOS 기기에서(그리고 지메일 웹앱에서도)는 그런 현상이 나타났습니다.

In the screenshot below, you can see how the user has to click a link to view the entire message: this can discourage people from reading your email in full.
아래 스크린샷을 보면, 사용자들이 전체 메세지를 보기위해 링크를 클릭해야하는 것을 볼 수 있을텐데요: 이것은 사용자들로 하여금 전체 이메일 내용을 보는 것을 방해하는 것일 수도 있습니다.

![long email](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382039long_mail.jpg)

#2. Focus on email goals and mind the fold 이메일의 목표에 집중하라

Although I am not a fan of the “above the fold” issue (take a look at this old and very interesting article), the way emails are read on mobile devices means we should always consider their upper part as critically important.
비록 제가 “above the fold[^1]”(이와 관련하여 오래됬지만 매우 흥미로운 [이 글](http://iampaddy.com/lifebelow600/)을 보시길.)의 적극 지지자는 아니지만 모바일 기기에서 이메일이 읽혀지게하는 방법은 가장 중요한 내용을 윗 부분에 배치해야하는 것을 의미합니다.

[^1]: 역자주, “above the fold”라는 표현은 신문을 반으로 접었을때 위에 보여지는 면을 말하는 것으로 웹디자인에서는 스크롤하지 않고 볼 수 있는 웹페이지의 상단영역을 말한다. 비슷한 말로 “above the scroll”이 있다. 본문에서 말하는 “above the fold” 이슈라고 말하는 것은 액션을 일으키는 요소들을 페이지 상단에 배치해야 한다는 고전적인 웹디자인 규칙을 의미합니다. 최근에는 스크롤 해야 볼 수 있는 페이지 하단에서도 액션을 일으키는 요소의 배치가 효과적일 수 있다는 것이 밝혀져 “above the fold”에 집착하는 것이 좋지 않습니다. 위에서 소개한 글 [“Life Below 600px”](http://iampaddy.com/lifebelow600/)에서 이 쟁점에 대한 재미있는 이야기를 보실 수 있습니다. 또 다른 참고 글 [“above the fold의 정의”](http://www.marketology.co.kr/?p=816)

A quick glance at this content is, in many cases, the best chance you'll have to draw your readers into reading more, so giving your them an easy to digest summary can make the difference.
많은 경우에 이 부분의 컨텐츠가 빠르게 읽혀지고 이것이 여러분의 독자들이 더 많은 내용을 읽을 수 있도록 끌어들일 수 있는 가장 좋은 기회가 될 것입니다. 따라서 여러분은 읽기 쉬운 요약문을 제공함으로써 그렇게 할 수 있습니다. 

A small paragraph at the top of the email can often do the trick.
이메일 상단의 작은 문단으로 그런 기교를 부릴 수 있겠지요.

![email summary](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382014email_summary.jpg)

This can also work very conveniently for some important clients that display these lines in their inbox list view (i.e. Gmail App, or Apple Mail on IOS and OSX).
이것은 몇몇 중요한 이메일 클라이언트 앱의 메일 박스 리스트 화면에 표시되기 때문에 매우 효과적일 수있습니다.(예컨대 지메일 앱이나 IOS/OSX에서의 애플 메일)

![gmail app](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382024gmail_app.png)

#3. Resize fonts and images 폰트와 이미지들의 크기를 재조정할것.

This topic only applies to devices that support media queries. Unfortunately, we can't do anything for the others: sometimes they resize text and images themselves, but we can't really control this behaviour.
이 주제는 오직 미디어 쿼리를 지원하는 기기에만 적용됩니다. 불행하게도 우리는 다른 기기들을 위해서는 아무것도 할 수 없습니다: 때때로 그것들은 자동으로 텍스트와 이미지들을 조정하지만 우리가 그것을 컨트롤할 수 없습니다.

Media queries are currently supported by all IOS devices, the Android native email App (with some issues and remembering that Lollipop dropped it in favor of Gmail App), the newest Blackberry phones and a handful of others (for a more complete list, take a look at Campaign Monitor Guide to CSS or FreshInbox Email Client Media Query and Embedded Styles Support 2014).
미디어 쿼리는 현재 모든 IOS 기기들, 안드로이드 네이티브 이메일 앱(), 최신 블랙베리 폰들 등에서 지원하고 있습니다(더 완벽한 리스트는 [Campaign Monitor Guide to CSS](https://www.campaignmonitor.com/css/) 또는 [FreshInbox Email Client Media Query and Embedded Styles Support 2014](http://freshinbox.com/blog/email-client-media-query-and-embedded-styles-support-2014/)를 보십시요). 

Together they correspond to a significant and continuously growing percentage of email clients, so it's really mandatory to take care of them.
이들 모두 이메일 클라이언트로서 지속적으로 의미심장하게 성장하고 있으므로 주의 깊에 지켜봐야 합니다.

IOS devices have two main issues with font and image size:
IOS 기기들은 폰트와 이미지 사이즈와 관련된 두 가지 이슈를 가지고 있습니다.

 - Small font sizes are enlarged by default 작은 글꼴은 자동으로 확대됩니다.
 - Email width is based on the largest element 이메일의 너비는 가장 큰 요소에 맞춰집니다.

Font-size enlargement is usually not a critical problem, but in some cases it may cause some lines of text to be spliced potentially breaking your layout.
폰트 사이즈 확대 문제는 평소에는 심각한 문제가 아닐 수 있지만 몇몇 케이스들에서는 레이아웃이 깨져 일부 텍스트 줄이 겹칠 수도 있습니다.

This can be easily fixed adding this line to your CSS:
이 문제는 여러분의 CSS에 아래 줄을 추가함으로서 쉽게 고칠 수 있습니다.
```
    * { -webkit-text-size-adjust: none; }
```
In the screenshot below you can see how the text size in the red area can change adding the -webkit-text-size-adjust rule (on the left) or removing it (on the right).
아래 스크린 샷에서 위 코드를 삽입한 경우(왼쪽)과 하지 않은 경우(오른쪽) 발간 영역안의 텍스트 사이즈가 어떻게 달라지는지 볼 수 있습니다.

![iphone5 font size adjust](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382034iphone5_font_size_adjust.jpg)

Font-size management also affects the user experience on mobile. Small text that might be easily readable on desktop devices can have a different effect on small screen.
폰트 사이즈 조정은 또한 모바일에서의 사용자 경험에 영향을 미칩니다. 작은 텍스트가 데스크탑에서는 쉽게 읽힐 수 있으나 작은 스크린에서는 다른 결과를 가져올 수 있습니다.

In the example below, the summary text on the right version has been enlarged to make it easily readable and to attract users eyes:
아래 그림을 보면, 글자가 더 확대된 오른쪽 버전이 더 읽기 쉽고 매력적으로 보입니다.

![font resizing](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382019font-resizing.jpg)

In general, increasing the font size on mobile devices is a good practice, and especially for emails, where reading time is extremely condensed and you need to capture users attention quickly.
일반적으로 모바일 기기에서 폰트사이즈를키우는 것은 좋은 사례가 될 수 있습니다. 특히 글자를 극단적으로 빨리 읽는 이메일 에서는 사용자의 주의를 재빨리 사로잡아야 합니다.

##About images

I've just written about images in my [previous article](http://www.sitepoint.com/tricks-building-responsive-email/): optimizing images for mobile devices is an easy task based on classic max-width responsive images technique.
저의 [이전 기사](http://www.sitepoint.com/tricks-building-responsive-email/)에서 이미지에 대해 다룬적이 있습니다: 모바일 기기에서의 이미지 최적화는 고전적인 max-width 반영형 이지미 테크닉에 기반한 쉬운 작업이니다.

You can also load targetted images for devices which support media queries (take a look at A Slick, New Image Swapping Technique for Responsive Emails on Email On Acid blog, or Optimizing images for mobile on Campaign Monitor).
여러분은 미디어 쿼리를 지원하는 기기에 맞춰 이미지를 로드할 수 있습니다(Email On Acid blog의 [A Slick, New Image Swapping Technique for Responsive Emails](http://www.emailonacid.com/blog/details/C13/a_slick_new_image_swapping_technique_for_responsive_emails) 또는 Campaign Monitor의 [Optimizing images for mobile](https://www.campaignmonitor.com/guides/mobile/optimizing-images/)를 읽어보십시요).

4. Customize links and buttons

Email mobile design requires some tricks for links.

First, consider that the links will be clicked using… fingers, so keep them well spaced and strictly limit their number (Mobile device ergonomics and links in email newsletters article on Campaign Monitor blog addresses some interesting topics about this argument).

Size and spacing are a mandatory for buttons (typically they are Call to Actions links): make sure they are easily clickable and visible. Furthermore, always remember to add rules for anchors in your inlined CSS: Gmail App styles links as blue and underlines them by default.

One small potential problem is the links that Gmail and IOS add by default to telephone numbers (both), and to URL and email strings (in Gmail App only).

To avoid automatically auto-generated telephone links on IOS, you have to simply add this meta tag to your code: