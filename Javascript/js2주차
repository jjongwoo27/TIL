# 알고있으면 유용한 자바스크립트 문법

# 삼항 연산자

특정 조건에 따라 text 값이 달라야 하는 상황

```jsx
조건 ? true일때 : false일때
```

```jsx
const array = [];
let text = array.length === 0 // 조건
  ? '배열이 비어있습니다' // true, array.length == 0
  : '배열이 비어있지 않습니다.'; // false, array.length != 0

console.log(text);
```

# Truthy Falsy

Falsy한 값들 (다음 값들은 모두 True)

```jsx
console.log(!undefined);
console.log(!null);
console.log(!0);
console.log(!'');
console.log(!NaN);
```

Truthy한 값들 (다음 값들은 모두 False)

```jsx
console.log(!3);
console.log(!'hello');
console.log(!['array?']);
console.log(![]);
console.log(!{ value: 1 });
```

Truthy 한 값과 Falsy 한 값은 if 문에서도 사용 가능

```jsx
const value = { a: 1 };
if (value) {
  console.log('value 가 Truthy 하네요.'); // value가 Truthy한 값이므로 출력
}
```

```jsx
const value = { a: 1 };
const truthy = value ? true : false;
const truthy = !!value;
// !value 는 false 가 되고, 여기에 !false 는 true 가 되어서, 결과는 true
```

# 단축 평가 논리 계산법

논리 연산자

```jsx
true && true // true
true && false // false
true || false // true
false || true // true
```

논리 연산자를 사용 할 때에는 무조건 true 혹은 false를 사용해야 하는 것은 아니다. 문자열이나 숫자, 객체를 사용 할 수도 있고, 해당 값이 Truthy 하냐 Falsy 하냐에 따라 결과가 달라진다.

```jsx
console.log(true && 'hello'); // hello
console.log(false && 'hello'); // false
console.log('hello' && 'bye'); // bye
console.log(null && 'hello'); // null
console.log(undefined && 'hello'); // undefined
console.log('' && 'hello'); // ''
console.log(0 && 'hello'); // 0
console.log(1 && 'hello'); // hello
console.log(1 && 1); // 1
```

```jsx
const dog = {
  name: '멍멍이'
};

function getName(animal) {
  return animal && animal.name;
}

const name = getName(dog);
console.log(name); // 멍멍이
```

|| 연산자는 만약 어떤 값이 Falsy 하다면 대체로 사용 할 값을 지정해줄 때 매우 유용하게 사용 가능

→ A || B 는 만약 A 가 Truthy 하다면 결과는 A, A가 Falsy 하다면 결과는 B

```jsx
const namelessDog = {
  name: ''
};

function getName(animal) {
  const name = animal && animal.name;
  return name || '이름이 없는 동물입니다.';
}

const name = getName(namelessDog);
console.log(name); // 이름이 없는 동물입니다.
```

# 함수의 기본 파라미터

만약에 r 값이 주어지지 않았을 때 기본 값을 1을 사용하도록 하려면?

```jsx
function calculateCircleArea(r = 1) {
  return Math.PI * r * r;
}

const area = calculateCircleArea();
console.log(area); // 3.141592653589793
```

```jsx
const calculateCircleArea = (r = 1) => Math.PI * r * r;

const area = calculateCircleArea();
console.log(area); // 3.141592653589793
```

# 조건문 더 스마트하게 쓰기

****특정 값이 여러 값중 하나인지 확인해야 할 때****

특정 값이 여러 값 중 하나인지 확인을 해야 하는 상황에서 비교해야 할 값이 많아질 수록 코드는 길어진다. 이럴 때는, 배열을 만들고 배열의 include 함수를 사용한다.

```jsx
function isAnimal(name) {
  const animals = ['고양이', '개', '거북이', '너구리'];
  return animals.includes(name);
}

console.log(isAnimal('개')); // true
console.log(isAnimal('노트북')); // false
```

```jsx
const isAnimal = name => ['고양이', '개', '거북이', '너구리'].includes(name);

console.log(isAnimal('개')); // true
console.log(isAnimal('노트북')); // false
```

****값에 따라 다른 결과물을 반환 해야 할 때****

switch case 문을 사용하여 구현할 수도 있지만 객체를 사용하여 좀 더 간단하게 표현 가능하다.

