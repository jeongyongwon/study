# React

MVC => 유저 interaction이 많고 거대한 app에 적합하지 않음

## The reason use react

### Simplicity

간단하다. JSX를 활용해서 접근이 어렵지 않다.

### Developers love it

방대한 react 라이브러리가 존재

### Reusable elements

## React Lifecycle

### Render

- constructor
  set initial state.
  <br> this.state

- static getDerivedStateFromProps
  if props changes, change related state.
  <br> Why is it 'static'? because no access to 'this'

* render
  mandatory.

- componentDidMount

### Re-render

- static getDerivedStateFromProps

* shouldComponentUpdate
  why it exist? need decision.
  <br/> this component need to be updated or not
  <br/> returns true or false

If it's false, followed lifecycles will not be executed.

- render

- getSnapshotBeforeUpdate
  pre commit phase.

* componentDidUpdate

## 타 라이브러리와 다른점

## Redux

### Redux를 사용하는이유

react => 단방향 바인딩, redux => 양방향 바인딩
