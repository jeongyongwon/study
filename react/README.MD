# React

## The reason use react

### Simplicity

간단하다. JSX를 활용해서 접근이 어렵지 않다.
<br/> Angular comes as huge package.

### Developers love it

방대한 react 라이브러리가 존재

### Reusable elements

## Why do we use arrow functions in react?

class Propery vs class Method

```js
class App extends Components {
  state = {
    loggedIn: false,
  };
  loginHandle = () => {
    this.setState((prevState) => ({
      loggedIn: !prevState.loggedIn,
    }));
  };
  render () {
      return (<div>...<div>)
  }
}
```

In above code, <code>loginHandle</code> is actually not a method, it's a property.

## React Lifecycle

### Render

- <strong>1. constructor</strong>
  <br/>set initial state.
  <br/>this.state

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

### componentWillUnmount

It's not in render or re-render.
<br/>Makes side effects when component did unmount.

### How to prevent components from re-rendering?

Can prevent in 3 ways.

- <strong>shouldComponentUpdate()</strong>
- <strong>React.PureComponent</strong>
- <strong>React.memo(In functional component)</strong>
  <br/>If input is same, not calculate and return same result.

## Explain Error Boundaries?

- <strong>state getDerivedStateFromError</strong>
- <strong>componentDidCatch</strong>

## Best Lifecycle Method for making API calls?

In componentDidMount. => It says DOM is ready.

## React Patterns

- <strong>context-api pattern</strong>
  <br/>Provider VS Consumer
- <strong>render props</strong>
- <strong>presentation component pattern</strong>
  <br/>A component that's primary job is to presentation.
  <br/>They're written as statless functional components.

## What is css-in-js pattern?

## Why can't you update state directly without setState()?

SetState always trigger re-rendering of the component.
<br/>to change View!

## How many ways you can conditionally render in react?

```js
if (isLiar) {
  return <PantsOnFire />;
} else {
  return <YourAreNice />;
}
```

```js
{
  isLiar ? <PantsOnFire /> : <YouAreNice />;
}
```

## What is Fragment and why we use it?

## How to do code-splitting in react?

LazyLoading. React.Lazy

## Explain Virtual DOM

Do you know internals of how react works?
<br/>Manipulating the DOM is expensive.
<br/>React has DOM tree of it's own. It's virtual DOM.

# React-Hooks

Hooks are functions that lets you "Hook into" React state and lifecycle features from function components.

## Why react-hooks?

- <strong>Different way of doing the same things.</strong>

- <strong>No more complex lifecycle methods.</strong>

- <strong>Simpler code. No more mapStateToProps, mapDispatchToProps with redux.</strong>

- <strong>Hooking into components is much eaiser.</strong>

## Rules of react hooks?

- <strong>Only call Hooks at the top level.</strong>
- <strong>Dont call hooks inside loop, conditions, or nested functions.</strong>
- <strong>Call hooks from React Components or Custom Hooks.</strong>

## Map lifecycle class methods to lifecycle hooks

# Redux

## What are some alternatives to redux?

- <strong>mobX</strong>
- <strong>apollo client + graphQL</strong>
- <strong>RxJS</strong>

## Diffrence between redux-saga and redux-thunk

### thunk

```js
let a = 1;
AC = () => let a = 1
```

### saga

```js
function* generator() {
  yield doFirst();
  yield doSecond();
}
```

In saga, you can actually cancel action.
