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

* ###  #20 - addEventListener 그리고 이벤트 객체