```jsx
function getSound(animal) {
  const sounds = {
    개: '멍멍!',
    고양이: '야옹~',
    참새: '짹짹',
    비둘기: '구구 구 구'
  };
  return sounds[animal] || '...?';
}

console.log(getSound('개')); // 멍멍!
console.log(getSound('비둘기')); // 구구 구 구
```

**값에 따라 실행해야 하는 코드 구문이 다를 때**

객체에 함수를 넣으면 된다.

```jsx
function makeSound(animal) {
  const tasks = {
    개() {
      console.log('멍멍');
    },
    고양이() {
      console.log('고양이');
    },
    비둘기() {
      console.log('구구 구 구');
    }
  };
  if (!tasks[animal]) {
    console.log('...?');
    return;
  }
  tasks[animal]();
}

getSound('개');
getSound('비둘기');
```

# 비구조화 할당

(복습) 함수에 파라미터에서도 비구조화 할당을 할 수 있다!

```jsx
const object = { a: 1, b: 2 };

function print({ a, b }) {
  console.log(a);
  console.log(b);
}

print(object);
```

****비구조화 할당시 기본값 설정****

```jsx
const object = { a: 1 };

function print({ a, b = 2 }) {
  console.log(a);
  console.log(b);
}

print(object);
// 1
// 2
```

```jsx
const object = { a: 1 };

const { a, b = 2 } = object;

console.log(a); // 1
console.log(b); // 2
```

****비구조화 할당시 이름 바꾸기****

“animal 객체 안에 있는 name 을 nickname 이라고 선언하겠다”

```jsx
const animal = {
  name: '멍멍이',
  type: '개'
};

const { name: nickname } = animal
console.log(nickname);
```

**배열에서 비구조화 할당하기**

배열 안에 있는 원소를 다른 이름으로 새로 선언해주고 싶을 때 사용하면 매우 유용하다.

객체 비구조화 할당과 마찬가지로, 기본값 지정이 가능하다.

```jsx
const array = [1];
const [one, two = 2] = array;

console.log(one);
console.log(two);
```

****깊은 값 비구조화 할당****

객체에서 name, languages, value 값들을 밖으로 꺼내주고 싶다면?

![Untitled](%E1%84%8B%E1%85%A1%E1%86%AF%E1%84%80%E1%85%A9%E1%84%8B%E1%85%B5%E1%86%BB%E1%84%8B%E1%85%B3%2098945/Untitled.png)

1) 비구조화 할당 문법 두번 사용하기

```jsx
const deepObject = {
  state: {
    information: {
      name: 'velopert',
      languages: ['korean', 'english', 'chinese']
    }
  },
  value: 5
};

const { name, languages } = deepObject.state.information;
const { value } = deepObject;

const extracted = {
  name,
  languages,
  value
};

console.log(extracted); // {name: "velopert", languages: Array[3], value: 5}
```

2) 한번에 모두 추출하는 방법

```jsx
const deepObject = {
  state: {
    information: {
      name: 'velopert',
      languages: ['korean', 'english', 'chinese']
    }
  },
  value: 5
};

const {
  state: {
    information: { name, languages }
  },
  value
} = deepObject;

const extracted = {
  name,
  languages,
  value
};

console.log(extracted);
```

p.s. object-shorthand : key 이름으로 선언된 값이 존재하다면, 바로 매칭시켜준다.

```jsx
const extracted = {
  name, // name: name
  languages, // language: languge
  value // value: value
}
```

# spread와 rest

**spread**

기존의 것을 건들이지 않고, 새로운 객체를 만들 때!

![Untitled](%E1%84%8B%E1%85%A1%E1%86%AF%E1%84%80%E1%85%A9%E1%84%8B%E1%85%B5%E1%86%BB%E1%84%8B%E1%85%B3%2098945/Untitled%201.png)

기존에 선언한 slime 을 건들이지 않고 새로운 객체를 만들어서 slime 이 가지고 있는 값을 그대로 사용

```jsx
const slime = {
  name: '슬라임'
};

const cuteSlime = {
  ...slime,
  attribute: 'cute'
};

const purpleCuteSlime = {
  ...cuteSlime,
  color: 'purple'
};

console.log(slime);
console.log(cuteSlime);
console.log(purpleCuteSlime);
```

spread는 배열에서도 사용 가능

![Untitled](%E1%84%8B%E1%85%A1%E1%86%AF%E1%84%80%E1%85%A9%E1%84%8B%E1%85%B5%E1%86%BB%E1%84%8B%E1%85%B3%2098945/Untitled%202.png)

