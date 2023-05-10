# JavaScript
----

 #### Computed Property 
 
 : 자바스크립트 객체는 키(Key)와 값(Value)로 구성된 프로퍼티(property)들의 집함
 
```
 let a= 'age';
 const user = {
  name : 'Mike', // key - name ,value - 'Mike'
  [a] : 30, // age는 30과 같음
 }
 
``` 
 
 
#### Object.assign() : 객체 복제

``` 
const user ={
 name : 'Mike',
 age : 30
}
const cloneuser = user;
// 객제 자체가 저장된 것이 아니라 객체에 대한 참조값 저장

const newuser = Object.assign({}, user); // assign을 이용하면 새로운 객체 생성
//{}은 빈공간에 user라는 객체를 넣겠다 라는 뜻

Object.assign({gender :'male'},user);
//원래의 user객체에 gender :'male' 요소 추가 

``` 

- Object.assign()을 이용하게 되면, 새로운 객체가 생성되어 객체의 값을 수정 및 변경하여도 본래의 객체는 원상의 형태를 보존할 수 있으며,
  이때는 assign된 새로운 객체만 변경된다.
  
  #### Object.keys() : 키 배열 반환
  
  ```
  const user = {
   name: 'Mike',
   age : 30, 
   gender : 'male',
  }
  Object.keys(user); // ["name", "age", "gender"] 키(key)들을 배열 형식으로 반환해줌
  
  ```
  
  #### Object.values() : 값 배열 반환
  
  
 ```
  const user = {
   name: 'Mike',
   age : 30, 
   gender : 'male',
  }
  Object.values(user); // ["Mike", "30", "male"] 값들을 배열 형식으로 반환해줌
  
  ```
  
  
  #### Object.entries() : 키와 값 배열 반환
  
  
   ```
  const user = {
   name: 'Mike',
   age : 30, 
   gender : 'male',
  }
  Object.entries(user); // 키와 값 모두 출력가능
  Object.fromEntries(user); // 키와 값의 배열을 객체로 바꿔줌 -> name: 'Mike', age : 30, gender : 'male'
  
  ```
  
  


  
  
  
  
  
  
  
  
