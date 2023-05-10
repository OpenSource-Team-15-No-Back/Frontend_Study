# Javascript 

### Javascript For Beginers

> codepen 사용 - 웹브라우저에서 에디터처럼 바로 사용가능, 작업코드 공유 편리 <br>
codepen - <https://codepen.io>

* ###  #1 - 변수 
 변수 - 어떤 정보에 이름을 붙여서 저장 <br>
 ```javascript
 name = "Mike";
 age = 30;
 ```
\* 여기에서 ';'은 생략해도 괜찮지만 항상 적어두는 것이 좋음 <br>
자바스크립트에서 `문자열`은 항상 `' '`를 적어야한다 (`" "`도 상관없음) <br>
 
변수명으로 사용할 수 없는 단어 => 예약어 <br>

`alert() - 경고창을 띄우는 함수` <br>
`console.log() - log를 찍는 함수`<br>

변수이름이 같을 때, 마지막으로 선언된 변수로 내용이 덮어 씌워지는 경우가 있다 <br>
=> 이를 방지하고자 `let`과 `const`키워드를 사용 <br>

**let** <br>
최초로 선언하는 모든 변수에 let을 선언하면 이미 사용시에 ERROR를 통해 알 수 있다 <br>
```javascript
let name = "Mike";

// 1000 lines...

let name = "google";
``` 
위의 코드는 에러가 발생한다 <br>
<br>
let을 한 번 선언 후 다른 값으로 바꾸기 위해서는 의도적으로 let을 생략하고 변수를 적는다 <br>

```javascript
let grade = "F";

// 1000 lines...

grade = "A+";
```

**const** <br>
절대로 바뀌지 않는 `상수`를 입력할 때 사용 (수정하려고 하면 에러발생)<br>
<br>
보통 파이나 최댓값, 생일 등 바뀌지 않는 값을 입력할 때 사용 <br>
\*대문자로 선언하는 것이 좋음 (다른 개발자들에게 상수라는 것을 알리기 위함)
``` javascript
const PI = 3.14;
const SPEED_LIMIT = 50;
const BIRTH_DAY = '2020-01-01';
```

### 정리 <br>
자바스크립트에서 변수를 선언할때는, <br>
변하지 않는 값은 `const`, 변할 수 있는 값은 `let`으로 선언하세요 <br>
<br>
++ <br>
변수 조건 <br>
1. 변수는 문자와 숫자, $와 _만 사용
2. 첫글자는 숫자가 될 수 없다
3. 예약어는 사용할 수 없다
4. 가급적 상수는 대문자로 알려주기
5. 변수명은 읽기 쉽고 이해할 수 있게 선언 <br>

* ###  #2 - 자료형 <br>
1. 문자형 String <br>
```javascript
const name1 = "Mke"
const name2 = 'Mike'
const name3 = `Mike`
``` 
위와 같이 ' '," ",\` `모두 가능 <br>

```javascript
const message = "I'm a boy.";
const message2 = 'I\'m a boy.';
```
문자형 내에 작은따옴표를 써야하는 경우 큰 따옴표를 쓰거나 작은따옴표 앞 \를 사용

```javascript
const name = "Mike";
const message 3 = `My name is ${name}`;
console.log(message3)
```
위 코드를 실행하면 콘솔 창에 "My name is Mike"가 출력된다 (``백틱을 사용함 주의)
```javascript
const message4 = `나는 ${30+1}살 입니다.`;
console.log(message4)
```
위 코드처럼 ${}사이에 바로 표현식을 넣어서 사용할 수도 있다 <br>

```javascript
const name = "Mike";
const a = "나는 ";
const b = " 입니다.";

console.log(a + name + b); //"나는 Mike 입니다."

const age = 30;
console.log(a + age + "살" + b); //"나는 30살 입니다."
```

위와 같이 문자형과 문자형을 더하면 하나의 문자열로 합쳐준다. <br>
숫자형과 문자형을 섞어서 더할 수 있지만 이 때 `문자형`으로 변경된다는 점을 주의

