# WDD 430 - Week 01: From JavaScript to React

BYU-Idaho WDD 430 Week 1 학습 활동 결과물입니다.
[React Foundations](https://nextjs.org/learn/react-foundations) 튜토리얼 Chapter 1~7을 완료하며 작성한 코드와 학습 내용을 정리했습니다.

## 📁 파일 구성

- `index.html` — React, ReactDOM, Babel을 CDN으로 불러와 작성한 첫 번째 React 앱.
  - `Header` 컴포넌트 (props 사용)
  - `HomePage` 컴포넌트 (배열 렌더링 + `useState` 훅으로 좋아요 카운터 구현)

## ▶️ 실행 방법

별도 빌드 도구 없이 브라우저에서 바로 실행할 수 있습니다.

1. 저장소를 클론합니다.
2. `index.html`을 브라우저에서 엽니다 (VS Code의 Live Server 확장 추천).
3. "Like" 버튼을 클릭하면 카운터가 증가합니다.

## ✅ Check Your Understanding

### 1. DOM이란 무엇인가?

DOM(Document Object Model)은 브라우저가 HTML 문서를 읽어들여 만드는 **트리 구조의 객체 표현**입니다. HTML의 각 요소(`<div>`, `<p>`, `<h1>` 등)는 트리의 노드(node)가 되고, JavaScript는 이 트리에 접근하여 요소를 추가/삭제/수정할 수 있습니다. 즉, DOM은 HTML과 JavaScript 사이의 다리 역할을 합니다.

### 2. 명령형(Imperative) vs 선언형(Declarative) 프로그래밍의 차이

- **명령형**: "어떻게(how)" 할지를 단계별로 지시합니다. 피자 만드는 과정을 직접 알려주는 것과 같습니다 — "반죽을 펴고, 소스를 바르고, 치즈를 올리고, 220°C에서 15분 굽는다."
- **선언형**: "무엇(what)"을 원하는지만 선언합니다. 피자를 주문하는 것과 같습니다 — "페퍼로니 피자 주세요." 어떻게 만들지는 가게가 알아서 처리합니다.

순수 JavaScript로 DOM을 직접 조작하는 방식은 명령형이고, **React는 선언형**입니다. 개발자가 "UI가 어떤 상태여야 하는가"만 기술하면, React가 실제 DOM 업데이트를 알아서 수행합니다.

### 3. JSX란 무엇인가?

JSX(JavaScript XML)는 **JavaScript의 구문 확장(syntax extension)** 으로, JS 파일 안에 HTML과 비슷한 마크업을 직접 작성할 수 있게 해줍니다.

```jsx
const element = <h1>Hello, world!</h1>
```

브라우저는 JSX를 직접 이해하지 못하기 때문에, Babel 같은 컴파일러를 통해 일반 JavaScript로 변환되어야 실행할 수 있습니다.

### 4. Babel 인터프리터란 무엇인가?

**Babel**은 JavaScript 컴파일러(transpiler)입니다. React에서는 두 가지 주요 역할을 합니다.

1. **JSX → 일반 JavaScript 변환**: 예를 들어 `<h1>Hello</h1>`를 `React.createElement('h1', null, 'Hello')`로 변환합니다.
2. **최신 JS → 구형 브라우저 호환 JS 변환**: 최신 ES 문법을 구형 브라우저도 이해할 수 있는 코드로 바꿔줍니다.

이번 프로젝트에서는 `<script src="https://unpkg.com/@babel/standalone/babel.min.js">`로 불러와 브라우저 안에서 직접 변환을 수행했습니다.

### 5. props와 state의 차이

| 항목 | Props | State |
|------|-------|-------|
| 출처 | **부모** 컴포넌트로부터 전달받음 | 컴포넌트 **내부**에서 생성 및 관리 |
| 수정 가능 여부 | 읽기 전용 (immutable) | `useState`의 setter로 업데이트 가능 |
| 비유 | 함수의 매개변수(parameter) | 컴포넌트의 기억(memory) |
| 예시 | `<Header title="Hello" />`의 `title` | `const [likes, setLikes] = useState(0)`의 `likes` |

쉽게 말해, **props는 밖에서 받는 값**이고 **state는 내가 가지고 있는 값**입니다. 두 값 모두 변경되면 컴포넌트가 리렌더링됩니다.

## 🔗 참고 자료

- [Essential JavaScript for React](https://nextjs.org/learn/react-foundations/getting-started-with-react#essential-javascript-for-react)
- [React Foundations Course (Next.js)](https://nextjs.org/learn/react-foundations)
