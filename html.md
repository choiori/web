# html 태그 정리

0.  link

    - 외부 리소스의 연결 및 현재 문서와의 관계를 명시함 (html, css 스타일시트 등의 외부 문서를 가져오기)
    - 속성
      - rel : (필수) 현재 문서와 외부 리소스와의 관계
        stylesheet: 스타일시트로 연결할 때
        alternate: 문서의 대안 버전(프린트, 번역)으로 연결
      - href : 외부 리소스의 URL(절대,상대주소)
      - type : 외부 리소스의 MIME 타입 /\*MIME 타입이란 현재 웹에서 내용 유형을 말할 때 자주 쓰임 (css파일: text/css, js파일: text/javascript 등)

1.  div

    - **block**

    * 본질적으로 아무 것도 나타내지 않는 콘텐츠 영역을 설정 (구분, 꾸미는 목적으로 사용)
    * 여러 html 요소들을 하나로 묶어주어 css로 스타일을 변경하거나 자바스크립트로 특정 작업을 수행하기 위한 일종의 컨테니어로 자주 사용됨

2.  a

    - **inline**

    * 다른 페이지, 같은 페이지 위치, 파일, 이메일 주소, 전화번호 등 다른 URL로 연결할 수 있는 하이퍼링크를 설정 (Anchor, 외부로 내보내기)
    * 속성
      - 필수 속성 없음
      - download: 사용자가 하이퍼링크를 클릭할 때 해당 대상(target)으로 연결되지 않고 대신 해당 콘텐츠가 다운로드됨을 명시, 반드시 href 속성이 설정되어 있어야만 사용가능
        - <a download="파일 이름"> 다운로드되는 파일이름 명시, 생략가능
      - href: 이동하고자 하는 문서의 위치를 지정 (절대/상대주소)
      - rel:현재 문서와 링크된 문서 사이의 연관 관계를 명시
      - target: 링크를 클릭할 때 창을 어떻게 열지 설정
        \_self(현재 프레임), \_blank(새로운 창), \_parent(부모 프레임), \_top(현재 창에서 가장 상위 프레임)
      - title: 하이퍼링크에 대한 설명 (마우스 커서를 올리면 말풍선에 설명표시)

3.  p
    - **block**
    * 하나의 문단을 설정함(paragraph)
    * 자동으로 위아래 약간의 여백을 추가됨 ( 여백은 css의 margin 속성을 사용하여 조정할 수 있음)

4) span
   - **inline**
   * 본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정함
   * 그 자체만으로는 어떠한 의미도 가지지 않지만, class나 id와 같이 사용되어 스타일링을 위해 요소들을 그룹화하는데 유용하다.
     <-> div (block)

5. ol / ul / li

   - **ol, ul : block**
   - **li : list-item**

   * 각 항목<li>의 정렬된 목록<ol: ordered list>이나 정렬되지 않은 목록<ul: unordered list>을 설정함
   * ol 속성:
     - 필수 속성 없음
     - start : 항목에 매겨지는 번호의 시작 값 / 숫자(Number)
     - type : 항목에 매겨지는 번호의 유형 / a, A, i 등
   * ul 속성: 없음
   * li 속성:
     - value : 항목의 순서를 결정 / 숫자(Number) \*\*\*
   * <ol>, <ul> 은 자식으로 <li>만 가능
       + <li>은 단독으로 사용 할 수 없음
       + <ol>의 항목 순서는 중요도를 의미할 수 있음

6. section / nav / header / footer / article

   - **block**

   * <section>은 문서의 일반적인 영역을 설정함. 웹 문서 내에서 절단위로 구분하거나 의미가 비슷한 그룹으로 문서 구분할 때 사용
       + 일반적으로 <article> 요소로 표현된 하나의 글은 여러 개의 <section> 그룹으로 구성할 수 있음
   * <header> 문서에서 페이지 혹은 섹션의 머리말 영역을 나타낼 때 사용함.
       + (보통 로고, 웹 문서 제목, 소개, 검색 등을 포함)
   * <footer> 문서의 꼬리말에 해당하는 영역
       + (보통 저자 정보, 저작권 정보, 관련 링크 등을 포함)
   * <article> 독립적으로 구분되거나 재사용 가능한 영역을 설정함
       + (매거진, 신문기사, 블로그 등)
   * <nav> 다른 페이지 링크를 제공하는 영역을 설정함
       + (navigation, 보통 메뉴, 목차, 색인 등을 설정)

7. img:

   - **inline-block**

   * html 문서에서 이미지를 정의할 때 사용, html 문서에 직접 삽입되는 것이 아닌 html 문서에 이미지가 링크되는 형태
   * 속성
     - src, alt 필수 속성
     - src: 이미지 소스의 url을 명시
     - alt: 이미지 가져오는데 실패했을 경우 대체 텍스트를 명시
     - width, height: 각각 이미지의 너비와 높이를 명시

8. meta:

   - 해당 문서에 대한 정보인 메타데이터를 정의할 때 사용
   - <head>요소 내부에 위치
   - 속성
     - charset: 해당 문서의 문자 인코딩 방식을 명시
     - name: 메타데이터를 위한 이름을 명시
     - content: name 속성이나 http-equiv 속성과 관련된 값을 명시
     - 검색 엔진을 위한 키워드 정의 예시: <meta name="keyword" content="HTML, meta, tag, element, reference">
     - 웹 페이지에 대한 설명을 정의하는 예시: <meta name="description" content="HTML meta tag page">

9. table / 자식요소: tr, th, td
   - table : table
   - tr: table-row
   - th, td: table-cell
   * <table>태그는 데이터를 포함한 셀들의 행과 열로 구성된 테이블 정의, <tr>은 테이블의 각 행을 정의, <th>는 각 열의 제목을 정의, <td>는 하나의 테이블 셀을 정의함
   * <caption>,<thead>,<tfoot>,<tbody>요소 사용하여 테이블을 구분할 수 있음
