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

- <strong>1. constructor</strong>
  <br/>set initial state.
  <br/> this.state

- <strong>2. static getDerivedStateFromProps</strong>
  <br/>if props changes, change related state.
  <br/> Why is it 'static'? because no access to 'this'

* <strong>3. render</strong>
  <br/>mandatory.

- <strong>4. componentDidMount</strong>

### Re-render

- <strong>1. static getDerivedStateFromProps</strong>

* <strong>2. shouldComponentUpdate</strong>
  <br/> why it exist? => need for decision making
  <br/> decide this component need to be updated or not.
  <br/> returns true or false.
  <br/><code>If it's false, followed lifecycles will not be executed.</code>

- <strong>3. render</strong>

- <strong>4. getSnapshotBeforeUpdate</strong>
  <br/>pre commit phase.

* <strong>5. componentDidUpdate</strong>

## 타 라이브러리와 다른점

## Redux

### Redux를 사용하는이유

react => 단방향 바인딩, redux => 양방향 바인딩
