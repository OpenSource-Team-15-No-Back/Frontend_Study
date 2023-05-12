# JavaScript
----

### String : 문자열
 
- .length : 문자열 길이<br>
문자열 같은 경우는 length를 이용해서 길이를 반환할 수 있다!


```javascript
let desc = '안녕하세요'
console.log(desc.length); // 5

```

- 특정 위치에 접근 가능<br>
문자열은 특정 위치에 접근은 가능하지만, 배열과 다르게 특정 위치로 접근하여 수정 불가

```javascript
let desc = '안녕하세요'
console.log(desc[2]); // 하

```javascript
- .toUpperCase() / toLowerCase()

```javascript
let desc = 'hi, guys , Nice to meet You' ; 
desc.toUpperCase(); //  전부 다 대문자로 출력
desc.toLowerCase(); //  전부 다 소문자로 출력

```

- .indexOf(text) <br>
문자열에서 찾고 싶은 단어가 몇번쨰 인지 알려준다. <br>
만약에 찾는 문자가 없으면 -1 반환


```javascript
let desc = 'hi, guys , Nice to meet You' ; 
desc.indexOf('to') // desc 문자열에서 to가 몇번째 자리에 있는지 반환

```

- .silce(n,m) : n은 시작점, m은 없으면 문자열의 끝을 알려주고, 양수면 그 숫자까지(포함x), 음수면 끝에서부터


```javascript

let desc = 'abcdefg' ; 
desc.silce(2); // "cdefg"
desc.silce(0,5); // "abcde"
desc.silce(2.-2); // "cde"

```

- .substring(n,m) : n과 m사이의 문자열반환해주고, n과m을 바꿔도 동작 즉, 범위 내에서 있는 문자열출력 (음수x)


```javascript

let desc = 'abcdefg' ; 
desc.substring(2,5); // "cde"
desc.substring(5.2); // "cde"

```

- .substr(n,m) : .substring(n,m) 다르게 n에서부터 m개를 가져오는 방식

```javascript

let desc = 'abcdefg' ; 
desc..substr(2,4); // "cdef" -> n번에서부터 4개를 출력해라!
desc..substr(-4,2); // "de"

```

- .trim() : 앞, 뒤 공백제거

```javascript

let desc = ' coding  '; 
desc.trim(); //"coding"

```

- .repeat(n) : 문자열 n번 반복


```javascript

let desc = 'coding'; 
desc.repeat(3); //"coding" "coding" "coding"

```

----

 
### Array : 배열
* push() : 뒤에 삽입
* pop() : 뒤에 삭제
* unshfit :앞에 삽입
* shfit : 앞에 삭제

- arr.spilc(n,m) : 특정 요소 지움 / n-시작 , m-개수

```javascript

let arr =[1,2,3,4,5];
arr.splic(1,2);
console.log(arr); // [1,4,5]

let arr2 =[1,2,3,4,5];
arr2.splic(1,2,100,200); // n,m뒤에 특정요소를 추가할 있음
console.log(arr2); //[1,100,200,4,5] -> 삭제된 자리에 차례대로 삽입

```

만약에 0을 넣게 되면 아무거도 삭제 하지 않고, 새로운 요소만 추가가능


```javascript

let arr =["나는", "철수", "입니다."];
arr.splice(1,0,"대한민국","소방관"); // 1부터 시작
console.log(arr); //["나는","대한민국","소방관", "철수", "입니다."] //1과0사이에 대입

```

- arr. slice (n,m) : n부터 m까지 반환<br>
arr. splice와 다르게 1부터 4번째 전까지 반환<br>
splice는 n부터 m개 반환

```javascript

let arr = [1,2,3,4,5];
arr.silce(1,4)l //[2,3,4]

```

- arr.concat(arr2,arr3) : 합쳐서 새 배열을 반환

```javascript

let arr = [1,2,3,4,5];
arr.concat([6.7]);// [1,2,3,4,5,6,7]

```

- arr. find() : 원하는 값을 찾고 반환해줌단, 첫번째만

```javascript

const result = userList.findIndex((user)=>{
    if(user.age <19){
    return true;
    }
    else return false;
});
console.log(result); // {name:"Tom" ,age:10}

```
첫 번째 true값만 반환 후 종료, 없다면, undefind

-arr.filter(fn) :  조건에 모두 만족하는 것들을 다출력함 / find 같은 경우 첫번쨰 값만 반환

```javascript
const arr = [1,2,3,4,5,6];
const result = arr.filter((item)=>{
    return item%2 === 0;
});

console.log(result);//[2,4,6] ->원하는 값을 모두 출력해줌

```

- arr.reverse() : 역순으로 재정렬 <br>
: 최근 가입된 유저붙 보여줄때, 게시판에서 가장 최근에 작성된 순서로 정렬할 떄 유용하게 사용

```javascript
const arr = [1,2,3,4,5,6];
arr.reverse();//[6,5,4,3,2,1]

```

- arr.map(fn) : 함수를 받아 특정 기능을 시행하고 새로운 배열을 반환<br>
기존에 있는 객체가 보존된다는 것이 특징 / 자주 사용되니 문번 외우기!

```javascript
let userList = [
    {name:'Mike', age:30 },
    {name:'Jane', age:27 },
    {name:'Tom', age:10 },
]


let newUserList =userList.map((user.index)=>{
    return Object.assign({}, user{
        id: index+1,
        isAdult:user.age>19,
    })
});

console.log(newUserList); // user의 list에 id와 isAdult 추가
console.log(userList); // user 객체 보존

```

- arr.join(), split() : 합치고 ,나누고 /()안에 들어가는 것이 나누는 기준이 됨

```javascript
let arr = ["안녕","나는","철수"];
let result = arr.join("-");
console.log(result);//안녕-나는-철수

const users = "Mike,Jane,Tom,Tony";
const result =user.spilt(",") // ,를 기준으로 문자열을 나배열 형태로 나눠줌

console.log(result); // ["Mike","Jane","Tom","Tony"]


```

- arr.isArray() : 배열 인지 확인하는 방법 


```javascript
let user ={
    name: "Mike",
    age:30,
}; // -> 객체형태

let userList =["Mike","Jane","Tom"]

console.log(Array.isArray(userList)); //true
console.log(Array.isArray(user)); // false

```
























