---
title: "[HTML] 파비콘(Favicon) 생성 및 적용하기"
excerpt: "주소창 아이콘을 만들고 적용하는 방법-ico파일 만들기"

categories:
  - HTML
tags:
  - [HTML]

permalink: /html/favicon/

toc: true
toc_sticky: true
 
date: 2022-01-22
last_modified_at: 2022-01-23

---
## 파비콘(Favicon)이란?
>파비콘(Favicon, 'Favorites+Icon')은 웹 브라우저의 주소창 옆에 표시되는 작은 아이콘으로,
>웹사이트나 웹페이지를 잘 나타낼 수 있는 로고(Logo)의 역할을 합니다.<br>
<p align="center">
  예시1) <img src="/assets/images/posts_img/html_favicon/favicon_01.png" width="200"><br>
  예시2) <img src="/assets/images/posts_img/html_favicon/favicon_02.png" width="200">
</p>
오늘은 홈페이지 제작 시 파비콘을 적용하는 방법을 알아보도록 하겠습니다.<br>

- 파비콘 적용 절차는 크게 2단계로 나뉩니다.

  ① 파비콘용 파일 만들기<br>
  ② HTML 파일 수정 및 적용하기<br>

- 파비콘의 **<mark>기본 확장자는 .ico이며 사이즈도 보통 16x16 크기</mark>**를 사용합니다.

  <font color="grey">(.png로도 표현이 가능하며 최근의 32x32 크기도 지원합니다.)</font>

## 1. 파비콘용 파일 만들기
웹 상으로 공유되는 파비콘도 많기 때문에 원하는 이미지를 찾아서 다운로드를 받을 수도 있습니다. 저는 직접 그린 이미지로 파비콘용 파일을 만들도록 하겠습니다.<br>

우선 파비콘으로 만들 이미지 파일을 미리 준비하고, 검색 엔진에 'favicon'을 검색하시면 이미지 파일을 파비콘으로 변경해주는 웹 페이지들이 많이 있습니다.<br>

저는 <a href = "www.favicon-generator.org/"> www.favicon-generator.org </a>를 이용하여 제작하도록 하겠습니다.<br>


사이트로 접속 후<br>
### ① 이미지 파일 선택하기
"<font color="red">파일 선택</font>"를 클릭하여 미리 준비한 이미지를 찾아서 선택합니다.
### ② 파비콘 이미지 생성하기
"<font color="red">Create Favicon</font>"을 클릭하여 파비콘 이미지들이 생성되기 시작합니다.
<center><img src="/assets/images/posts_img/html_favicon/favicon_03.png" style="zoom:60%;"/></center>

### ③ 압축파일 다운 받기
"<font color="red">Download the generated favicon</font>"을 클릭하여 압축파일을 다운 받습니다.
<center><img src="/assets/images/posts_img/html_favicon/favicon_04.png" style="zoom:60%;"/></center>

### ④ 압축파일 풀기
압축파일을 풀면 아래와 같이 여러 이미지들이 크기별로 생성되어 있는 것을 볼 수가 있습니다.<br>이중에서 **<mark>favicon.ico</mark>** 파일이 바로 파비콘으로 만들어진 파일입니다.
<center><img src="/assets/images/posts_img/html_favicon/favicon_05.png" style="zoom:60%;"/></center>

## 2. HTML 파일 수정 및 적용하기

html 파일이 있는 폴더로 ico 파일을 이동시키고,<br>
아래 형태로 코드를 **<mark>head 태그</mark>** 사이에 적용하면 됩니다.

```html
<link rel="apple-touch-icon" sizes="57x57" href="/apple-icon-57x57.png">
<link rel="apple-touch-icon" sizes="60x60" href="/apple-icon-60x60.png">
<link rel="apple-touch-icon" sizes="72x72" href="/apple-icon-72x72.png">
<link rel="apple-touch-icon" sizes="76x76" href="/apple-icon-76x76.png">
<link rel="apple-touch-icon" sizes="114x114" href="/apple-icon-114x114.png">
<link rel="apple-touch-icon" sizes="120x120" href="/apple-icon-120x120.png">
<link rel="apple-touch-icon" sizes="144x144" href="/apple-icon-144x144.png">
<link rel="apple-touch-icon" sizes="152x152" href="/apple-icon-152x152.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-icon-180x180.png">
<link rel="icon" type="image/png" sizes="192x192"  href="/android-icon-192x192.png">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="96x96" href="/favicon-96x96.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
<link rel="manifest" href="/manifest.json">
<meta name="msapplication-TileColor" content="#ffffff">
<meta name="msapplication-TileImage" content="/ms-icon-144x144.png">
<meta name="theme-color" content="#ffffff">
```
파비콘을 적용하면 아래와 같이 파비콘이 나타나는 것을 확인할 수가 있습니다.

<center><img src="/assets/images/posts_img/html_favicon/favicon_06.png"/></center>

## 💬 추가
위에 언급한 사이트 대신 <font color="grey"><A href = "https://realfavicongenerator.net/"> https://realfavicongenerator.net/</A></font>을 이용하시면 더욱 깔끔한 파비콘을 제작하실 수 있습니다!<font color="grey"> (사용 방법이 유사하므로 따로 포스팅하지는 않겠습니다.)</font>
<center><img src="/assets/images/posts_img/html_favicon/favicon_07.png" style="zoom:40%;"/></center>

💡 개인 기록용 블로그입니다. 오류가 있을 경우 언제든지 댓글 혹은 메일로 말씀해주시면 감사하겠습니다!
{: .notice}
[BACK TO TOP ↑](#){: .back-to-top }{: .align-right}