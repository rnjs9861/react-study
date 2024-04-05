# css header 영역

## 1. html 태그 작업

### 1.1. anchor 태그

- `<a href="보여줄 페이지 주소">글자</a>`
- `<a href="보여줄 페이지 주소">글자</a>`
- `<a href="http://www.naver.com" target="_blank">그림</a>`
  : 새 탭으로 보여주기(`target="_blank"`)

#### 1.2. img 태그

: 파일명.jpg, 파일명 .png, 파일명 .gif, 파일명 .svg
: 팁 1. 1순위 .png
: 팁 2. FrontEnd 는 .WEBP (Next.js 기본)
: 상식. .gif는 여러장의 이미지를 일정한 시간으로 교체하면서 보여주는 파일

- `<img src="경로/파일명.확장자 />`
- `<img src="경로/파일명.확장자 alt="이미지설명" />`

## 2. CSS 선택자 태그

### 2.1. 범위 안쪽에 있는 태그 찾기

- 범위 안쪽에 있는 태그 찾기

```css
.header-logo-slide img {
  ....;
}
```

### 2.2. display 간단 이해

- 신규프로젝트는 적극적으로 display:flex를 활용
- 유지, 보수 프로젝트는 `display: inline, display: inline-block` 을 조심하세요.

````txt
[정화섭] [오후 3:40] # css header 영역

## 1. html 태그 작업

### 1.1. anchor 태그

- `<a href="보여줄 페이지 주소"> 글자 </a>`
- `<a href="보여줄 페이지 주소"> 그림 </a>`
- `<a href="보여줄 페이지 주소" target="_blank">네이버</a>`
  : 새 탭으로 보여주기(`target="_blank"`)

### 1.2. img 태그

: 파일명.jpg, 파일명.png, 파일명.gif, 파일명.svg
: 팁 1. 1순위 .png
: 팁 2. FE 는 .WebP (Next.js 기본)
: 상식. .gif 는 여러장의 이미지를 일정한 시간으로 교체하면서 보여주는 파일

- `<img src="경로/파일명.확장자" />`
- `<img src="경로/파일명.확장자" alt="이미지설명" />`

## 2. CSS 선택자

### 2.1. 범위 안쪽에 있는 태그 찾기

```css
.header-logo-slide img {
 ...
  // 적극적으로 사용
  display: block;

  // 사용안함.
  display: inline;

  // 아주 가끔 쓰는데 엔터키 공백 들어감을 알고 있어야 함.
  display: inline-block;

  // 적극적으로 사용
  display: flex;

  // 자주활용
  // css 로 초기 모양을 설정하는 부분에 오류발생 소지가 있다.
  display: none;


````

```html
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>레이아웃</title>
    <style>
      div,
      footer,
      header {
        border: 5px solid;
        padding: 5px;
      }

      main {
        display: none;
      }
      .community {
        display: flex;
      }

      .news {
        display: inline-block;
        height: 400px;
        width: 25%;
      }
      .notice {
        display: inline-block;
        height: 400px;
        width: 25%;
      }
      .banner {
        display: inline-block;
        height: 400px;
        width: 25%;
      }
      .product {
        display: inline-block;
        height: 400px;
        width: 25%;
      }
    </style>
  </head>
  <body>
    <!-- 전체 레이아웃  -->
    <div class="wrap">
      <header class="header"></header>
      <main class="main">
        <div class="slide">슬라이드</div>
        <div class="community">
          <div class="news">뉴스</div>
          <div class="notice">공지사항</div>
          <div class="banner">배너</div>
          <div class="product">제품소개</div>
        </div>
      </main>
      <footer class="footer"></footer>
    </div>
    <div class="blocktest">블락임</div>
  </body>
</html>
```

### 2.3. flex 기초

- 관련사이트
  :https://codepen.io/enxaneta/pen/adLPwv
  :https://studiomeal.com/archives/197
  :https://flexboxfroggy.com/#ko
  : container (상자)
- container

```css
.header-logo-link {
  display: flex;
  /* 세로 중앙 */
  align-items: center;
  /* 가로 왼쪽 정렬 */
  justify-content: flex-start;
  /* 가로 가운데 정렬 */
  justify-content: center;
  /* 가로 우측 정렬 */
  justify-content: flex-end;
  /* 가로 양쪽 균등 정렬 */
  justify-content: space-between;
  justify-content: space-around;
}
```

- item 용 flex (요소들)
