# Chapter 04. HTML & CSS 필수 기초 (1)

#웹 #프론트엔드 #HTML #CSS
> 이 포스트는 SW마에스트로 자기주도학습으로 패스트캠퍼스의 `웹 프론트엔드 올인원 패키지 Online`을 수강하면서 작성한 노트입니다.

# 1. HTML의 요소

## 1) 블록 요소
* DIV, H1, P
* 사용 가능한 최대 가로 너비를 사용함
* 크기(width, height)를 지정할 수 있음
    * `width: 100%;` `height: 0`에서 **출발**
    * default: `width: auto;` `height: auto;`
* 수직으로 쌓임
* margin, padding 상하좌우 모두 사용 가능하다.
* 레이아웃 잡을 때 사용
* `display: block;` (default)

## 2) 인라인 요소
* SPAN, IMG
* 필요한 만큼의 너비만 사용함
* **크기를 가질 수 없음**
    * `width: 0;` `height: 0`에서 **출발**
    * default는 블록 요소와 같지만 다르게 동작한다.
    * `display: block;` 을 이용해 강제적으로 블록 요소로 바꿀 수 있다.
        * 인라인 요소로 바꾸기: `display: inline;`
* 수평으로 쌓임
    * 같은 라인에서 정의한 요소는 요소 사이에 공백이 없다.
* margin, padding의 **상, 하는 사용이 불가**하다.
* TEXT 
* `display: inline;` (default)


# 2. HTML, HEAD, BODY, TITLE

> [HTML 요소 레퍼런스](https://developer.mozilla.org/ko/docs/Web/HTML/Element)

## 1) HTML
* ISO 639-1
    > [List of ISO 639-1 codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
    * `<html lang="ko">`
    * 한국어 -> ko
    * 영어 -> en
* `<!DOCTYPE html>`
    * HTML5 버전으로 해석해서 브라우저에 출력함

## 2) HEAD
* HTML 문서의 제목, 기타 정보, 스타일 직접 입력, 스타일 외부에서 가져와서 연결
* `meta`
    * 빈 태그
    * 속성 추가해 사용
    * `<meta charset="UTF-8">`
        > [Character encoding](https://en.wikipedia.org/wiki/Character_encoding)

        * EUC-KR: 완성형
            * 홍 길 동
            * 완성된 조합이 없는 경우에는 한글이 깨짐
            * 오래된 사이트에서 볼 수 있는 인코딩 방식
        * UTF-8: 조합형
            * ㅎ ㅗ ㅇ ㄱ ㅣ ㄹ ㄷ ㅗ ㅇ
            * 조합할 수 있는 경우의 수가 있으면 문자를 나타낼 수 있음
            * 대부분 이 인코딩 방식을 사용함
    * `http-equiv`
        * HTTP 헤더에 특정한 값을 담아서 전송할 수 있음
        * `name`속성과 함께 사용할 수 없음
        * `<meta http-equiv="X-UA-Compatible" content="IE=edge">`
            * IE에서 렌더링될 때, 최신 IE 버전으로 렌더링되도록 함
    * `name`
        * author, description 등 문서 레벨의 메타데이터의 이름을 정의함
        * `name=viewport`: 반응형
            * `width=device-width`: 디바이스의 가로 길이에 최적화
            * `initial-scale=1.0`: 확대/축소에 대해 1배로 시작
* `title`
* `style`
    * `<style type="text/css">`
        * 생략 가능
    * [MIME 타입](https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/MIME_types)

        * 클라이언트에게 전송된 문서의 타입을 명시
        * `text/plain`, `image/jpeg`, `video/mp4`, ...
    * body 태그 내에서도 동작하지만, head 태그 내에서 선언하는 것이 브라우저에 효율적임
* `base`
    * 문서에 포함된 모든 상대 URL들의 기준 URL을 나타냄
    * 주요 경로로, 단 한 번 사용됨
    * `./css/main.css`
    ```
    <base href="./css/">
    <link rel="stylesheet" href="main.css">
    ```
## 3) BODY
* 정보의 구조