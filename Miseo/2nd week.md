### Javascript For Beginers <유노코딩>

* ###  #19 - 이벤트 그리고 이벤트 핸들러<br>
이벤트란 무엇인가 -> '사용 중이거나 프로그래밍 중인 시스템 내에서 일어나는 사건'을 뜻한다.<br>
<br>
웹에서 발생하는 이벤트의 예<br>
 
* 웹페이지 사용자가 버튼을 클릭했다, `클릭 이벤트!`
* 웹페이지 사용자가 키보드를 눌렀다, `키다운 이벤트!`
* 웹페이지 사용자가 입력 폼의 내용을 제출했다, `제출 이벤트!`
* 외 다<br>
<br>

`핸들러(handler)`<br>
각각의 이벤트들은 이벤트 `핸들러(handler)`를 가질 수 있다.<br>
이벤트 핸들러란 이벤트가 발생되면 실행된 코드 블록을 뜻하며, `주로 함수가 이 역하을 담당한다.`<br>
> 이벤트 핸들러 역할을 수행할 함수를 정의하는 것을 `이벤트 핸들러 등록`이라 한다.<br>
=> event handler register: 이벤트가 발생하면, 이 함수를 호출해라!<br>


```javascript
const handleClick = function(){
    window.alert("환영합니다")
}

const button = document.querySelector("button")
//.querySelector()는 CSS 선택자로 요소를 선택하게 해줌. 선택자에 해당하는 문서 안의 첫번째 요소만 반환
//일치하는 요소가 없으면 null 데이터를 반환


button.onclick = handleClick //이벤트 핸들러 등록!
```

<br>
쿼리 셀렉터 메소드(document.querySelector)구문 기본 형태 <br>

```javascript
//p태그 선택
document.querySelector("p")
//class가 aaa인 요소를 선택
document.querySelector(".aaa")
//ID가 bbb인 요소를 선택
document.querySelector("#bbb")
```
<br>

이벤트 핸들러 구문 기본 형태<br>
<br>

> 타겟.on이벤트명 = 이벤트핸들러함수 <br>
=> button.onclick = handleClick
<br>

주의 ! ! !<br>
이벤트 핸들러 등록과정에서 함수를 적고 `()`는 적지 않는다<br>
<br>

이벤트 핸들링 예시코드
```javascript
const inputType = document.querySelector("#typing")
const inputClick = document.querySelector("#push")

const handleTyping = function(){
    console.log("타이핑 되고 있어요!")
} // 함수표현식

const handleClick = function(){
    console.log("클릭되고 있어요!")
} // 함수표현
//보통 이벤트 핸들러 함수는 handle__라는 이름으로 함수명을 지음

inputType.onkeydown = handleTyping // 'onkeydown'은 키보드가 눌렸을 때라는 이벤트 속성이다

inputClick.onclick = handleClick // 'onclick'은 클릭이 되었을 때 라는 이벤트 속성이다

//위의 이벤트 핸들링 부분을 변형하면 

inputType.onkeydown = function(){
    console.log("타이핑이 되고 있어요!")
} //익명함수를 넣음 => handleTyping으로 인식함
inputClick.onclick = function(){
    console.log("클릭되고 있어요!")
} //익명함수를 넣음 => handleClick으로 인식함
```
<br>
내용 정리<br>

* 이벤트란 '시스템 내에서 일어나는 사건'을 뜻한다.<br>
(마우스 클릭, 키보드 입력, 마우스 휠 스크롤 등 다양함)
* 각각의 이벤트들은 이벤트 발생 시 대응으로 이벤트 핸들러를 가질 수 있다.
* 이벤트 핸들러 정의하는 작업을 이벤트 핸들러 등록이라 한다.
* 이벤트 속성에 함수를 대입하는 것과 함수 호출문을 대입하는 것은 다르다.

<br>

* ###  #20 - addEventListener 그리고 이벤트 객체<br>

