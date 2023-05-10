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
+ 단점 <br>
1. 스크립트 일시 정지 (창을 닫기 전에는 이후 동작에 제한을 받음) <br>
2. 스타일링 x (위치와 모양을 정할 수 없음) <br>

* ###  #4 - 형변환 <br>
**String()** - `문자형`으로 변환 <br>
**Number()** - `숫자형`으로 변환 <br>
**Boolean()** - `불린형`으로 변환 <br>

```javascript
const mathScore = prompt("수학 몇점?"); //입력값을 90
const engScore = prompt("영어 몇점?"); //입력값을 80
const result = (mathScore + engScore) / 2;

console.log(result)
```
위의 코드의 출력 값은 4540이 나온다 <br>
왜 그럴까? -> 문자형을 받아서이다!! ("90" + "80" = "9080" / "9080" / 2 = 4540) <br>
prompt 입력 -> `문자형` <br> <br>
그런데 "9080" / 2 가 제대로 작동한 이유는 무엇일까? <br> 
-> 숫자형이 아니더라도 / 같은 표현식은 숫자형으로 자동 변환 되어 계산됨 <br>
EX) "6" / "2" = 3 <br>
바로 이러한 과정을 `자동 형변환`이라고 한다 <br>
자동 형변환은 원인을 찾기 힘든 에러를 발생시킬 수 있음 <br>
-> 항상 의도를 가지고 원하는 타입으로 변환하는 것이 좋다! => `명시적 형변환` <br>
<br>
1. String() <br>
괄호 안의 타입을 문자형으로 바꾸어 줌 <br>
```javascript
console.log(
String(3), 
String(true),
String(false),
String(null),
String(undifined)
)
// "3" "true" "false" "null" "undefined"
```
2. Number() <br>
괄호 안의 타입을 숫자형으로 바꾸어 줌 (보통 사용자로부터 입력받은 값이 문자형인 경우 자주 사용) <br>
```javascript
console.log(
Number("1234"), // 1234
Number("1234akjdls) //NaN
)
```
문자열안에 숫자가 아닌 글자를 넣을 경우 NaN이 출력됨으로 주의 <br>

```javascript
console.log(
Number(true), // 1
Number(false) // 0
)
```
Number 형변환에 true와 false는 각각 1과 0으로 출력된다 <br>

3. Boolean() <br>
`false`의 경우를 기억하기 <br>
+ 숫자0
+ 빈문자열''
+ null
+ undefined
+ NaN <br>
위의 값의 예외는 모두 `true`반환 <br><br>

### 정리 <br>
String() -> `문자형`으로 변환 <br>
Number() -> `숫자형`으로 변환 <br>
\*Number("문자")//NaN
Boolean() -> `불린형`으로 변환 <br>
\*0, '', null, undefined, NaN -> false <br>
<br>

### 주의사항 (외우기) <br>
+ Number(null) //0
+ Number(undefined) //NaN 
+ Boolean(0) //false
+ Boolean('0') //true
+ Boolean('') //false
+ Boolean(' ') //true <br><br>

* ###  #5 - 기본 연산자 <br>
    * \+ // 더하기
    * \- // 빼기
    * \* // 곱하기   
    * / // 나누기
    * % // 나머지 
    * ** // 거듭제곱 <br>
<br>
나머지를 어디에 쓸까(%) <br>
홀수 : X % 2 = 1 <br>
짝수 : Y % 2 = 0 <br>
<br>
어떤 값이 들어와도 5를 넘기면 안돼<br>
-> X % 5 = 0 ~ 4 사이의 값만 반환 <br>

연산자의 우선순위 <br>
 `* / > + -` <br>
<br>
연산자 줄여서 쓰기<br>
```javascript
let num = 10;
num += 5; //num = num + 5;
num *= 5; //num = num * 5;
num -= 5; //num = num - 5;
num %= 5; //num = num % 5;
```
<br>
증가 연산자, 감소 연산자<br>

```javascript
let num = 10;
num ++ //증가 연산자
num -- //감소 연산자

console.log(num);
```
`증가 연산자 ++`<br>
`감소 연산자 --`
```javascript
let num = 10;
//let result = num++; 증가시키기 전의 값을 result에 넣는다
let result = ++num; //1증가 시킨 값을 result에 넣는다

console.log(result);
```
위의 코드에서 ++가 num앞에 위치한 결과와 뒤에 위치한 결과는 서로 다르다는 것을 유의하자

* ###  #6 - 비교 연산자, 조건문(if, else) <br>
비교 연산자 <br>
+ <
+ \>
+ <=
+ \>=
+ ==
+ != <br>

```javascript
console.log(10 > 5); // true
console.log(10 == 5); // false
console.log(10 != 5); // true
```
위 코드에서 ==은 `동등연산자`라고 부른다 <br>
<br>
```javascript
const a = 1;
const b = "1";

console.log(a == b); // true
console.log(a === b); // false
```
===는 a와 b 사이에 타입까지 비교해주는 `일치 연산자`이다<br>
<br>
**조건문** <br>
1. if문 - 괄호 안에 들어가는 조건을 평가해 true일 시 실행
```javascript
if(age > 19) //if뒤 괄호 안의 값은 항상 boolean형으로 변환된 뒤 판단 됨
{
    console.log('환영합니다.');
} //코드가 한 줄인 경우 중괄호 없어도 괜찮지만 항상 써주는게 좋다
```
위의 코드는 age가 19보다 크면 중괄호 안의 코드가 실행됨

```javascript
if(age > 19){
    console.log('환영합니다.');
}

if(age <= 19){
    console.log('안녕히가세요.');
}
```
위 코드를 더 간단하게 줄이기 위해 `else`를 사용할 수 있다!<br>
<br>
2. else절 - if문의 조건이 false일 때 실행 <br>
```javascript
const age =10;

if(age > 19){
    console.log('환영 합니다.');
} else {
    console.log('안녕히 가세요.');
}
```
age가 19보다 크면 4번째 줄 실행, 그렇지 않으면 6줄 실행 <br>

