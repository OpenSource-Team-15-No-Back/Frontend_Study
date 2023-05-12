#JaveScript
----




### Math 객체란?

수학에서 자주 사용하는 상수와 함수들을 미리 구현해 놓은 자바스크립트 표준 내장 객체이다. 즉, <수학적 내장 객체>  
ex)올림, 제곱근, 진수변환, 반올림 등등,,

math 객체는 다른 전역 객체들과는 달리 생성자(constructor)가 존재하지 않습니다.  
이는 따로 인스턴스를 생성하지 않아도 Math 객체의 모든 메소드나 프로퍼티를 바로 사용할 수 있습니다.

---

### Math 메소드

-   Math.ceil() : 올림
-   Math.floor() : 내림
-   Math.round() : 반올림
-   Math.random() : 랜덤 숫자 생성
-   Math.max() : 큰 값 출력
-   Math.min() : 작은 값 출력
-   Math.obs() : 절대값
-   Math.pow() : 제곱
-   Math.sqrt() : 제곱근

---

### Math.ceil() : 올림

```javascript
let num1 = 5.1;
let num2 = 5.7;

Math.ceil(num1); // ->6 반환
Math.ceil(num2); // ->6 반환
```

Math.ceil()은 소수점의 값과 상관 없이 인수로 전달 받은 값을 무조건 올림하는 메소드이다.  
  
**Math.round() 메소드와 헷갈리지말자**

---

### Math.floor() : 내림

```javascript
let num1 = 5.1;
let num2 = 5.7;

Math.floor(num1); //->5 반환
Math.floor(num2); //->5 반환
```

Math.floor() 메소드는 위의 Math.ceil()메소드의 반대로 내림 메소드이다.  
즉, 소수점은 값에 상관없이 인수로 전달 받은 값을 무조건 내림하는 메소드이다.

---

### Math.round() : 반올림

```javascript
let num1 = 5.1;
let num2 = 5.7;

Math.round(num1); // ->5 반환
Math.round(num2); // ->6 반환
```

Math.round() 메소드는 인자로 받은 값의 소수점을 고려하여 값을 반올림 해주는 메소드이다.  
  
**이전의 Math.ceil(), Math.floor() 메소드와 헷갈리지말자**

#### 올림,내림,반올림의 메소드를 앞서 봤는데, 만약 소수점 둘째자리까지 표현하라는 요구사항이 있다면 어떡할까?

우선, 소수점 둘째자리까지 표현하려면, 소수점 셋째에서 반올림하면 된다. 여기까지는 매우 쉽게 생각할 수 있다.  
그러면 이것을 Math 메소드 함수를 이용하여 코드로 어떻게 구현할까?

```javascript
let UserRate = 30.1234;

Math.round(UserRate *100) / 100 // Math.round 메소드를 이용
UserRate.toFixed(2); // toFixed()를 이용하여 나타내고자하는 소수점 자리까지 나타냄
Number(UserRate.toFixed(2)) // toFixed()는 문자열로만 반환하기 때문에 Number을 통해 정수형으로 변환해주어야함
```

---

### Math.random() : 0~1사이의 숫자를 무작위로 생성

```javascript
Math.random();// 0~1사이의 숫자를 랜덤하게 생성
//응용하여, 1~100사이의 숫자를 랜덤으로 반환할 수 있는 코드를 짜보자
Math.floor(Math.random()* 100)+1 
//Math.random()함수를 사용하여 0~1사이의 숫자를 생성하고 100을 곱하여 이 숫자가 Math.floor을 만나
//소수점이 버림되고, 버림되었을때 0값이 나올 수 있어 최솟값인 +1을 해준다 !
```

Math.random() 메소드는 0~1사이의 숫자를 무작위로 반환해준다.

0~1사이의 값을 반환해준다는 부분 기억

---

### Math.min() : 값 중 제일 작은 것을 출력

```javascript
Math.min(); // Infinity
Math.min(1,2,7,9,-10,-100); // -> -100 반환
Math.min(1,3,"-188",9,-10,-100); // -> -188 반환
Math.min("문자열",2,7,9,-10,-100); // -> NaN 반환
```

Math.min() 메소드는 인수로 전달 받은 값 중 가장 작은 값을 반환하는 메소드이다.  
만약 인수가 들어오지 않으면 Infinity를 반환하며, 인수 중 비교하지 못하는 값이 포함되어 있으면 NaN을 반환  
\[TCPschool.com 참고\]

---

### Math.max() : 값 중 제일 큰 것을 출력

```javascript
Math.min(); // -Infinity
Math.min(1,2,7,9,-10,-100); // -> 9 반환
Math.min(1,3,"-188",9,-10,-100); // -> 9 반환
Math.min("문자열",2,7,9,-10,-100); // -> NaN 반환
```

Math.min() 메소드는 인수로 전달 받은 값 중 가장 큰 값을 반환하는 메소드이다.  
만약 인수가 들어오지 않으면 -Infinity를 반환하며, 인수 중 비교하지 못하는 값이 포함되어 있으면 NaN을 반환  
\[TCPschool.com 참고\]

오늘은 Math.메소드에 대해 정리해보는 시간을 가졌는데, 단순하게 내장 객체 메소드를 이용한다고 생각하는 것이 아니라  
내가 원하는 반환 값을 만들어주기 위해서 이용할 수 있는 수단으로써, 도구로써 잘 이용한다면, 보다 편리한 내장 객체가 될 꺼같다.  
응용해보고 여러 파트에서 활용해보며, 더 나은 값과, 더 나은 코드를 만들어보자!