2. 숫자형 Number
```javascript
const age = 30; 
const PI = 3.14 //소수점 표현 가능

console.log(1 + 2); // 더하기
console.log(10 - 3); // 빼기
console.log(3 * 2); // * 곱하기
console.log(6 / 3); // / 나누기
console.log(6 % 4); // % 나머지
```

만약 숫자를 0으로 나눌 경우 어떻게 될까
```javascript
const x = 1/0;
console.log(x)
```
위의 출력결과는 `Infinity`로 나온다 <br>

그렇다면 문자열을 숫자로 나누면 어떻게 될까
``` javascript
const name = "Mike";
const y = name/2;

console.log(y)
```
위의 출력결과는 `NaN`으로 나온다 <br>
NaN = Not a number

3. Boolean <br>
```javascript
const a = true; // 참
const b = false; // 거짓
```

boolean의 예시
```javascript
const name = "Mike";
const age = 30;

console.log(name == 'Mike') //true
console.log(age > 40) //false
```

4. null 과 undefined <br>
**null** - 존재하지 않는 값 <br>
**undefined** - 값이 할당 되지 않았음<br>

```javascript
let age;
console.log(age) //undefined 출력

let user = null; //유저는 존재하지 않음
```

5. typeof 연산자 <br>
변수의 자료형을 알아낼 수 있음
```javascript
const name = "Mike";

console.log(typeof 3); //"number"
console.log(typeof name); //"string"
console.log(typeof true); //"boolean"
console.log(typeof "xxx"); //"string"
console.log(typeof null); //"object"
console.log(typeof undefined); //"undefined"
```
typeof 연산자는 다른 개발자가 작성한 변수의 type을 알아야 하거나, api 통신등을 통해 받아온 데이터를 type에 따라 다른 방식으로 처리해야 할 때 많이 사용한다

+ `object`는 객체형을 의미한다 <br>
null은 객체가 아니다 <br>

* ###  #3 - alert, prompt, confirm  <br>
**alert** - 메시지를 띄워 알려줌 <br>
**prompt** - 입력 받음 //input 느낌 <br>
**confirm** - 확인 받음 <br>

```javascript
const name = prompt("이름을 입력하세요."); //입력하는 창이 뜸
alert("환영합니다, " + name + "님"); //문자열 형식으로 alert 출력
alert(`안녕하세요, ${name}님. 환영합니다.`);
```
\*만약 prompt를 실행하고 아무 값을 입력하지 않을시 console.log로 출력을 하게 되면 `null`이 출력된다

```javascript
const name = prompt("예약일을 입력해주세요.", "2020-10-"); //prompt는 두 개의 인수를 받을 수 있음 이 때 두번째 값은 입력받을 default값이 됨 default값은 뭔가를 안내하거나 힌트를 줄 때 유용함
```
<br>
confirm()은 뭔가를 확인 받을 때 사용 <br>

```javascript
const isAdult = confirm("당신은 성인입니까?");

console.log(isAdult) //확인을 누를 시 console창에는 true가 출력, 취소를 누를 시 console 창에는 false가 출력
```
위 코드를 실행 시 alert와 달리 `확인`과 `취소`버튼이 함께 있는 메시지를 띄움 <br>
<br>
정리
1. alert는 실행 시 메시지를 보여주고 확인 버튼을 누르면 닫힘 <br>
2. prompt는 사용자에게 메시지를 보여주고 어떤 값을 입력받을 수 있는 필드를 제공 -> 취소를 누르면 null 반환 / 두 번째 인수를 넣으면 default값을 제공 <br>
3. confirm은 사용자에게 확인을 받기 위한 용도로 사용됨 확인 버튼은 true를, 취소 버튼은 false를 반환함 <br>
<br>
+ 단점
1. 스크립트 일시 정지 (창을 닫기 전에는 이후 동작에 제한을 받음)
2. 스타일링 x (위치와 모양을 정할 수 없음) <br>

* ###  #4 - 형변환 <br>
**String()** - `문자형`으로 변환
**Number()** - `숫자형`으로 변환
**Boolean()** - `불린형`으로 변

### Javascript For Intermediate

# React JS