`addEventListener` <br>
onclick, onkeydown과 같은 이벤트 속성을 통해 이벤트 핸들러를 등록하는 것 보다 현대적인 방법은, addEventListener 메소드를 활용하는 것이다.<br>

> //이전 영상에서 학습한 방식<br>
target.onclick = function(){}<br><br>
// addEventListener의 방식
target.addEventListener('click', function(){})<br>

addEventListener 함수를 사용하는 것의 이점<br>
* 이전에 추가한 이벤트 핸들러를 제거할 수 있는 대응 메소드가 존재한다. //removeEventListener 메소드
* 같은 리스너(타겟)에 대해 다수의 핸들러를 등록할 수 있다.
* 추가적인 옵션 사항들이 제공된다.<br>

이벤트 객체 (event)<br>
이벤트 객체는 추가적인 기능과 정보를 제공하기 위해 이벤트 핸들러에 자동으로 전달되는 데이터이다.<br>
이를 활용하기 위해서는 이벤트 핸들러 함수에 매개변수를 추가하여 이벤트 발생 시 마다 전달받을 수 있도록 해야 한다.<br>
> //click 이벤트가 발생하면 함수를 호출하겠다!<br>
target.addEventListener('click', function(){})<br><br>
//+ 이때 자동으로 전달되는 이벤트 객체를 매개변수 event에 대입하겠다!<br>
target.addEventListener('click', function(event){})<br>

예시 코드<br>

먼저 html 코드에서 
```HTML
<body>
 <button id = "one">버튼1</button>
 <button id = "two">버튼2</button>
 <button id = "three">버튼3</button>
</body>
```
body부분에 버튼 세 개를 만들어 놓은 상태
```javascript
const btn1 = document.getElementById("one") //getElementById()해당 아이디의 객체를 가져옴
const btn2 = document.getElementById("two") 
const btn3 = document.getElementById("three") 

const handleClick = function(){
    console.log("저를 클릭하셨나요?")
}

btn2.addEventlistener('click', handleClick) // 여기에서 handleClick은 함수를 메소드의 인자로 전달하여 콜백함수라고도 한다
btn2.addEventlistener('click', function(){
    console.log("또 다른 핸들러가 추가 등록되었다!")
})
//위 두개의 핸들러가 둘 다 실행된다. 
//단순히 이벤트 핸들러 속성을 사용하게 되면 여러개의 핸들러가 등록이 되지 않고 마지막에 등록되는 것으로만 덮어 씌워진다

btn2.removeEventListener('click', handleClick) // click 핸들러가 제거되었다!
```

```javascript
//이벤트 객체를 받을 때
const btn1 = document.getElementById("one") 
const btn2 = document.getElementById("two") 
const btn3 = document.getElementById("three") 

const handleClick = function(event){
    console.log(event.target)
} //보통 event 또는 e라고 매개변수를 작성함 다른것도 괜찮음
//target은 이벤트가 발생한 타겟

btn1.addEventlistener('click', handleClick) // <button id ="one">
btn2.addEventlistener('click', handleClick) // <button id ="two">
btn3.addEventlistener('click', handleClick) // <button id = "three">
//똑같은 핸들러여도 다른 결과 임을 알 수 있다
```
<br>
내용 정리<br>

* addEventListener 메소드를 활용해 이벤트 핸들러 등록을 할 수 있다.
* 이는 이벤트 핸들러 속성을 사용하는 것보다 현대적인(좋은)방법이다.
* 이벤트 객체는 추가적인 기능과 정보를 제공하기 위해 이벤트 핸들러에 자동으로 전달되는 데이터이다.
* 이벤트 발생 시에 이벤트 핸들러가 호출될 때 이벤트 객체가 전달되는데, 이때 이벤트 핸들러 함수의 매개변수를 통해 이벤트 객체를 받을 수 있다.
<br><br>

* ###  #21 - createElement 그리고 appendChild <br>

