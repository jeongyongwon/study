# Javascript

## Hoisting

### 함수 선언식과 함수표현식

```js
//fucntion declarartion
function test() {}

//function expression
const test = () => {};
```

함수 선언식은 선언 이전에 <code>Hoisting</code> 된다.
<br>
단, {} 안의 값 할당은 런타임과정에서 이루어지기에 <code>Hoisting</code> 되지 않는다.

## Closure

Closure = 함수 + 함수를 둘러싼 환경 (Lexical Enviroment)

### Scope

#### Scope Level

Function level Scope VS Block Level Scope

##### Function Level Scope

var 키워드로 선언된 함수 & 함수 선언식으로 만들어진 함수는 <code>Function Level Scope</code>를 갖는다.

```js
function foo() {
  if (true) {
    var color = "blue";
  }
  console.log(color); // blue
}
foo();
```

만약 <code>Block Level Scope</code>였다면 <code>var color</code>는 if문이 끝날때 파괴되었을 것이다.

##### Block Level Scope

<code>let, const</code>는 Block Level Scope 변수를 만든다.

```js
function foo() {
  if (true) {
    let color = "blue";
    console.log(color); // blue
  }
  console.log(color); // ReferenceError: color is not defined
}
foo();
```

<code>let color</code>를 if 블록 밖에서 참조하면 에러가 발생한다.

#### Lexical Scope (=Static Scope)

the strange word "Lexical"
<br/>“Having to do with the words you(the programmer) typed when you defined the function.” Another useful tidbit is, “A function doesn’t care where it was invoked, only where it was defined.”
<br> 어디서 정의되었을때를 제외하고 어디서 불러오든지 상관 X

```js
const num = 6;

function one() {
  console.log("inside one and num is ", num);
}

function two() {
  const num = 3;

  one();
}

two(); // "inside one and num is 6"
```

```js
function one() {
  console.log("inside one and num is ", num);
}

function two() {
  const num = 3;

  one();
}

two(); // Error: num is not defined
// one이 선언될 당시에는 num에 대한 정보가 전혀없음
```

```js
function two() {
  const num = 3;
  function one() {
    console.log("inside one and num is ", num);
  }
  one();
}

two(); // "inside one and num is 3"
// num이 정의되었을때 closure를 통해 two안에있는
// num에 접근할수 있기에 3을 출력할 수 있다
```

## Callback vs Promise vs Async Await

```js
function printString(string) {
  setTimeout(() => {
    console.log(string);
  }, Math.floor(Math.random() * 100) + 1);
}
```

### Callback

```js
function printAll() {
  printString("A", () => {
    printString("B", () => {
      printString("C", () => {});
    });
  });
}
printAll();
```

nesting.. nesting... nesting..
<br>The problem with callbacks is it creates something called “Callback Hell.” Basically, you start nesting functions within functions within functions, and it starts to get really hard to read the code.

### Promise

```js
function printAll() {
  printString("A")
    .then(() => printString("B"))
    .then(() => printString("C"));
}
printAll();
```

### Async Await

```js
async function printAll() {
  await printString("A");
  await printString("B");
  await printString("C");
}
printAll();
```

## Call by reference vs Call by value

### Call by reference

### Call by value

## Modern JS

### ES6

- Arrow function expression
- Classes
- Destructuring
- Rest, Spread Operator
- Symbols
- Promise
- let, const
- Template String `${expression}`

### ES7

- Array.prototype.includes()

### ES8

- Async Await
