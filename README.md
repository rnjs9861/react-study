# css 최적화

# js Syntax 1장

1. Syntax(구문) : 약속된 문법, syntax error=문법 오류
2. Interpreter (번역) : 갤럭시 AI
3. 프로그래밍은 요구사항을 분석하고, (개인별로 작성 : 의사코드)
   Syntax를 이용해서
   적절한 자료구조(변수) + 적절한 함수를 활용하고,
   흐름을 제어하여 요구사항을 만족 시킨다.

# js Syntax 코드 위치

1. inline 방식

```html
<div class="wrap" onclick="alert('안녕');"></div>
```

2. 태그 방식

```html
<script>
  alert("반가워");
</script>
```

3. 외부파일 방식

```html
<script src="./js/script.js">
  alert("반가워"); //실행 안됨
</script>
```

# Swiper Slide 적용해 보기

- Slide 를 직접 코딩하지 마세요.
- 사용법을 배운다.
- Swiper(https://swiperjs.com/), Slick(https://kenwheeler.github.io/slick/), BxSlider(https://bxslider.com/) 가 있어요.
  ㄴ 권장

## 1. Swiper 슬라이드 적용시 주의 사항

- html 로드 완료 및 이미지 로드 완료 후 실행 권장.

```js
window.addEventListener("load", function () {
  // 실제 슬라이드 코드 배치하자.
});
```

# Swiper slide 적용해 보기 2.

- 데모사이트의 core메뉴를 통해서 참조한다.
- 기본 css 와 js 파일은 CDN으로 참조한다.

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.css"
/>
<script src="https://cdn.jsdelivr.net/npm/swiper@11/swiper-bundle.min.js"></script>
```

- 기본형 코드를 작성해서 원하는 영역에 배치한다. - 슬라이드 개수 만큼
  swiper-slide div 를 만든다.

```html
<div class="swiper 원하는이름">
  <div class="swipeer-wrapper">
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
    <div class="swiper-slide">내용</div>
  </div>
</div>
```

- css 로 `원하는이름` 을 찾아서 width, height를 100% 주자.
- css 로 `원하는이름` 에 절대로 display 등을 넣으면 안되요.

# Swiper slide 적용해보기 3.

- 외부 데이터연동(json)
- 데이터의 구조를 설계
- json 이란 javaScript Object Notation 입니다.

```json
[

  { "키": 값, "pic": "b1.png", "url": "#" },
  { "id": 2, "pic": "b2.png", "url": "#" },
  { "id": 3, "pic": "b3.png", "url": "#" },
  { "id": 4, "pic": "b4.png", "url": "#" }
]

```

# Swiper Slide 적용해 보기 4.

- 비동기 호출하기(vanila/pure) js)
  : BE 와 협업시 활용합니다.
- fetch 를 활용 가능
- async await 활용 가능

# js 3장

```txt
DOM(Document Object Model)
   - html 을 읽고, 수정 등등의 조작을 하는
     함수 (DOM API)
     document.querySelector(".wrap")

    클라이언트 사이드 API
    DOM, BOM, Canvas, XMLHttpRequest, fetch
    requestAnimationFrame, SVG, Web Storage,
    Web Component, Web Worker 등..

    Node.js   설치를 하면 자동으로
    npm 설치 됩니다. Node Package(js 소스) Manager
    https://www.npmjs.com/

    npm install 패키지명@버전
    node -v
    npm -v

    nvm (Node.js 의 버전을 자유롭게 변경하고, 설치)

    yarn install 패키지명@버전
```

# Swiper Slide 적용해 보기 5.

- 외부 js 파일을 이용한다.

```html
<script src="./js/파일명.js"></script>
```

```js
window.addEventListener("load", function () {
  //내용작성;
});
```

- swiper 에 보여줄 데이터를 외부 .json 파일로 연동한다.
  : 자료(데이터)를 만들어주는 동료가 백엔드
  : BE 와 협의가 필요하다. (협업의 기본)
  : 초기에는 가짜데이터(Dummy, Mockup) 를 가지고 작업

```json
[
{ "키명": "키값" },
{ "키명": "문자열" },
{ "키명": 55 },
{ "키명": true },
{ "키명": [] },
{ "키명": {} }
];

```

```json
[
  {
    "id": 1,
    "pic": "b1.png",
    "url": "#",
    "title": "AI 헬스케어의 <br/> 마일스톤을 찍다"
  },
  {
    "id": 2,
    "pic": "b2.png",
    "url": "#",
    "title": "카카오브레인의 <br/> 연구문화"
  },
  {
    "id": 3,
    "pic": "b3.png",
    "url": "#",
    "title": "PathFinder 2기의 <br/> 언어모델 활용기"
  },
  {
    "id": 4,
    "pic": "b4.png",
    "url": "#",
    "title": "칼로리의 꿈 <br/> 시리즈 ③"
  }
]
```

- json 데이터를 이용해서 자료를 추출한다.
  : 외부 주소를 통해서 자료를 불러들이기 위해 fetch 를 알고 적용한다.
  : 더불어서 크롬 개발자 도구 (F12)의 Network 탭을 알아야 한다.
  : 옵션으로 Fetch/XHR 을 선택할 수 있어야 한다.
  : request 와 response 를 구별하여 파악 할 수 있어야 한다.

```js
fetch("주소")
  .then((결과) => {
    const 접속결과 = 결과.json();
    return 접속결과;
  })
  .then((최종자료) => {
    // 하고 싶은 일 마음대로...
    // 우리가 할 일을 진행한다.
  })
  .catch((오류) => {
    // 오류 처리
  });
```

- 추출된 데이터로 html 을 생성한다.
  : 백틱(``)을 적극적으로 사용한다.

  ```js
  for (let i = 0; i < result.length; i++) {
    const data = result[i];
    // 템플릿 문법 필요(html 생성)
    const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background:url('${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
    slideTags += test;
  }
  ```

: html 을 배치한다.

```js
// 원하는 장소에 출력해 보자.
const whereTag = document.querySelector(".topslide .swiper-wrapper");
whereTag.innerHTML = slideTags;
```

- swiper 를 작동시킨다.
  : html 완료 후 슬라이드 생성하자.

```js
// DOM 을 다루려고 하는 목적인 경우
window.addEventListener("load", function () {
  //1. 외부에서 자료를 불러온다.
  const dataUrl = "./apis/topslide.json";

  fetch(dataUrl)
    .then((response) => {
      // Step 1. 자료 받아서 json 변경하기
      // 토큰을 js의 데이터로 변경하기
      const data = response.json();
      // 변환된 결과를 돌려주기
      return data;
    })
    .then((result) => {
      // Step 2. json 변경된 데이터 활용하기
      // 전체 글자 모음

      let slideTags = "";

      for (let i = 0; i < result.length; i++) {
        const data = result[i];
        // 템플릿 문법 필요(html 생성)
        const test = `<div class="swiper-slide">
          <a href="${data.url}" style="background:url('${data.pic}') no-repeat center; background-size: cover;">
            <p class="slide-title">
              ${data.title}
            </p>
          </a>
        </div>`;
        slideTags += test;
      }
      // 원하는 장소에 출력해 보자.
      const whereTag = document.querySelector(".topslide .swiper-wrapper");
      whereTag.innerHTML = slideTags;

      //기본코드를 넣어보자.
      var topSlide = new Swiper(".topslide", {});
    })

    .catch((error) => {
      console.log(error);
    });

  //then->성공했을때 catch->에러 났을때

  //2. 자료를 이용해서 슬라이드에 배치할 html 을 만든다.
  //3. html 완성후 swiper 를 생성한다.
});
```

# Swiper Slide 적용해 보기 6.

-[옵션](https://swiperjs.com/demos#autoplay)
:loop
:autoplay
:effect
:speed
:pagenation(https://swiperjs.com/demos#autoplay)
:페이지네이션 디자인 수정하기 참조!

```css
.bannerslide .swiper-pagination {
  bottom: 30px !important;
}
.bannerslide .swiper-pagination-bullet {
  width: 4px !important;
  height: 4px !important;
  background: #ffffff !important;
  opacity: 0.7 !important;
  border-radius: 4px !important;
  transition: width 0.3s;
  margin: 0 2px !important;
}
.bannerslide .swiper-pagination-bullet-active {
  background: #ffffff !important;
  opacity: 1 !important;
  width: 20px !important;
}
```
