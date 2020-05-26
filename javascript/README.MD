# Javascript

## Hoisting

### 함수 선언식과 함수표현식

```
//fucntion declarartion
function test() {}

//function expression
const test = () => {}
```

함수 선언식은 선언 이전에 <code>Hoisting</code> 된다.
<br>
단, {} 안의 값 할당은 런타임과정에서 이루어지기에 <code>Hoisting</code> 되지 않는다.

## Closure

Closure = 함수 + 함수를 둘러싼 환경 (Lexical Enviroment)

### Scope

#### Scope Level

##### Function Level Scope

var 키워드로 선언된 함수 & 함수 선언식으로 만들어진 함수는 <code>Function Level Scope</code>를 갖는다.

```
function foo() {
    if (true) {
        var color = 'blue';
    }
    console.log(color); // blue
}
foo();
```

만약 <code>Block Level Scope</code>였다면 <code>var color</code>는 if문이 끝날때 파괴되었을 것이다.

##### Block Level Scope

<code>let, const</code>는 Block Level Scope 변수를 만든다.

```
function foo() {
    if(true) {
        let color = 'blue';
        console.log(color); // blue
    }
    console.log(color); // ReferenceError: color is not defined
}
foo();
```

<code>let color</code>를 if 블록 밖에서 참조하면 에러가 발생한다.

#### Lexical Scope
