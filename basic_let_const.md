## const

- 한 번 지정하고 나면 변경이 불가능한 상수를 선언할 때 사용하는 키워드
- 한 번 선언한 후 변할 일이 없는 값에 사용

<br>

## let

- 동적인 값을 담을 수 있는 변수를 선언할 때 사용하는 키워드
- 한 번 선언한 후 값이 유동적으로 변할 수 있을 때 사용
  - 예: for 문

<br>

## var

- var 키워드는 scope가 함수 단위이다.
- let과 const의 scope는 함수 단위가 아닌, 블록 단위이다.

```js
function test() {
  var ab = 'ab';
  let cd = 'cd';
  const ef = 'ef';
  
  console.log(ab);	// ab
  console.log(cd);	// cd
  console.log(ef);	// ef
}

console.log(ab);	// Uncaught ReferenceError: ab is not defined
console.log(cd);	// Uncaught ReferenceError: cd is not defined
console.log(ef);	// Uncaught ReferenceError: ef is not defined
```

```js
if (true) {
  var ab = 'ab';
  let cd = 'cd';
  const ef = 'ef';
}

console.log(ab);	// ab
console.log(cd);	// Uncaught ReferenceError: cd is not defined
console.log(ef);	// Uncaught ReferenceError: ef is not defined
```

<br>

- ES6 문법에서 var를 사용할 일은 없다.

------

<br>

## Summary

- 기본적으로 const를 사용하고, 해당 값을 변경해야 할 때 let을 사용한다.
- let은 변수의 값을 재할당 할 수 있지만, const는 재할당 할 수 없다.

------

<br>