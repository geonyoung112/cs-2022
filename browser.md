<!-- Heading -->

# 브라우저와 작동원리

## 브라우저

브라우저의 주요 기능은 사용자가 참조하고 싶은 웹페이지를 서버에 요청하고, 서버의 응답을 받아 브라우저에 보여주는 것이다. 흔히 사용하는 크롬, 인터넷 익스플로러 등 인터넷 프로그램이다. 서버의 응답은 주소를 통해 요청하는데, 이 주소를 URI(Uniform Resource Identifier)라고 한다.

## 브라우저 렌더링 과정

- browser elements

- rendring engine working process
- html, css parsing process
- render process

## browser elements

- 사용자 인터페이스: 주소 표시줄, 이전/다음 버튼, 홈버튼, 새로고침/정지 버튼 등 요청한 페이지를 보여주는 창 외에 사용자가 컨트롤 할 수 있는 부분

- 브라우저 엔진: 사용자 인터페이스와 렌더링 엔진 사이에 동작을 제어한다.

- 렌더링 엔진: 요청한 URL를 브라우저 엔진에게 받아서 server에게 요청한다.
  server로 부터 URL에 해당하는 데이터(html, css, javascript)를 받아서 파싱한 후 렌더링한다.

> 파싱(parsing)은 구문 분석이라고 한다. 문장이 이루고 있는 구성 성분을 분해하고 분해된 성분의 위계 관계를 분석하여 구조를 결정하는 것이다. 즉 데이터를 분해 분석하여 원하는 형태로 조립하고 다시 빼내는 프로그램을 말한다.

- 통신: 렌더링 엔진으로부터 http 요청 등을 받아서 네트워크 처리 후 응답을 전달한다.

- 자바스크립트 해석기: javascript를 파싱한다.

- 자료 저장소: 쿠키 등의 자료를 컴퓨터 하드디스크에 저장한다.

> 쿠키란 하이퍼 텍스트의 기록서의 일종으로서 인터넷 사용자가 어떠한 웹사이트를 방문할 경우 그 사이트가 사용하고 있는 서버를 통해 인터넷 사용자의 컴퓨터에 설치되는 작은 기록 정보 파일을 일컫는다.

- UI 백엔드: render tree를 browser에 그리는 역할을 담당한다.

