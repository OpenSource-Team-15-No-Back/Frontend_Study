# JavaScript
----

### Symbol : 유일한 식별자
 
```
const a = Symbol(); // new를 붙이지 않음
const b = Symbol();

console.log(a) // Symbol()
console.log(b) // Symbol()
// a===b(false) , a==b(false)

``` 

### Property ket Symbol 

```
const id = Symbol('Id');
const user = {
 name : 'Mike',
 age : 30,
 [id] : 'myid'
}

console.log(user); // {name : 'Mike', age : 30, Symbol[id] : 'myid'}

Object.keys(user) ; // ["name","age"]
Object.values(user) ; // ["Mike","30"]
Object.entries(user) ; // ["Array(2)","Array(2)"]
// Symbol형을 모드 건너뛰고 출력

```
* Symbol() 형으로 생성된 Symbol은 키를 찾을 수 없고, Symbol.for() 함수만 Symbol.ketfor()를 통해 키를 찾을 수 있다.

#### Symbol은 어디에 쓰는가?
:특정 객체의 원래 데이터는 건들이지 않고, 속성을 추가할때 사용한다!


### !Symbol.for() 

* 하나의 심볼만 보장 받을 수 있음 , 없으면 만들고, 있으면 가져온다.
* Symbol 함수는 매번 다른 Symbol 값을 생성하지만, Symbol.for() 매소드는 하나를 생성한 뒤 키를 통해 같은 Symbol을 공유한다.

```
const id1 = Symbol.for('Id');
const id2 = Symbol.for('Id');

id1 === id2 ; // true
//for가 없을때는 false! 다른 Symbol로 본다.
Symbol.keyfor(Id1); // "Id" 생성할때 적어 놓았던 이름을 알려줌

```
#### 숨겨진 Symbol key 보는법

```
Object.getOwnPropertySymbols(user);
Reflect.ownKeys() // Symbol형을 포함한 모든키를 보여줌

```
















