# grid

## 1. flex vs grid

    - flex : 1차원, 한 방향 레이아웃
    - grid : 2차원, 두 방향 가로-세로 레이아웃 -> 더 복합적인 레이아웃 표현 가능

## 2. container vs item

    - container : 그리드의 영향을 받는 전체공간, items을 감싸는 부모 요소
    - items : 설정된 속성에 따라서 컨테이너 안에서 어떤 형태로 배치되는 것

## 3. grid를 이루는 요소

- 그리드 컨테이너 : 그리드의 전체 영역
- 그리드 아이템 : 그리드 규칙에 의해 배치되는 컨테이너의 자식 요소들
- 그리드 트랙 : 그리드의 행 또는 열
- 그리드 셀 : 그리드 아이템 하나가 들어가는 "가상의 칸(틀)"
- 그리드 라인 : 그리드 셀을 구분하는 선
- 그리드 번호 : 그리드 라인의 각 번호
- 그리드 갭 : 그리드 셀 사이의 간격
- 그리드 영역 : 그리드 라인으로 둘러싸인 사각형 영역, 그리드 셀의 집합

## 4. grid container 속성

| 속성                  |                 의미                 |                                                                                    사용 |
| :-------------------- | :----------------------------------: | --------------------------------------------------------------------------------------: |
| display               | 그리드 컨테이너 정의 / **필수작성**  |                                                                          display: grid; |
| grid-template-rows    |       명시적 행의 크기를 정의        |                                                        fr(공간 비율 단위), repeat()함수 |
| grid-template-columns |       명시적 열의 크기를 정의        |            fr(=fraction 공간 비율 단위: 숫자 비율대로 트랙의 크기를 나눔), repeat()함수 |
| row-gap               |       행과 행 사이의 간격 정의       |                                                               _그리드 선의 크기를 지정_ |
| column-gap            |   열과 열 사이의 간격(Line)을 정의   |
| grid-auto-rows        |       암시적 행의 크기를 정의        |                                                            (명시적 행 외부에 배치할 때) |
| grid-auto-columns     |       암시적 열의 크기를 정의        |                                                            (명시적 열 외부에 배치할 때) |
| align-content         |   그리드 콘텐츠를 수직(열 축) 정렬   | stretch가 기본값, 속성값: start, center, end, space-around, space-between, space-evenly |
| justify-content       |   그리드 콘텐츠를 수평(행 축) 정렬   |
| align-items           |     그리드 아이템들을 수직 정렬      |                                                     normal(stretch), start, center, end |
| justify-items         | 그리드의 아이템들을 수평(행 축) 정렬 |                                                                                         |

## 5. grid item 속성

| 속성              |                  의미                   |                      사용 |
| :---------------- | :-------------------------------------: | ------------------------: |
| grid-row-start    | 그리드 아이템(Item)의 행 시작 위치 지정 |            display: grid; |
| grid-row-end      |     그리드 아이템의 행 끝 위치 지정     |
| grid-column-start |    그리드 아이템의 열 시작 위치 지정    |
| grid-column-end   |     그리드 아이템의 열 끝 위치 지정     |
| align-self        |  단일 그리드 아이템을 수직(열 축) 정렬  |
| justify-self      |  단일 그리드 아이템을 수평(행 축) 정렬  |
| order             |    그리드 아이템의 배치 순서를 지정     | 숫자가 작을수록 앞서 배치 |

## 6. grid 함수

    1. repeat()
        - 행/열의 크기 정의를 반복
        - '반복되는 횟수' + 행/열 크기 정의
        - ex) grid-template-columns: repeat(9, 100px);
    2. minmax()
        - 행/열의 최소/최대 크기
        - ex) minmax(100px, auto) 최소한 100px, 최대 자동으로 늘어나게됨
    3. fit-content()
        - 행/열의 크기를 그리드 아이템이 포함하는 내용(콘텐츠) 크기에 맞춤
        - '내용의 최대 크기'
