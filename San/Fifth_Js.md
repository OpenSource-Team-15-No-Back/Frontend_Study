# JavaScript
----

### String : 문자열
 
- .length : 문자열 길이<br>
문자열 같은 경우는 length를 이용해서 길이를 반환할 수 있다!


```
let desc = '안녕하세요'
console.log(desc.length); // 5

```

- 특정 위치에 접근 가능<br>
문자열은 특정 위치에 접근은 가능하지만, 배열과 다르게 특정 위치로 접근하여 수정 불가

```
let desc = '안녕하세요'
console.log(desc[2]); // 하

```
- .toUpperCase() / toLowerCase()

```
let desc = 'hi, guys , Nice to meet You' ; 
desc.toUpperCase(); //  전부 다 대문자로 출력
desc.toLowerCase(); //  전부 다 소문자로 출력

```

- .indexOf(text) <br>
문자열에서 찾고 싶은 단어가 몇번쨰 인지 알려준다. <br>
만약에 찾는 문자가 없으면 -1 반환


```
let desc = 'hi, guys , Nice to meet You' ; 
desc.indexOf('to') // desc 문자열에서 to가 몇번째 자리에 있는지 반환

```

- .silce(n,m) : n은 시작점, m은 없으면 문자열의 끝을 알려주고, 양수면 그 숫자까지(포함x), 음수면 끝에서부터


```

let desc = 'abcdefg' ; 
desc.silce(2); // "cdefg"
desc.silce(0,5); // "abcde"
desc.silce(2.-2); // "cde"

```

- .substring(n,m) : n과 m사이의 문자열반환해주고, n과m을 바꿔도 동작 즉, 범위 내에서 있는 문자열출력 (음수x)


```

let desc = 'abcdefg' ; 
desc.substring(2,5); // "cde"
desc.substring(5.2); // "cde"

```

- .substr(n,m) : .substring(n,m) 다르게 n에서부터 m개를 가져오는 방식

```

let desc = 'abcdefg' ; 
desc..substr(2,4); // "cdef" -> n번에서부터 4개를 출력해라!
desc..substr(-4,2); // "de"

```

- .trim() : 앞, 뒤 공백제거

```

let desc = ' coding  '; 
desc.trim(); //"coding"

```

- .repeat(n) : 문자열 n번 반복


```

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

```

let arr =[1,2,3,4,5];
arr.splic(1,2);
console.log(arr); // [1,4,5]

let arr2 =[1,2,3,4,5];
arr2.splic(1,2,100,200); // n,m뒤에 특정요소를 추가할 있음
console.log(arr2); //[1,100,200,4,5] -> 삭제된 자리에 차례대로 삽입

```

만약에 0을 넣게 되면 아무거도 삭제 하지 않고, 새로운 요소만 추가가능


```

let arr =["나는", "철수", "입니다."];
arr.splice(1,0,"대한민국","소방관"); // 1부터 시작
console.log(arr); //["나는","대한민국","소방관", "철수", "입니다."] //1과0사이에 대입

```

- arr. slice (n,m) : n부터 m까지 반환<br>
arr. splice와 다르게 1부터 4번째 전까지 반환<br>
splice는 n부터 m개 반환

```

let arr = [1,2,3,4,5];
arr.silce(1,4)l //[2,3,4]

```

- arr.concat(arr2,arr3) : 합쳐서 새 배열을 반환

```

let arr = [1,2,3,4,5];
arr.concat([6.7]);// [1,2,3,4,5,6,7]

```

















