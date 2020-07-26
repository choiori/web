# CSS

#### 1. flex : 엘리먼트들의 크기나 위치를 쉽게 잡아주는 도구

- flex를 사용하기 위해 컨테이너 태그에서 display: flex 속성 부여
- 정렬방향 flex-direction 바꾸기 (기본 row)
- 부모 요소 : flex container - flex 영향을 받는 전체 공간
- 자식 요소 : flex item - 아이템들이 설정된 속성에 따라 배치되는 것
- 속성
  1. 컨테이너에 적용하는 속성
     - display: flex;
       - flex item들 가로 방향으로 배치
       - 자신이 가진 내용물의 width만큼 차지
       - 컨테이너의 높이만큼 height 설정 (정렬 속성으로 조정가능)
     - flex-direction
       - 아이템들이 배치되는 축의 방향을 결정하는 속성
       - row(가로/기본값), row-reverse(역순 가로), column(세로), column-reverse(역순 세로)
     - flex-wrap
       - 컨테이너가 더 이상 아이템들을 한 줄에 담을 여유 공간 없을 때, 아이템 줄바꿈을 결정하는 속성
       - nowrap(줄바꿈하지 않고, 넘치면 그냥 나감/기본값), wrap(줄바꿈), wrap-reverse(줄바꿈, 아이템 역순배치)
     - flex-flow
       - flex-direction과 flex-wrap을 한꺼번에 지정하는 단축 속성
       - flex-direction flex-wrap 순으로 쓰기
     - justify-content
       - 메인축 방향으로 아이템을 정렬하는 속성
       - flex-start(시작점으로 정렬/row:왼쪽, column:위/기본값), flex-end(끝점으로 정렬/row:오른쪽, column:아래), center(가운데 정렬), space-between(아이템들 사이에 균일한 간격), space-around(아이템들의 둘레에 균일한 간격), space-evenly(아이템들의 사이와 양 끝에 균일한 간격, IE, 엣지 지원x)
     - align-items
       - 수직축 방향으로 아이템을 정렬하는 속성
       - stretch(아이템들이 수직축 방향으로 끝까지 늘어남/기본값), flex-start(시작점으로 정렬/row: 위, column: 왼쪽), flex-end(끝점으로 정렬), center(가운데 정렬), baseline(텍스트 베이스라인 기준으로 정렬)
       - justify-content: center; + align-item: center; 아이템을 한 가운데에 놓을 수 있음
     - align-content
       - flex-wrap: wrap; 설정된 상태에서 아이템들의 행이 2줄 이상 되었을 때 수직축 방향 정렬을 결정하는 속성
       - stretch, flex-start, flex-end, center, space-between, space-around, space-evenly
  2. 아이템에 적용하는 속성
     - flex-basis
       - flex 아이템의 기본 크기 설정 (flex-direction: row; 너비/ column; 높이)
       - auto(해당 아이템의 width값 사용/기본값)
       - 해당 아이템이 width 따로 설정해놓지 않으면 content의 크기로 자동으로 설정
     - flex-grow
       - 아이템이 flex-basis의 값보다 커질 수 있는지 결정하는 속성
       - 숫자값 (0보다 큰 값: 해당 아이템 flexible box로 변하고 원래의 크기보다 커지며 빈 공간을 메우게 됨, 아이템들의 flex-basis를 제외한 여백 부분을 flex-grow에 지정된 숫자의 비율로 나누어 가짐), 0(기본값)
     - flex-shrink
       - 아이템이 flex-basis의 값보다 작아질 수 있는지를 결정
       - 숫자값(0보다 큰 값: 해당 아이템이 flexible box로 변하고 원래의 flex-basis보다 작아짐), 1(기본값-따로 지정하지 않아도 아이템이 flex-basis보다 작아질 수 있음), 0(아이템의 크기가 flex-basis보다 작아지지 않아서 고정폭의 column을 만들 수 있음- 고정 크기는 width로 설정)
     - flex
       - flex-grow, flex-shrink, flex-basis를 한번에 쓸 수 있는 축약형 속성
       - 생략해서 쓰면 0이 됨
       - 여백의 비가 아니라 영역 자체를 원하는 비율로 분할: flex-basis:0;
     - align-self
       - 해당 아이템의 수직축 방향 정렬 속성
     - align-items(전체 아이템의 수직축 방향 정렬)보다 우선권이 있음 (\*전체 설정보다 각각 개별 설정을 우선시함)
       - auto(align-items 설정을 상속 받음/기본값), stretch, flex-start, flex-end, center, baseline
     - order
       - 각 아이템들의 시각적 나열 순서 결정하는 속성
       - 숫자값(작은 숫자일 수록 먼저 배치)
       - 시각적 순서일 뿐 html 구조 바꾸는 것은 아니므로 접근성 측면에서 주의
     - z-index
       - z축으로 정렬가능
       - 숫자값(큰 숫자일 수록 위에 배치, 기본값이 0므로, 1만 설정해도 나머지 아이템 보다 위로 올라옴)

#### 2. position : html 요소가 위치를 결정하는 방식 설정, 정적위치 지정 방식을 제외한 나머지 다른 방식들은 전부 어떤 기준에 대해 해당 요소의 상대적인 위치를 설정하는 방식임.

1.  static: 기본값, 단순히 웹 페이지의 흐름에 따라 차례대로 요소들을 위치시킴, 위치를 지정하지 않을 때와 같음
    - 앞에 설정된 position을 무시할 때 사용
    - top, bottom, left, right 속성값 영향x
2.  relative: 해당 html요소의 기본위치(static일 때의 위치)를 기준으로 위치를 계산하여 설정함.
    - top, bottom, left, right 위치 설정
3.  absolute: relative와 달리 문서의 위치와 상관없이 위치를 지정가능, 가장 가까운 상위 요소를 기준으로 위치 결정 (상위 요소가 없으면 위치는 html body요소 기준으로 설정)
4.  fixed: 뷰포트(viewport)를 기준으로 위치를 설정
    - 웹 페이지가 스크롤 되어도 고정 위치로 지정된 요소는 항상 같은 곳에 위치
    - position 속성: position(앞에 기술한 내용), top, right, bottom, left, z-index, overflow(내용의 크기가 해당 요소의 박스를 넘어갈 때 어떻게 처리할지를 설정)