```jsx
const animals = ['개', '고양이', '참새'];
const anotherAnimals = [...animals, '비둘기'];
console.log(animals);
console.log(anotherAnimals);
```

spread 연산자를 여러번 사용 할 수도 있다.

```jsx
const numbers = [1, 2, 3, 4, 5];

const spreadNumbers = [...numbers, 1000, ...numbers];
console.log(spreadNumbers); // [1, 2, 3, 4, 5, 1000, 1, 2, 3, 4, 5]
```

**rest**

rest 는 객체와 배열에서 사용 할 때는 비구조화 할당 문법과 함께 사용한다. 대신 추출한 값의 이름이 꼭 rest일 필요는 없다.

```jsx
const purpleCuteSlime = {
  name: '슬라임',
  attribute: 'cute',
  color: 'purple'
};

const { color, ...cuteSlime } = purpleCuteSlime;
console.log(color); // purple
console.log(cuteSlime); // {name: "슬라임", attribute: "cute"} (color를 제외한 나머지)
```

배열에서는 다음처럼 사용할 수도 있다.

```jsx
const numbers = [0, 1, 2, 3, 4, 5, 6];

const [one, ...rest] = numbers;
// (주의) const [..rest, last] = numbers; 이렇게는 불가능.

console.log(one);
console.log(rest);
```

함수의 파라미터가 몇개가 될 지 모르는 상황에서 rest 파라미터를 사용하면 매우 유용하다.

```jsx
function sum(...rest) {
  return rest.reduce((acc, current) => acc + current, 0);
}

const result = sum(1, 2, 3, 4, 5, 6);
console.log(result); // 21
```

# scope의 이해

Scope 란, 우리가 변수 혹은 함수를 선언하게 될 때 해당 변수 또는 함수가 유효한 범위를 의미한다.

1. **Global (전역) Scope**: 코드의 모든 범위에서 사용
2. **Function (함수) Scope**: 함수 안에서만 사용
3. **Block (블록) Scope**: if, for, switch 등 특정 블록 내부에서만 사용

```jsx
const value = 'hello!';

function myFunction() {
  console.log('myFunction: ');
  console.log(value);
}

function otherFunction() {
  console.log('otherFunction: ');
  const value = 'bye!';
  console.log(value);
}

myFunction();
otherFunction();

console.log('global scope: ');
console.log(value);
```

- 코드의 맨 윗줄에서 선언된 `value` 값은 Global Scope 로 선언된 값
- `otherFunction` 에서는 함수 내부에서 `value` 값을 `'bye!'` 로 새로 선언 → `value` 라는 값은 Function Scoped에서만 유효함

```jsx
const value = 'hello!';

function myFunction() {
  const value = 'bye!';
  if (true) {
    const value = 'world';
    console.log('block scope: ');
    console.log(value);
  }
  console.log('function scope: ');
  console.log(value);
}

myFunction();
console.log('global scope: ');
console.log(value); // hello!
```

- my function 안에서 `const` 로 선언한 값은 Block Scope 로 선언 
→ if문 같은 블록 내에서 새로운 변수/상수를 선언하게 된다면, 해당 블록 내부에서만 사용이 가능하며, 블록 밖의 범위에서 똑같은 이름을 가진 값이 있다고 해도 영향을 주지 않는다.

**Hoisting**

아직 선언되지 않은 함수를 "끌어올려서" 사용 할 수 있는 자바스크립트의 작동 방식

```jsx
myFunction();

function myFunction() {
  console.log('hello world!');
}
```

위 코드에서는 `myFunction` 함수를 선언하기 전에, `myFunction()` 을 호출했는데도 불구하고 코드는 정상적으로 작동한다. 

변수 또한 마찬가지다.

```jsx
console.log(number);
var number = 2;
```

(주의1) 반면, `const` 와 `let` 은 hoisting 이 발생하지 않고, 에러가 발생한다.

(주의2) Hoisting은 방지하는 것이 좋다!

<aside>
💡 Hoisting 을 방지하기 위해서, 함수의 경우 꼭 선언 후에 호출을 하도록 주의를 하시고, `var` 대신 `const`, `let` 을 위주로 사용하세요. 추가적으로, 나중에 자바스크립트 개발을 본격적으로 하게 될 때에는 ESLint 라는것을 사용하여 Hoisting 이 발생하는 코드는 에디터상에서 쉽게 발견해낼 수 있습니다.

</aside>