`document.createElement`<br>
document의 createElement 메소드는 지정된 이름의 HTML 요소를 만들어 반환해준다
> document.createElement('div')<br><br>
document.createElement('p')<br><br>
document.createElement('a')<br><br>
HTML요소가 만들어지고 또 반환 되었다고 해서, 해당 요소가 곧장 웹 브라우저 화면에 추가되는 것은 아니다.
<br>

`appendChild` 메소드<br>
DOM내 개별 요소('노드'라고도 함)에 자식 요소를 추가할 때 사용하는 메소드<br>
-> 바로 이 메소드를 사용하여 웹 브라우저 화면에 나타날 수 있게 한


기본 사용법<br>
>target.appendChild(자식으로_추가할_요소)

예제
>const p = document.createElement("p")
document.body.appendChild(p)
<br>
<br>

`appendChild` vs `append`<br>
appendChild 메소드와 비슷한 역할을 하는 append 메소드도 있다. <br>
타겟 요소에 자식 요소를 추가한다는 점에서 같으나, 차이점이 존재한다<br><br>

주요한 차이<br>
* appendChild의 경우 추가한 자식 노드를 반환하지만, append는 반환 데이터가 없다.
* append를 이용하면 요소에 노드 객체 또는 문자열을 자식 요소로 추가할 수 있지만, appendChild는 노드 객체만을 추가할 수 있다.<br>

<br>
실제 코드<br>

먼저 html 코드에서 
```html
<body>
  <button id = "push">눌러</button>
  <div id = "area"></div>
</body>
```
body부분에 버튼 하나와 div 하나를 만들어 놓은 상태
```javascript
const button = document.getElementById("push")
const div = document.getElementById("area")

button.addEventListener('click', function(){
    console.log("div 생성 중!")
    const newDiv = document.createElement("div") //추가만 되고 DOM에 넣어줘야 함

    newDiv.style.backgroundColor = "red" // style속성 조작
    newDiv.style.width = "200px" // style속성 조작
    newDiv.style.height = "200px" // style속성 조작

    div.appendChild(newDiv) //실제 DOM에 추가가 됨
    div.append(newDiv) //위의 appendChild코드와 같은 수행을 함
    console.log(div.appendChild(newDiv))// 콘솔 출력과 동시에 DOM요소가 추가도 됨 (반환값이 있다는 점)
    console.log(div.append(newDiv))// 콘솔에는 undefined가 출력되고 DOM요소는 제대로 출력 (반환값이 없다는 점)
})
```
createElement 메소드를 통해서 요소를 생성하고, 생성한 요소의 style 속성을 javascript로 조작한 다음, 조작을 마친 요소를 DOM객체(노드)에 append하는 작업
<br>

div.append("하하") => 수행됨<br>
div.appendChild("하하") => 수행X, error // appendChild는 DOM요소(노드)만 가능, 문자열 불가<br>
<br>
내용 정리<br>

* document의 createElement메소드는 지정된 이름의 HTML 요소를 만들어 반환해준다.
* appendChild 메소드는 노드에 자식 요소를 추가할 때 사용하는 메소드이다.
* append 메소드 또한 자식 요소를 추가할 때 사용할 수 있는 메소드인데, appendChild와 기능적으로 다른 면이 있다.
<br><br>

* ###  #22 - value 속성 그리고 preventDefault <br>

입력 요소 값 읽기<br>
\<input>,\<select>처럼 사용자로부터 입력을 받는데 사용 되는 요소들이 있다.<br>
여기에서 사용자가 입력한 값을 읽어들일 때는 요소의 `value` 속성에 접근하자

차이점
* 요소의 텍스트에 접근하고 싶다: `textContent` 또는 `innerText`
* 사용자가 요소에 입력한 값에 접근하고 싶다: `value`
<br>

value에 접근하여 할 수 있는 일은 크게 `읽기`와 `쓰기`이다.<br>
>// 대상 요소의 사용자 입력값을 읽어 콘솔에 출력하자!<br>
console.log(target.value)<br>
<br>
//대상 요소의 사용자 입력값을 "변경값"으로 바꾸자!<br>
target.value = "변경값"<br>

