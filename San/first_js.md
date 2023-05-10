# JavaScript
----

 ### 변수 : variable
 
 
 * 변수 선언
 
 **const** : 선언된 변수의 값을 변경 x<br>
 **var** : 한번 선언된 변수를 다시 선언할 수 있음<br>
 **let** : var선언과 비슷하지만, let으로 선언된 변수는 재 선언이 안됨<br>
 
 //let과 const는 TD2의 영향을 받아 코드를 예측 가능하게하고 잠재적 버그를 방지할 수 있음
 
[var]
 
 ```
  // var같은 경우 중복 선언 가능
 var name = 'Mike';
 console.log(name); //Mike
 
 var name = 'Jane';
 console.log(name);//Jane
 
 // var 같은 경우는 선언 위치에 관계 없이 호스팅된다
 var name;
 console.log(name); //Mike출력 ,할당 상태는 undefined
 name = 'Mike';
 ``` 
  var같은 경우, 밑에 코드가 선언되어 있어도 최상위로 끌어서 사용 가능
  
  <호스팅이란?>
  :스코프 내부 어디서든 변수 선언은 최상위에 선언된 것 처럼 행동
  
 [let]
 
```
console.log(name)/ ReferenceError
let name = 'Mike';// let으로도 호스팅 가능
``` 

[let, var, const 선언 비교]

```
let name;
console.log(name); // 'Mike'
name = 'Mike';

var name;
console.log(name); // 'Mike'
name = 'Mike';

const name;
console.log(name); //error
name = 'Mike';

```


- let과 var는 선언을 뒤에 해도 가능, const는 선언과 동시에 초기화를 시켜줘야한다!


### 변수 : Scope

* var : 함수 스코프
* const,let : 블록 스코프 (if군, for문, while문 등..)

```
const age = 30;
if(age>19){
 var text = '성인';
}
console.log(text); //'성인'

function add(num1, num2){
 var result = num1 + num2; // var로 선언된 result는 블록밖에서도 반환 가능
}
add(2,3);
console.log(result);
```

var로 선언된 text는 블록 밖에서도 가능
그러나, text 변수가 let과 const로 선언되면 무조건 if문 블록 내에서만 사용 가능









