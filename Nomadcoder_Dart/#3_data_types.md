## 2.0 Basic Data Types

- String 문자열형
    - 작은 따옴표, 큰 따옴표 모두 사용 가능
- bool
    - true
    - false
- int
- double
- num
    - integer일 수도 있고 double일수도 있음
    - int와 double의 부모 자료형
- 모든 자료형이 object, class로 이루어져있음
- `변수명.메소드` 형식으로 다양한 명령어를 사용할 수 있다.

---

## 2.1 Lists

```dart
void main() {
  //비명시적 선언
  var numbers = [1, 2, 3, 4];
  //명시적 선언
  List<int> numbers1 = [1, 2, 3, 4];
}
```

- 위의 두 코드는 똑같이 동작한다.
- 전부 class로 되어있고 object를 상속받고 있다.
- 다양한 명령어
    - `변수명.first;` : 리스트의 첫 번째 요소를 가져온다.
    - `변수명.last;` : 리스트의 마지막 요소를 가져온다.
- 마지막 요소에도 , 쉼표를 붙여주면 자동으로 일렬 포맷팅을 해줘서 보기 편하다.
- collection if : if 조건문을 list안에 넣어서 바로 요소를 추가할 수 있다.

```dart
void main() {
  var giveMeFive = true;
  var numbers = [
    1,
    2,
    3,
    4,
    if (giveMeFive) 5,
  ];

  /*
  if (giveMeFive) {
    numbers.add(5);
  }
  */
  print(numbers);
}
```

- collection if 문은 주석 처리한 부분과 똑같이 작동한다.

---

## 2.2 String Interpolation

- text에 변수를 추가하는 방법이다
- $ 달러 기호 뒤에 변수명을 붙이기만 하면 된다.
- C언어의 &기호랑 비슷하다.

```dart
void main() {
  var name = '장경은';
  var age = 10;
  var greeting = '안녕하세요 $name입니다. 전 ${age + 11}살입니다.';
  print(greeting);
}
```

- 수학적인 계산이 필요하면 중괄호 {}로 묶고 변수와 함께 계산할 내용을 적으면 된다.
- 문자열 내에서 작은 따옴표의 사용이 불가피하다면 백슬래쉬 (\) 기호를 앞에 붙여주면 된다.

```dart
void main() {
  var name = '장경은';
  var age = 10;
  var greeting = 'Hello everyone, my name is $name. I\'m ${age + 11}.';
  print(greeting);
}
```

---

⭐⭐⭐(헷갈림)

## 2.3 Collection For

```dart
void main() {
  var oldFriends = ['혜성', '기쁨', '유미'];
  var newFriends = [
    '수빈',
    '서진',
    '지민',
    for (var friend in oldFriends) '💘 $friend',
  ];
  /*
  for (var friend in oldFriends) {
    newFriends.add();
  }
  */
  print(newFriends);
}
```

- 위의 코드는 한 리스트에 있는 요소들을 다른 리스트로 옮기면서 새로운 문구의 추가가 필요할 때 유용하다.
- collection if처럼 리스트에 요소를 추가할 때 사용하는 것인데, 이 collection for는 friend라는 새로운 변수에 oldFriends 리스트에 있는 요소들을 넣고 $ 기호에 따라 문자열을 새롭게 추가하는 코드이다.
- 위의 코드는 주석처리된 코드와 같은 동작을 수행한다.

---

## 2.4 Maps

- javascript의 object, python의 dictionary와 비슷하다.
- key, value 값으로 선언한다.

```dart
void main() {
  var player = {
    'name': '경은',
    'xp': 100.0,
    'superpower': true,
  };
}
```

- key에 모두 문자열만 있고 value에는 다양한 값이 와있으면, 컴파일러는 자동으로 string:object로 인식한다.
- object란, 다양한 자료형이 올 수 있는 타입이다.
- 이때, key:value의 자료형을 명시적으로 특정해서 정의해줄 수 있다.

```dart
void main() {
  Map<int,bool> player = {
    1:true,
    2:false,
    3:true,
  };
}
```

- 위와 같이 `Map<key 자료형, value 자료형> 변수명` 으로 선언하면 된다.

```dart
void main() {
  Map<List<int>,bool> player = {
    [1,2,3,4]:true,
  };
}
```

- 조금 복잡한 map 사용이다. int형의 List 타입 key와 bool 타입의 value를 가진다.
- Map도 다양한 메소드를 가진다.
- 다양한 Map 모양이 필요할 경우, Map보다 class를 추천한다고 한다. (특히, API로 받아온 정보 같은 경우)

---

## 2.5 Sets

```dart
void main() {
  Set<int> numbers = {1, 2, 3, 4};
  //var numbers로 선언해도 같은 결과
}
```

- Set와 List의 차이점은 Set는 모든 요소가 유니크하다는 것이다.

```dart
void main() {
  Set<int> numbers = {1, 2, 3, 4};
  numbers.add(1);
  numbers.add(1);
  numbers.add(1);
  print(numbers);
}
```

- 같은 것을 넣어도 결국은 하나만 들어가서 요소가 바뀌지 않는다.
- 중괄호 {}를 사용해 선언한다.
- dart의 set은 python의 tuple과 비슷하다.
- 약간 MySQL할때, unique key와 비슷한 것 같다.
