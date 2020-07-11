# git 명령어 정리

### git

- **git init**: 저장소 생성
- **git add (filename)**: 저장소에 파일 추가
  - git \* -> 두 가지 이상의 변동 내용을 한번에 적용
- **git commit**: 저장소에 변경 내용을 반영
  - git add는 추가만 한 것임.(초록색 글씨로 표시) -> git commit으로 추가한 상태를 확정할 필요가 있음
- **git status**: 저장소의 상태 확인

- **git log**: 이제까지의 내역을 볼 수 있음
- **gitk**: GUI로 한 눈에 쉽게 직관적으로 히스토리를 볼 수 있음

#### branch 관리

- 혼자서는 master branch에서만 작업해도 괜찮지만, 동시에 여러사람들이 파일을 만들고 업데이트를 하는 상황이면 master에서만 작업하면 불편 -> 새로운 branch 만들어 작업하고 관리자는 merge하는 작업에 신경써야함

- **git branch (branch명)**: new branch 생성
- **git branch**: branch들을 확인
- 처음은 master -> 내가 만든 branch로 switch하기 위해서는 **git checkout (branch명)**
- **git branch -d (branch명)**: 해당 branch 삭제

#### git과 github(원격저장소)

- **git remote**: 원격 저장소인 github을 관리할 수 있는 명령어
  - git remote add origin http://github.com/[이름]/gitExample: github 주소를 등록
  - origin 이라는 이름을 사용하면 입력했던 저장소에 접속 가능
  - git remote remove origin: origin 원격저장소 삭제
- **git clone**: github의 내용을 로컬저장소로 복제해서 가져옴
  - git clone (github에서 복사해온 url)
- **git push**: 로컬저장소에서 수정된 것을 다시 github으로 보냄
  - git commit을 하게 되면 아직 로컬에만 반영이 되고 github에는 반영이 안 되었으므로 push를 해줘야 함)
- **git pull**: github에서 필요한 파일을 다운 + 병합
- **git fetch**: github에서 필요한 파일을 다운만 함 (_병합은 따로_),
  - 원래 내용과 바뀐 내용의 차이를 알 수 있고, commit이 얼마나 됐는지 알 수 있으며, 이러한 세부적인 내용들을 확인 후에 git merge origin/master하면(_병합_) git pull 상태와 같아짐
  - 신중할 때 사용함