![image desciption](https://d2.naver.com/content/images/2015/06/helloworld-59361-1.png)

## browser rendering process

브라우저가 렌더링하는 과정을 간단하게 설명한다.

1. 사용자가 사용자 인터페이스, 주소표시줄에 URL을 입력하여 브라우저 엔진에 전달한다.

2. 브라우저 엔진은 자료 저장소에서 URL에 해당하는 자료를 찾고, 해당 자료를 쿠키로 저장했다면 그 자료를 렌더링 엔진에 전달한다.

3. 렌더링 엔진은 브라우저 엔진에서 가져온 자료를 분석한다.
   동시에 URL 데이터를 통신, 자바스크립트 해석기, UI 백엔드로 전파한다.

4. 또한 렌더링 엔진은 통심 레이어에 URL에 대한 추가 데이터(있다면) 요청하고 응답할 때까지 기다린다.

5. 응답받은 데이터에서 HTML, CSS는 렌더링 엔진이 파싱한다.

6. 응답받은 데이터에서 JavaScript는 JavaScript 해석기가 파싱한다.

7. JavaScript 해석기는 파싱한 결과를 렌더링 엔진에 전달하여 3번과 5번에서 파싱한 HTML의 결과인 DOM tree를 조작한다.

8. 조작이 완료된 DOM node는 render object로 변한다.

9. UI 백엔드는 render object를 브라우저 렌더링 화면에 띄워준다.

> 노드(node):
> HTML DOM은 노드(node)라고 불리는 계층적 단위에 정보를 저장하고 있다. HTML DOM은 이러한 노드들을 정의하고, 그들 사이의 관계를 설명해 주는 역할을 한다.

> ![image desciption](https://i.imgur.com/RL1IrMs.png)

> HTML 문서의 정보는 노드 트리(node tree)라고 불리는 계층적 구조에 저장된다. 이러한 노드 트리는 노드들의 집합이며, 노드 간의 관계를 보여준다.
> 노드 트리는 최상위 레벨인 루트 노드(root node)로부터 시작하여, 가장 낮은 레벨인 텍스트 노드까지 뻗어 내려간다.
> 자바스크립트에서는 HTML DOM을 이용하여 노드 트리에 포함된 모든 노드에 접근할 수 있다.

## rendering engine working procedd

---

렌더링 엔진은 URL을 통해 요청을 받아서 해당하는 데이터를 렌더링하는 역할을 담당한다.

### 대략적인 rendering engine 동작 과정

1. 앞서 말한 과정 중 DOM tree 구축을 위한 HTML, CSS, JavaScript parsing: HTML 문서를 파싱한 후, content tree 내부에서 tag(a, div)를 DOM node(Document Object Model)로 변환한다. 스타일 요소와 HTML 표시 규칙, JavaScript의 파싱 결과물은 render tree (render object)를 생성한다.

2. render tree 구축: HTML, CSS를 파싱해서 만들어진 render tree는 색상 또는 면적 등 시각적 속성을 갖는 사각형을 포함한다. 이를 정해진 순서대로 렌더링한다.

3. render tree 배치: render tree가 생성이 끝나면, 배치가 시작된다.
   각 node가 정확한 위치에 표시되기 위해 이동한다.

4. render tree 그리기: 각 node 배치를 완료하면 UI 백엔드에서 각 node를 가로지르며 paint 작업을 한다.

**여기서 1번과 2,3,4번은 병렬적으로 진행된다.
즉, 통신 레이어에서 data를 계속 받아오면서 (통신레이어) 받아온 HTML, CSS, JavaScript를 파싱하면서(1번) render tree에 node를 그린다. (2,3,4번)**

---

## 예시를 통해 구체적인 동작과정 알아보기

### Webkit의 동작과정

> 웹킷(WebKit)은 애플에서 오픈소스로 개발하고 있는 웹컨텐트(web content) 엔진 또는 웹렌더링(web rendering) 엔진이다.
> ex) 크롬

![image description](https://d2.naver.com/content/images/2015/06/helloworld-59361-3.png)

**1. HTML을 파싱하여 DOM tree를 생성한다.**

DOM으로 바꾼 HTML은 JavaScript가 조작할 수 있게 된다.
(HTML은 정보를 표시하는 역할을 하는데 이는 정보를 동적으로 움직이게 하는 프로그래밍 언어달리 HTML은 이를 하지못한다. 그래서 파싱을 하여 DOM tree를 생성해 JavaScript가 조작할 수 있게 만들어 사용자와 상호작용이 가능해지는 것 - 버튼을 누르거나 동작하는 것 등등 등등 )

![image description](https://davidhwang.netlify.app/static/3ac6ca31dbadb692e12d5ae14c73ec57/c7805/domtree.png)

브라우저는 tag의 parsing 과 실행을 동시에 진행한다.

1. 첫번째 tag 를 parsing 한다.
2. 첫번째 tag 를 실행한다.
3. 실행이 완료된 후 두번째 tag 를 파싱한다.

**2. CSS(style sheets)를 parsing 하여 스타일 규칙을 얻는다.**
css parsing 하여 CSSOM 생성한다.(스타일 규칙)

**3. DOM tree를 생성하는 동시에, 이미 생성된 DOM tree 와 스타일 규칙(CSSOM)을 Attachment 한다.**

- DOM tree를 구성하는 하나의 DOM node 는 attach 라는 method를 가진다. - 새로운 DOM node 가 추가되면 attach가 호출되어 render object를 생성한다.
- render object는 render tree의 구성요소로써, 자신과 자식 요소를 어떻게 배치하고 그려야할지 안다.
- node의 css box 를 표시할 정보를 가지고 있음
- 모든 DOM node가 전부 render object 로 생성되는 것은 아님 (ex head tag, display none tag 등)
- html 태그와 body 태그의 DOM node 또한 render object 로 구성되는데 이들은 render tree root로써 render view 라고 부른다.
- 나머지 DOM node 들은 render object 로 생성되어 이 render tree root에 추가된다.

**4. 구축한 render tree 를 배치(layout)한다.**

배치는 html 요소에 해당하는 최상위 render object 에서 시작한다. 화면에 왼쪽 위부터 render object에 해당하는 DOM node를 그려나간다.

**5. 배치가 끝난 render tree 를 그린다.**

render tree 탐색 후 해당하는 render object 의 paint method 를 호출한다.