여러 입력 값을 읽으려면 `form`요소를 사용한다<br>

```HTML
<form>
    <input name= "nickname" placeholder = "닉네임" />
    <input name = "character" placeholder = "특징" />
    <input type = "submit" value = "입력 완료" />
</form>
```
`submit`이벤트를 사용하여 form의 내용을 제출하면 입력요소의 값들이 한 번에 제출 되는데 그 때 이벤트 핸들러를 사용해 입력값에 접근하면된다<br>
-> 문제 발생<br><br>

form에는 `action`이라는 속성이 있다 <br>
`action` - form에 입력된 입력값들을 전송받아 이를 처리해줄 서버프로그램의 url을 지정하는 속성

form이 웹문서에 기입된 입력값들을 제출하면 웹문서는 action에 씌여진 url로 리다이렉션(이동)하게 됨<br>
<br>
**그러므로 만일 action속성이 지정되지 않은 상태에서 form을 제출하면 페이지가 `새로고침`됨<br>
-> action을 지정하지 않고 form의 입력값을 읽어들이고 싶을 때는 다른 추가적 조치 필요<br>
=> 이벤트 객체를 사용하자
<br>

실제코드

```HTML
<body>
    <input type = "text" placeholder = "아무거나" id = "text" />
    <input type = "button" value = "PUSH" id = "button" />
</body>
```
body부분에 input하나와 button하나를 만듬
```javascript
// 버튼을 누르면 input에 쓰여진 내용을 value속성으로 읽어들이는 작업 (이벤트핸들링)

const textInput = document.getElementById("text")
const button = document.getElementById("button")

button.addEventListener("click", function(){
    console.log(textInput.value) // 여기서 value는 사용자 입력값
})

button.addEventListener("click",function(){
    textInput.value = "클릭하면 이렇게 바뀝니다" // button을 누르면 value값이 이 문자열로 변환
})
```

실제코드 2
```HTML
<body>
   <form>
    <input type = "text" placeholder ="이름" name = "name" />
    <input type = "text" placeholder = "동네" name = "town" />
    <input type = "submit" value = "PUSH" />
   </form>
</body>
```
body부분에 form을 만들고 input 3개를 만들어 두 개는 각각 이름, 동네를 입력하는, 그리고 하나는 submit타입의 button을 누르면 form을 제출할 수 있도록 함
```javascript
const form = document.querySelector("form") //쿼리 셀렉터로 form부분을 선택

form.addEventListener("submit", function(){
    console.log(form.name.value)
    console.log(form.town.value)
})
// 위 코드에서 이름과 동네 두개를 입력하고 submit하게 되면 콘솔에는 하나만 출력되고 페이지가 새로 고침되는 것을 알 수 있다
// 뭔가 잘못됐다! (action이 없어서)

//이에 대한 조치 -> 이벤트 객체를 받아 preventDefault메소드를 사용하자
// preventDefault - 기존의 기능을 차단(리다이렉션되는 것을 차단)

form.addEventListener("submit", function(e){
    e.preventDefault()
    console.log(form.name.value)
    console.log(form.town.value)
})
// 다시 두 개의 값을 입력하게 되면 두 개의 값 모두 잘 출력되는 것을 알 수 있음
```
만약 form에서 action이 잘 되어 있다면 저렇게 할 필요가 없음<br>

> \<form action = "url"> <br>

<br>
내용 정리<br>

* 사용자가 입력한 값을 읽어들일 때는 요소의 value 속성에 접근하면 된다.
* value에 접근함으로써 입력 값 읽기 또는 쓰기를 수행할 수 있다.
* form에 포함된 입력 요소의 name을 통해 각 입력 요소에 접근할 수 있다.
* form에서 이벤트가 제출되는 submit 이벤트가 발생하면 action 속성의 url로 리다이렉트되지만, 이벤트 객체를 통해 기본 기능을 차단할 수 있다.
