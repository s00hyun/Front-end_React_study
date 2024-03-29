# Chapter 02. HTML 입문
#웹 #프론트엔드 #HTML
- - - -
## 1. HTML 문법의 기본 형태
* 요소: <태그>content</태그>
	* `<h1>`: 제목
	* `<p>`: 문단

## 2. 속성과 값
* `<TAG 속성=“값”></TAG>`
* `<img src=“./my_photo.jpg” alt=“사진 삽입 실패 시 보여줄 문구” />`: 이미지 삽입
* `<div class=“name”>홍길동</div>`: _의미를 가지지 않음_

## 3. 부모 요소와 자식 요소 
* 조상 요소
* 부모 요소
* 자식 요소
* 하위 요소

## 4. 빈 태그(Empty tag)
* 닫히는 개념이 없는 태그들
	1. ‘/‘가 없는 빈 태그
		* `<TAG>`
	2. ‘/‘가 있는 빈 태그
		* `<TAG/>`
		* `<TAG />`
* HTML5에서는 이 2가지 형태를 다 사용할 수 있으나, 개발 환경에 따라 /를 붙이거나 붙이지 않는다.
	* 그러나 두 형태를 혼용해서는 안 된다.
* 거의 대부분의 빈 태그들은 닫히는 태그가 없으므로 범위가 존재하지 않는다. 따라서 태그의 의미보다 의미를 확장해서 쓸 수 있는 `속성=“값”`의 형태가 빈 태그에 포함되게 된다.

## 5. HTML의 범위와 구성, DOCTYPE(DTD)
* `<!DOCTYPE html>`
	* Document Type Definition
	* HTML 1, 2, 3, 4, X-, 5 중 어느 버전인지 문서의 형식을 명시해준다.
* `<html>`: html 문서의 영역 (정보 범위)
	* `<head>html 문서의 정보</head>`
	* `<body>html 문서의 구조</body>`
* `</html>`

## 6. HEAD 태그
* `<title>네이버</title>`
	* 웹 페이지의 제목. 웹 브라우저의 사이트 탭에 표시된다.
* `<meta>`
	* 기타 모든 정보를 나타내는 태그
		* `<meta charset=“UTF-8”>`: 문자 인코딩 방식(텍스트가 출력되는 방식) 명시
		* `<meta name=‘author’ content=“홍길동”>`: 제작자 == 홍길동
		*` <meta name=‘description’ content=“웹 페이지 설명”>`
	* `name`: 검색엔진 등에 제공하기 위한 정보의 종류 (메타데이터)
		* `author`, `description`, `keywords`, `viewport`, …
	* `content`: `name`이나 `http-equiv` 속성의 값을 제공
* `<link>`
	* **외부 문서(html, CSS, favicon) 연결** 에 사용
	* 빈 태그
	* 	`<link rel=“관계” href=“경로”>`
		* 	`rel`(필수): `stylesheet`, `icon`, …
		* `href`: 경로
* `<style>`
	*  html의 일부분으로 css를 작성할 경우 사용한다.
* `<script>`
	* JS 코드의 경로를 명시할 경우 또는 html 내부에 JS 코드를 직접 작성할 경우에 사용한다.

## 7. BODY 태그(div, image), 웹 표준 검사하기
* DIV
	* 막 쓰는 태그. 아무런 의미를 가지지 않는다. 모양을 만드는 데에 특화되어 있다.
	* CSS로 꾸미거나 JS로 동작을 제어하기 위해 쓰인다.
* IMG
	* HTML에 이미지를 삽입 시 사용한다.
	* CSS에서 삽입하는 방법도 있다.(background)
	* `<img src=‘./kitty.png” alt=“이미지 대체 텍스트”>`
		* `src`, `alt`는 필수 속성으로, 누락되어서는 안 된다.
			* 누락될 경우 웹 표준에 어긋난다.
* 웹 표준 검사하기
	* W3C validator에 url을 입력하면 기본적인 표준 여부를 검사해 준다.
		* [The W3C Markup Validation Service](https://validator.w3.org)
