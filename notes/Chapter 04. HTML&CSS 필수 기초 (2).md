# Chapter 04. HTML & CSS 필수 기초 (2)

#웹 #프론트엔드 #HTML #CSS
> 이 포스트는 SW마에스트로 자기주도학습으로 패스트캠퍼스의 `웹 프론트엔드 올인원 패키지 Online`을 수강하면서 작성한 노트입니다.

# 3. 컨텐츠 구분 태그
* `h1`~`h6`
    * 6단계의 문서 제목을 구현함
        * 큰 주제(h1) ---> 작은 주제(h6)
    * **제목 폰트 크기를 줄이기 위해 사용하지 말 것. font-size 속성을 사용해야 함**
    * **제목 단계를 건너뛰는 것을 피할 것. h1, h2, ... 순차적으로 기입하기**
    * **h1은 한 페이지에 하나만 사용하기**
* `header`
    * 로고, 메뉴
    * 하위 요소로 사용할 수 없음
* `footer`
    * 주소, 사업자 
    * 하위 요소로 사용할 수 없음
* `main`
    * 문서의 핵심 컨텐츠를 설정 (블록 요소)
    * 한 문서 내에서 한 번만 사용
    * IE 지원 X
* `article`
    * **독립적**으로 구분되거나 **재사용 가능**한 영역을 설정함
* `section`
    * 문서의 일반적인 영역을 설정함
    * `article`을 담을 수 있음
        * 반대로, `article`이 `section`을 담을 수도 있음
* `aside`
    * 문서의 별도 콘텐츠를 설정
    * 광고, 기타 링크 
* `nav`(Navigation)
    * 다른 페이지 링크를 제공하는 영역을 설정
    * 메뉴(Home, About, Contact), 목차, 색인
* `address`
    * `body`, `article`, `footer` 등에서 1개 이상의 연락처 정보를 제공하기 위해 사용
    ```
    <address>
        <a href="mailto:ff152@gist.ac.kr">ff152@gist.ac.kr</a><br>
        <a href="tel:+13115552368">(311) 555-2368</a>
    </address>
    ```

# 4. 문자 컨텐츠
* `li`: list item (list item -- block element에 속함)
    * 단독 사용 불가
    * `ol` 또는 `ul`의 자식이어야 함
    * `value="7"`: 이하 항목의 순서를 7부터 다시 지정
* `ol`: ordered list (block)
    * `li`만 자식으로 사용 가능
    * `type="a/A/i/I/1"`: 번호 유형 선택
    * `reversed="reversed"` or `reversed`: 번호를 역순으로 표시
    * `started="2":` 번호 2부터 시작
* `ul`: unordered list (block)
    * `li`만 자식으로 사용 가능

* `dt`(definition term): 용어(key) (block 요소)
* `dd`(definition details): 설명(value) (block 요소)
* `dl`(description list): 용어와 설명의 집합 (block 요소)
    * dd, dt만을 포함해야 함
    * styling의 한계 -> ul, li를 이용
    ```
    <dl>
        <dt>Coffee</dt>
        <dd>Coffee is a brewed drink</dd>
        <dt>Milk</dt>
        <dd>Milk is a nutrient-rich, ...</dd>
    </dl>

    <ul>
        <li>
            <dfn>Coffee</dfn>
            <p>Coffee is a brewed drink</p>
        </li>
        <li>
            <dfn>Coffee</dfn>
            <p>Coffee is a brewed drink</p>
        </li>
    </ul>
    ```

* `<p></p>`(Paragraph): 하나의 문단을 설정 (block 요소)
* `<hr />`(Horizontal Rule): 문단의 분리를 위해 사용 (block 요소)
    * 수평선으로 표시됨
        * block 요소이므로, 상하좌우에 모두 선이 표시됨
            * border: 2px -> 실제로는 4px이 출력됨
        * `border: none; border-top(or border-bottom): dashed 2px;` 이용
    * 수평선을 그리기 위해서가 아닌 **의미적 관점으로만 사용해야 함**

* `pre`(Preformatted Text): 서식이 미리 지정된 텍스트를 설정 (block 요소)
    * 텍스트의 공백과 줄바꿈을 그대로 출력할 수 있음
        * 텍스트의 처음과 끝부분에 태그를 바로 붙여주어야 정확하게 출력됨 
    * 기본적으로 Monospace 계열의 글꼴로 출력됨
        > Monospace 계열의 글꼴은 각 글자의 너비가 동일함

* `blockquote`(Block Quotation): 인용문 설정
    ```
    <blockquote cite="인용된 위치(URL)">
    인용문
    </blockquote>
    ```

