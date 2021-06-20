---
layout: post
title: "!important로 css 덮어쓰기"
date: 2021-06-20 18:40:56 +0900
categories: css 사놓지
---

> _이번 시간에는 css를 덮어쒀 보자! 이 방법을 하면 라이브러리에 정의된 기본 css를 간편하게 변경할 수 있으며 내가 정의한 css가 적용되지 않는 불상사를 막을 수 있다 :)_

<br/>

- `css`에서는 동일한 속성을 여러번 설정하면 그 중 나중에 설정한 값이 적용된다.
- 하지만, 예외적으로 나중에 설정한 값이 적용되지 않아야 한다면? 아래 예시 코드를 보자
- 코드를 보면, 제일 마지막에 설정한 컬러가 적용되는 걸 볼 수 있다.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="css,result" data-user="kumjungmin" data-slug-hash="gOgwbxx" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="important 전">
  <span>See the Pen <a href="https://codepen.io/kumjungmin/pen/gOgwbxx">
  important 전</a> by KumJungMin (<a href="https://codepen.io/kumjungmin">@kumjungmin</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br/>

- 하지만 속성값에 `!important`를 추가하면, 먼저 작성한 속성이 적용된다!

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="css,result" data-user="kumjungmin" data-slug-hash="oNBzgoL" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="important 후">
  <span>See the Pen <a href="https://codepen.io/kumjungmin/pen/oNBzgoL">
  important 후</a> by KumJungMin (<a href="https://codepen.io/kumjungmin">@kumjungmin</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
