---
layout: post
title: "캔버스로 둥근 모서리 사각형을 그려보자!"
date: 2021-06-20 18:40:56 +0900
categories: canvas 사놓지
---

> `canvas`태그를 사용하면 선, 면, 원 등 여러가지를 만들 수 있다. <br/> 그렇다면 모서리가 둥근 사각형은 어떻게 만들 수 있을까? <br/> 이번 시간에는 `quadraticCurveTo`를 사용하여 둥근 모서리를 만들어보자!

<br/>

## 1. quadraticCurveTo?

_둥근모서리 사각형을 만들기에 앞서, quadraticCurveTo에 대해 간단히 알아보자._

- `quadraticCurveTo`는 2차 곡선을 만들 때 사용하는 함수이다.
- `조절점`을 기준으로 `끝점`이 (x,y)인 베지어 곡선을 그린다.
  ![](https://images.velog.io/images/gicomong/post/ff22add3-629e-42fb-b9f9-fb3c64bed48f/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-06-20%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.09.41.png)
- `quadraticCurveTo`을 사용하면 둥근 사각형을 만들 수 있다.

<br/><br/>

## 2. 둥근 모서리를 위한 규칙

> `width(너비)`, `height(높이)`, `radius(둥근모서리)`, `x&y(시작점)` 변수가 있다. 이 변수를 사용하여 오른쪽 둥근 모서리를 그리는 모습을 살펴보자!

### A. 예시 보기

**a.** 먼저, `(x+width-radius, y)`까지 선을 그린다.
![](https://images.velog.io/images/gicomong/post/b7a9dd2b-8eff-408f-8965-12f3fa501412/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-06-20%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.25.40.png)

**b.** `(x+width, y)`을 기준으로 끝점이 `(x+width, y+radius)`인 2차 곡선을 생성한다.  
![](https://images.velog.io/images/gicomong/post/9a31df7a-b44f-479d-8629-8307dd7377a2/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-06-20%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.25.47.png)

<br/>

_위 설명을 실제 코드로 보면 아래와 같다._

```js
ctx.lineTo(x + width - radius, y); //a
ctx.quadraticCurveTo(x + width, y, x + width, y + radius); //b
```

<br/><br/>

### B. 필요한 데이터 보기

- 만약 여러분들이 네 모서리가 모두 둥근 사각형을 만들려면 아래와 같은 데이터가 필요하다.
  ![](https://images.velog.io/images/gicomong/post/2e81fa21-a81f-48e1-bfb1-a4c78ff07523/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-06-20%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.43.04.png)

<br/>

- 하얀색 박스부분이 `lineTo`를 사용하여 이동해야할 점이며,
- `quadraticCurveTo(빨간박스[기준], 보라색박스[끝점])`을 사용해 2차곡선을 그리면 된다.
  ![](https://images.velog.io/images/gicomong/post/f40248cc-0906-4ccc-a2ad-d6e4e7fc44a4/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-06-20%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%205.44.18.png)

<br/>
<br/>

## 3. 만들어보기

- 너비 200, 높이 50인 둥근 모서리 사각형을 만들어보자.
- 필요한 점 데이터들은 아래와 같다.

![](https://images.velog.io/images/gicomong/post/ba9d505c-727f-43bb-97c8-131a44371f24/1.jpeg)

<br/>

- 위 그림을 코드로 표현하면 아래와 같다.

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="js,result" data-user="kumjungmin" data-slug-hash="gOmyRaY" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="둥근모서리">
  <span>See the Pen <a href="https://codepen.io/kumjungmin/pen/gOmyRaY">
  둥근모서리</a> by KumJungMin (<a href="https://codepen.io/kumjungmin">@kumjungmin</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<br/><br/><br/><br/>

_**출처**_

아래 링크를 가면 많은 정보를 얻을 수 있지~

- <a href="https://fromyou.tistory.com/563">fromyou님의 포스팅, quadraticCurveTo로 2차 곡선 그리기</a>
- <a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/quadraticCurveTo">MDN Web Docs, quadraticCurveTo</a>
- <a href="https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=pjh445&logNo=220041200342"> 웹디웹퍼님의 포스팅, 모서리가 둥근 사각형 선 그리기</a>
