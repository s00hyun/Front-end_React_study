# Chapter 03. CSS 입문
#웹 #프론트엔드 #CSS
---
## 1. CSS 문법 개요

* 구조
	* 선택자 { 속성: 값; }
	* `h1 { color: red; }`
* 선택자(selector)
	* HTML에 스타일(CSS)을 적용하기 위해 HTML의 특정한 요소를 선택하는 사인(sign)
	* ex. H1, P
    * `.class-name { color: blue; }`
* 속성(properties)
* 값(value)


## 2. CSS 선언 방식

### 1) 태그에 직접 작성하기(인라인)
* HTML 태그에 직접 작성
* 선택자 필요 X

### 2) HTML에 포함하기(내장)
* HTML의 `<style></style>`안에 작성

### 3) HTML 외부에서 불러오기
* `<link rel="stylesheet href="/css/main.css">`
* 외부의 별도 main.css 파일에서 CSS를 가져와 HTML 전체에 적용
* 상대경로, 절대경로


## 3. CSS의 속성: 크기

### 1) 속성
* 크기, 여백, 색상 등의 스타일을 지정
* `width`: 가로 너비(pixels) 
    * default=auto(전체 가로 너비의 100%)
* `height`: 세로 너비(pixels)
    * default=auto(요소의 크기만큼 높이가 결정됨)
* `background`: 배경색
* `font-size`: 폰트 크기(pixels, default=16px)
* `margin`: 요소의 바깥 여백(pixels) 
    * 단축 속성
    * 개별 속성
        * `margin-top`
        * `margin-right`
        * `margin-bottom`
        * `margin-left`
    * `margin=auto`: 수평 중앙 정렬
* `padding`: 요소의 내부 여백
    * div 요소의 내부에 여백이 추가되면 요소의 크기가 추가된 여백만큼 커진다.
    * 단축 속성
        ```
        padding: 20px 0; /* 상하 20px, 좌우 0px */
        ```
    * 개별 속성
        * top, right, bottom, left


## 4. CSS의 속성: 색상

* `color`
    * 요소의 **글자 색상** 지정
    * 주의: `font-color`(X), `text-color`(X)

* `background`
    * 요소의 **배경 색상** 지정
    * 단축속성
        * 배경의 위치, 특성도 지정 가능
    * 정확히 배경의 색상만 지정하려면 `background-color`를 사용


## 5. CSS 예제

### div 요소 가로로 정렬하기
```
<div class="menu clearfix">
    <div class="menu-item">Personal</div>
    <div class="menu-item">Open Source</div>
    <div class="menu-item">Business</div>
    <div class="menu-item">Explore</div>
</div>
```
```
.menu-item {
    float: left;
}
.clearfix::after {
    content: "";
    display: block;
    clear: both;
}
```
> 요소를 가로로 정렬하는 것이 `float: left;`의본래 목적은 아니므로, `clearfix`를 통해 해제(?)해 주어야 한다.

### 1) 이미지 하단의 여백 제거하기
```
<div class="logo">
    <img src="https://heropcode.github.io/GitHub-Responsive/img/logo.svg" alt="GitHub logo">
</div>
```
```
.logo {
    float: left;
    margin-right: 5px;
}
.logo img {
    display: block;
}
```
> `img` 태그로 이미지를 삽입하면 이미지 하단에 여백이 생기는 현상이 발생한다. 이 여백을 제거하기 위해 `display: block;`을 `img`태그의 CSS에 추가한다.

> `logo` 클래스 내부의 `img` 태그에만 이를 정의하려면 띄어쓰기를 이용한다.(`.logo img`)

### 2) div 영역 중앙에 요소들을 배치하기 (수직 중앙 정렬)
1. 바깥 박스의 위, 아래에 여백을 추가
2. 수평 중앙 정렬
    * `margin: auto;`

### 3) 기타
* CSS를 정의할 때에는 HTML 요소 순서에 맞춰서 작성하는 것이 유지/보수에 좋다.