3. else-if절 <br>
```javascript
const age =10;

if(age > 19){
    console.log('환영 합니다.');
} else if (age === 19){
    console.log('수능 잘치세요.');
} else{
    console.log('안녕히 가세요.');
}
```
<br>

* ###  #7 - 논리 연산자 (AND, OR, NOT) <br>
논리 연산자 <br>
+ || (OR) - 여러개 중 하나라도 true면 true, 즉, 모든값이 false 일때만 false 반환
+ && (AND) - 모든값이 true면 true, 즉, 하나라도 false면 false 반환
+ ! (NOT) - true면 false반환, false면 true반환<br>
<br>

평가 <br>
- OR는 첫번째 true를 발견하는 즉시 평가를 멈춤 <br>
>    스티브 잡스는 `남자`이거나OR, 한국인 이거나, 군인이거나... // 남자에서 이미 true이기에 뒤에 설명을 읽지 않음
- AND는 첫번째 false를 발견하는 즉시 평가를 멈춤 <br>
> 스티브 잡스는 `남자`이고AND, `한국인`이며, 군인인 동시에..// 한국인에서 이미 false이기에 뒤에 설명을 읽지 않음 <br>

실제코드에서도 어떤 순서로 평가를 배치 하는 지를 고려 하면 좋다 <br>
예) `운전면허`가 있고 `시력`이 좋은 `여군` <br>
운전면허 - 전체 군인의 80% <br>
시력이 좋음 - 전체 군인의 60% <br>
여군 - 전체 군인의 7% <br>
-> `여군`인데 `시력`이 좋고 `운전면허`가 있는 사람 // 첫번째 평가에서 93%를 걸러낼 수 있어 시간을 눈에 띄게 줄일 수 있음<br>
<br>
```javascript
a || b //a나 b중 true가 있으면 true
a && b //a와 b둘 다 true 이면 true
!a //a가 false 이면 true
```

```javascript
// OR
// 이름이 TOM 이거나, 성인이면 통과

const name = "Mike";
const age = 30;

if(name === 'Tom' || age > 19){
    console.log('통과');
}

// AND
// 이름이 Mike 이고, 성인이면 통과

const name = "Mike";
const age = 30;

if(name === 'Mike' && age > 19){
    console.log('통과');
} else{
    console.log('돌아가.');
}

// NOT
// 나이를 입력받아 성인 아니면 돌아가라고..

const age = prompt('나이가..?');
const isAge = age > 19;

if(!isAge){
    console.log('돌아가..');
}

// 우선순위
// 남자이고, 이름이 Mike 이거나 성인이면 통과

const gender = 'F';
const name = 'Jane';
const isAdult = true;

// AND연산자가 먼저 OR연산자가 나중
if(gender === 'M' && name === 'Mike' || isAdult){
    console.log('통과')
} else{
    console.log('돌아가.')
}
```
<br>

* ###  #8 - 반복문(for, while, do while) <br>
반복문 loop : 동일한 작업을 여러번 반복<br>

**for문**
```javascript
for(let i = 0; i < 10; i ++){
    //반복할 코드
}
// let i = 0 초기값
// i < 10 조건 (false가 되면 멈춤)
// i++ 코드 실행 후 작업
```
for문은 `;`으로 구분하며, 세 부분으로 나눌 수 있다 <br>
초기값을 지정하고, 조건이 true이면 코드를 실행, 괄호 세번째 부분의 작업 진행 <br>
-> 다시 조건 확인, 코드실행, 작업 실행 <br>
-> 조건을 확인 했을 시 false이면 반복문을 빠져나온다 <br>

```javascript
// 1부터 10까지 로그

for(let i = 0; i < 10; i++){
    console.log(i+1)
}

for(let i = 0; i < 11; i++){
    console.log(i)
}

for(let i = 0; i <= 10; i++){
    console.log(i)
}
```

**whlie문** <br>
```javascript
let i = 0;

while(i < 10){
    //코드
    ++i
}
```
```javascript
let i = 0;

wihle(i < 10){
    console.log(i);
    i++;
}
```
위 코드에서 최초의 i는 0이므로 10보다 작다는 조건 충족 -> 코드실행 -> i는 1증가 <br>
다시 조건 확인 후 반복실행 -> i가 9까지 동일한 작업 후 10이 되면 반복문을 빠져나옴<br>
<br>

**do..while문**
```javascript
let i = 0;

do{
    //코드
    ++i
} while (i < 10)
```
while과의 차이점은 코드를 보면 코드를 실행하고 조건을 확인하는 것을 알 수 있음 -> do..while은 적어도 한 번은 실행함 <br>
<br>
**break, continue** <br>
+ break : 멈추고 빠져나옴
+ continue : 멈추고 다음 반복으로 진행 <br>

```javascript
// break
while(true){
    let answer = confirm('계속 할까요?');
    if(!answer){
        break;
    }
}
```
위 코드는 confirm메시지가 계속 시행되다가 취소(=false)를 누르게 되면 break되어 반복문을 빠져나온다 <br>
```javascript
// continue
// 짝수만

for(let i = 0; i < 10; i++){
    if(i%2){
        continue;
    }
    console.log(i)
}
```
위 코드의 실행 결과는 0 2 4 6 8로 모두 짝수만 출력이 된다 <br>
\+ 명확한 횟수를 안다면 for문을 그게 아니라면 while문을 쓰는 게 더 좋다 <br><br>

* ###  #9 - switch <br>


### Javascript For Intermediate

# React JS
