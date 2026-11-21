# OSS Week 12 — React Hooks Playground (Student Starter)

## Project Information: 프로젝트 소개 및 Starter Project 정보

## Installation: 설치·실행 방법 및 실행 화면

## Source Code Exploration: 주요 파일 구조, useEffect 및 useRef 분석, 주요 코드 2개 설명

### Project Structure: App.jsx와 주요 Lab 컴포넌트의 역할
App.jsx는 Lab 컴포넌트들을 한 화면에서 보여주기 위한 틀이고, Lab 컴포넌트들은 실제 화면에서 보여질 주요 동작이 정의된 컴포넌트 들이다. 페이지 이동 없이 한 페이지 내에서 컴포넌트를 마운트/언마운트 해가며 컴포넌트를 보여준다.

### useEffect: Effect, Dependency Array 및 Cleanup의 동작 원리
- **Effect**: `useEffect(fn, deps)`에 전달한 함수는 렌더링 중이 아니라, 렌더링 결과가 화면에 반영된 이후에 실행된다. 타이머 등록, 네트워크 요청, 이벤트 구독처럼 렌더링과 무관한 요청을 이곳에서 처리한다.
- **Dependency Array**: Effect를 언제 다시 실행할지 결정한다.
  - `[]` : 마운트될 때 한 번만 실행된다.
  - `[a, b]` : 마운트 시 실행되고, 이후 `a`나 `b`의 값이 바뀐 렌더링 뒤에만 다시 실행된다.
  - 생략 : 매 렌더링마다 실행된다.
- **Cleanup**: Effect 함수가 반환하는 함수이다. 컴포넌트가 언마운트될 때, 그리고 의존성이 바뀌어 Effect가 다시 실행되기 직전에 호출되어 이전 Effect가 만든 것들을 정리한다. 정리하지 않으면 Lab 이전 Effect의 정보들이 남아 현재의 Effect에 영향을 미친다.

### useRef: .current 속성과 useState의 차이
- `useRef(initialValue)`는 `{ current: initialValue }` 형태의 객체를 반환하며, 이 객체는 컴포넌트가 다시 렌더링되어도 같은 객체가 유지된다.
- 값은 `.current` 속성에 저장하고 직접 읽고 쓴다. JSX에 `ref={inputRef}`로 연결하면 React가 해당 DOM 요소를 `inputRef.current`에 넣어 주므로 `inputRef.current.focus()`처럼 DOM을 직접 조작할 수 있다.

- `useState`는 `setState`로 값을 바꾸면 리렌더링이 일어나고 새 값은 다음 렌더링부터 반영된다. 반면 `useRef`는 `.current`를 바꿔도 리렌더링이 일어나지 않고 값이 즉시 반영된다.

### Code Analysis: useEffect와 useRef 관련 주요 코드 각 1개(5~15줄)를 선택하여 동작 원리 설명

## Lab Implementation: 4개 Lab 구현 내용 및 실행 결과

## Lab Comparison: STEP 3의 비교 분석 질문 4개에 대한 답변

## Customizing: 수정 내용 및 파일명

## Deployment: 실제 접근 가능한 Vercel URL

## Weekly Review:
- 새롭게 배운 내용 3가지
- 어려웠던 점과 해결 방법
- AI 활용 내용 및 느낀 점