#5 Golden Rules For Mobile Email Design

원문 : [5 Golden Rules For Mobile Email Design](http://www.sitepoint.com/golden-rules-mobile-email-design/)
저자 : [Massimo Cassandro](http://www.sitepoint.com/author/mcassandro/)
번역 : [공잠](http://gongjam.co.kr)

As I mentioned in my previous article, mobile email design is not only a content choreography issue, but involves many design elements.
제가 이전 기사에서 언급했듯이 모바일 이메일 디자인은 컨텐츠의 배치 문제만이 아니라 많은 디자인 요소의 문제를 포함하고 있습니다.

We should never consider the design for mobile devices a simple matter of catering to "screen size". Instead we need to have a comprehensive approach that takes into account the very different ways that people use the web — and email in particular — on small devices.
우리는 모바일 기기를 위한 디자인에서 "스크린 크기"를 맞추는 단순한 문제만 고려해서는 안됩니다. 대신에 우리는 사용자들이 작은 기기에서 웹을 사용하는 매우 다양한 방법을 고려한 포괄적인 목표를 가져야 합니다 — 이메일은 특히 그렇습니다.

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

Although I am not a fan of the "above the fold" issue (take a look at this old and very interesting article), the way emails are read on mobile devices means we should always consider their upper part as critically important.
비록 제가 "above the fold"(이와 관련하여 오래됬지만 매우 흥미로운 [이 글](http://iampaddy.com/lifebelow600/)을 보시길.)의 적극 지지자는 아니지만 모바일 기기에서 이메일이 읽혀지게하는 방법은 가장 중요한 내용을 윗 부분에 배치해야하는 것을 의미합니다.

A quick glance at this content is, in many cases, the best chance you'll have to draw your readers into reading more, so giving your them an easy to digest summary can make the difference.
많은 경우에 이 부분의 컨텐츠가 빠르게 읽혀지고 이것이 여러분의 독자들이 더 많은 내용을 읽을 수 있도록 끌어들일 수 있는 가장 좋은 기회가 될 것입니다. 따라서 여러분은 읽기 쉬운 요약문을 제공함으로써 그렇게 할 수 있습니다. 

A small paragraph at the top of the email can often do the trick.
이메일 상단의 작은 문단으로 그런 기교를 부릴 수 있겠지요.

![email summary](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382014email_summary.jpg)

This can also work very conveniently for some important clients that display these lines in their inbox list view (i.e. Gmail App, or Apple Mail on IOS and OSX).
이것은 몇몇 중요한 이메일 클라이언트 앱의 메일 박스 리스트 화면에 표시되기 때문에 매우 효과적일 수있습니다.(예컨대 지메일 앱이나 IOS/OSX에서의 애플 메일)

![gmail app](https://dl.dropboxusercontent.com/u/38351999/witinweb/blog/1425382024gmail_app.png)

#3. Resize fonts and images 픈트와 이미지들의 크기를 재조정할것.

This topic only applies to devices that support media queries. Unfortunately, we can't do anything for the others: sometimes they resize text and images themselves, but we can't really control this behaviour.
이 주제는 오직 미디어 쿼리를 지원하는 기기에만 적용됩니다. 불행하게도 우리는 다른 기기들을 위해서는 아무것도 할 수 없습니다: 때때로 그것들은 자동으로 텍스트와 이미지들을 조정하지만 우리가 그것을 컨트롤할 수 없습니다.

Media queries are currently supported by all IOS devices, the Android native email App (with some issues and remembering that Lollipop dropped it in favor of Gmail App), the newest Blackberry phones and a handful of others (for a more complete list, take a look at Campaign Monitor Guide to CSS or FreshInbox Email Client Media Query and Embedded Styles Support 2014).

Together they correspond to a significant and continuously growing percentage of email clients, so it's really mandatory to take care of them.

IOS devices have two main issues with font and image size:

Small font sizes are enlarged by default
Email width is based on the largest element
Font-size enlargement is usually not a critical problem, but in some cases it may cause some lines of text to be spliced potentially breaking your layout.

This can be easily fixed adding this line to your CSS:

1
* { -webkit-text-size-adjust: none; }
In the screenshot below you can see how the text size in the red area can change adding the -webkit-text-size-adjust rule (on the left) or removing it (on the right).