# 5. 인라인 텍스트
* `a` (inline)
    * 속성
        * download: 리소스 다운 용도로 사용되는 요소인지
        * **href**: 링크 URL
            * HTML5로 넘어오면서 필수 속성에서 선택 속성으로 변경됨 (생략 가능)
        * hreflang: 링크 URL 페이지 언어
        * rel: 현재 문서와 링크의 관계 (license, prec, next, ...)
        * **target**: 링크 URL의 표시 위치
            * _self: 현재 탭에 새로운 페이지를 띄움 (default)
            * _blank: 새로운 탭에 새로운 페이지를 띄움
    * type: 링크 URL의 MIME 타입 (주로 생략)
    * 모양을 입혀 버튼으로 사용할 경우 `display: block;`으로 변경해 주어야 함
    * 같은 페이지 내에서 이동하기
        ```
        <ul>
            <li><a href="#title1">제목1</a></li>
            <li><a href="#title2">제목2</a></li>
        </ul>
        <h2 id="title1">제목1</h2>
        <h2 id="title2">제목2</h2>
        <h2 id="title3">제목3</h2>
        ```
* `abbr`: title 속성으로 약어를 지정함

* `b`: Bring Attention. 문체가 다른 글자의 범위를 설정
    * 특별한 의미를 가지지 X
    * `<mark>`, `<strong>` 등의 다른 태그가 적합하지 않을 경우, **마지막 수단으로 사용**
    * 기본적으로 볼드체로 표시되나, 볼드체만을 위해 사용하지 말 것
        * 스타일링은 기본적으로 CSS를 이용해야 함

* `mark`: **사용자의 관심을 끌기 위해** 하이라이트를 쳐 줌 
    * CSS로도 충분히 지원됨
    * 의미보다는 시각적으로 특화된 태그
    * 기본적으로 글자 배경이 노란색으로 표시됨

* `em`: **의미 강조**를 표시
    * 중첩 가능 
        ```
        <em> <em></em> </em>
        ````
    * 중첩될수록 의미가 더 강조됨을 명시해 줌
    * 정보통신보조기기 등에서 강조해서 발음됨
    * 기본적으로 이탤릭체로 표시됨

* `strong`: 의미의 **중요성**을 나타냄
    * 기본적으로 볼드체로 표시됨

* `i`: `<em>, <strong>, <mark>, <cite>, <dfn>` 등의 태그로 표현하기 적합하지 않을 경우 사용
    * 아이콘이나 특수기호를 일반 텍스트와 구분하기 위해 사용

* `dfn`: Definition. 용어를 정의할 때 사용
    * `dl`, `dt`(정의), `dd`(설명)
        * 용어가 많을 경우, 용어의 정의를 설명하기 위해 사용
    * `dfn`: 용어를 정의하기 위해 사용
        ```
        <p><dfn id="def-internet">The Internet</dfn> is a global system of ...</p>
        ```

* `cite`: 창작물에 대한 참조를 설정
    * 기본적으로 이탤릭체로 표시됨

* `q`: 짧은 인용문을 설정
    * 긴 인용문의 경우, `<blockquote>`를 사용
    * cite 속성 사용 가능

* `u`: 밑줄효과
    * CSS로 충분히 커버 가능
        * `<span style="text-decoration: underline;">` 사용을 추천
    * 의미적인 부분은 딱히 없고, 순수하게 꾸미는 용도로 사용
    * `<a>`와 헷갈려 보이므로 사용에 주의

* `code`: 컴퓨터 코드 범위를 설정
    * 기본적으로 고정폭(Monospace) 글꼴 계열로 표시됨

* `kbd`: Keyboard input. 키보드 입력을 나타내는 텍스트 범위를 지정

* `sup`, `sub`: Superscripted text(위첨자), Subscripted text(아래첨자)

* `time`: 날짜나 시간을 나타내기 위한 목적으로 사용
    * datetime 속성을 이용해 유효한 날짜 문자를 지정
        * ex. Date 값(YYYY-MM-DD) 등

* `span`: 본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정
    * 인라인 요소, 의미 X
    * `div` 태그와 유사 
        * 블럭 요소, 의미 X
    * 특정 텍스트 부분에 CSS나 Javascript를 작성하기 위해 많이 사용됨

* `<br />`: 줄바꿈을 설정
    * 빈 태그 (닫히는 태그가 없이 사용)
    * HTML은 구조를 나타내기 위해 사용하는 것이므로, 줄 간격을 늘리기 위해 `br` 태그를 반복해서 사용하는 것은 지양해야 함
        * CSS의 `line-height` 이용

* `del`: Delete. 삭제(변경)된 텍스트의 범위를 지정
    * 현재는 유효한 정보가 아니어서 삭제했을 경우
    * cite 속성 -> 제거된 이유 or 변경사항을 설명하는 리소스의 URI(주소)
    * datetime 속성 -> 변경이 일어난 유효한 날짜 문자

* `ins`: Insert. 새로 추가(변경)된 텍스트의 범위를 지정
    * cite 속성 -> 변경사항 설명하는 주소
    * datetime 속성 -> 변경이 일어난 유효한 날짜 문자