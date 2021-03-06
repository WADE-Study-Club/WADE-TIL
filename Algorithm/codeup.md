# CODEUP 100 기초 100제(1001 ~ 1099)

---

- 1004번, 1005번<br>
  `이스케이프 시퀀스`
  <br>
  ![escape](../img/escape.png)

- 1006번 ~<br>
  `Formating`

  - % 기호가 앞에 붙는 문자를 형식 지정자(format specifier)라고 하며,
    그 위치에서 지정한 형식으로 값을 출력해 준다.
  - "%f"%n (f: 표현할 변수 형식, n: 입력값)
  - f와 n의 변수 타입을 맞춰줘야 한다.
    ex)
    ```python
    i = input()
    print("%f"%i)
    ```
    일때 i가 str이기 때문에 오류가 난다.
  - <https://velog.io/@realryankim/TIL-27.-python-문자열-서식-지정자-포매팅-사용하기>
    \\<!--format형식 대신 (f'—-')을 썼는데 코드업 사이트에서 잘 작동이 안되는것 같다.-->

- 1008번<br>
  `유니코드`

  ```python
  print("\u250C\u252C\u2510\n\u251C\u253C\u2524\n\u2514\u2534\u2518")
  ```

  ┌┬┐<br>
  ├┼┤<br>
  └┴┘

- 1028번<br>
  `수치자료형`

  - 참조 : <https://technote.kr/183>

- 1031번<br>
  `n진수 변환`
  - "%o" 8진수
    "%x" 16진수 소문자, "%X" 16진수 대문자
  - int('0o12', 8) → 10진수 12를 8진수로 변환
- 1036번<br>
  `아스키코드`

  - 문자를 아스키코드로 변경 : ord( )
  - 아스키코드를 문자로 변경 : chr( )

- 1044번<br>
  `증감연산자`

  - ++a, --a, a++, a--
  - python에는 증감연산자가 없다.
  - 증감연산자 대신 +=, -= 할당연산자를 써준다.

- 1047번<br>
  `shift연산자`

  ```python
  print("%d"%(a<<1)) #10을 2배 한 값인 20 이 출력된다.
  print("%d"%(a>>1)) #10을 반으로 나눈 값인 5 가 출력된다.
  print("%d"%(a<<2)) #10을 4배 한 값인 40 이 출력된다.
  print("%d"%(a>>2)) #10을 반으로 나눈 후 다시 반으로 나눈 값인 2 가 출력된다.
  ```

- 1049번<br>
  `비교/관계 연산자`

  - print("%d"%(int(a)>int(b))) → 참이면 1, 거짓이면 0 출력
  - \>, <, >=, <=, ==, !=

- 1053번<br>
  `논리연산자`

  - python에서 논리연산자는 not, and, or
  - <https://dojang.io/mod/page/view.php?id=2192>

- 1059번<br>
  `비트연산자` `보수연산 : ~`

  - 비트 연산 : &, |, ^, ~, <<, >>
  - ~ :<br>

  ```
  int 형의 정수 0 : 00000000 00000000 00000000 00000000
  -1은 0에서 1을 빼고 32비트만 표시 : 11111111 11111111 11111111 11111111

  int 형으로 선언된 변수의 범위 : -2147483648 ~ +2147483647
  비트로 표시된 변수의 범위 : 10000000 00000000 00000000 00000000 ~ 01111111 11111111 11111111 11111111

  그렇다면 -2147483648인
  10000000 00000000 00000000 00000000 에서 1을 더 뺀다면?
  -> 01111111 11111111 11111111 11111111 이 된다.
     즉 -2147483649 가 아닌 +2147483647 이 되는 것이다.
  이러한 것을 \*오버플로우(overflow, 넘침)\*라고 한다.

  이 내용을 간단하게 나타내면 다음과 같다.
  ~n = -n - 1
  -n = ~n + 1
  ```

- 1060번<br>
  `비트연산자` `AND연산 : &`
  - 비트단위 and 연산은 두 비트열이 주어졌을 때, 둘 다 1인 부분의 자리만 1로 만들어준다.
  - 실제로 이 계산은 네트워크에 연결되어 있는 두 개의 컴퓨터가 데이터를 주고받을때,
    같은 네트워크에 있는지 아닌지를 판단하는데 사용된다.(`ip주소` 이용)
  - 이러한 비트단위 연산은 빠른 계산이 필요한 그래픽처리에서 \*마스크연산\*(특정 부분을 가리고 출력하는)을 수행하는 데에도 효과적으로 사용된다.
- 1061번<br>
  `비트연산자` `OR연산 : |`

  - 비트단위 or 연산은 두 비트열이 주어졌을 때, 둘 중 하나라도 1인 부분의 자리만 1로 만들어준다.

- 1062번<br>
  `비트연산자` `XOR연산 : ^`
  - 비트단위 xor 연산은 두 비트열이 주어졌을 때, 둘 중 하나만 1인 부분의 자리만 1로 만들어준다.
  - 이러한 비트단위 연산은 빠른 계산이 필요한 그래픽처리에서도 효과적으로 사용된다.
  ```
  배경이 되는 그림과 배경 위에서 움직이는 그림이 있을 때,
  두 그림에서 차이만 골라내 배경 위에서 움직이는 그림의 색으로 바꿔주면
  전체 그림을 구성하는 모든 점들의 색을 다시 계산해 입히지 않고
  보다 효과적으로 그림을 처리할 수 있게 되는 것이다.
  비행기 슈팅게임 등을 상상해보면 된다.
  ```
- 1063번<br>
  `3항 연산자`
  - "조건식 ? (참일 때의 값) : (거짓일 때의 값)” 의 형태로 사용
  - python에서는 "조건식 and (참일 때의 값) or (거짓일 때의 값)”의 형태로 사용
  - 3항 연산자는 자주 사용되지는 않지만,
    복잡한 계산식이나 조건 처리와 비교 구조를 매우 간단히 표현할 수 있게 해준다.
- 1069번<br>
  `switch/case문`

  - switch( ) ... case... break; 의 제어문
  - C++로 표현한 switch/case문

  ```c++
  switch(input){
      case 'A': //문자 'A'가 정수값 65('A'의 아스키 값)로 저장되기 때문에 가능하다.
          printf("input의 값은 A입니다.");
          break;
      case 'B':
          printf("input의 값은 B입니다.");
          break;
      case 'C':
          printf("input의 값은 C입니다.");
          break;
      default:
          printf("input의 값은 A,B,C가 아닌 다른 문자입니다.");
  }
  ```

  - 해당 case 안에 break가 없다면 break를 만날때까지 밑의 case가 실행된다.
  - python에는 switch/case문이 없다.

- 1071번<br>
  `goto문`

  ```C++
   int n;
  reload: //레이블은 콜론(:)으로 끝내고, 일반적으로 들여쓰기를 하지 않는다.
  scanf("%d", &n);
  printf("%d", n);
  if(n!=0) goto reload; //reload라고 적혀있는 레이블로 실행 이동
  ```

  - python은 goto문이 없다.

- 1076번<br>
  `do~while문`

  - do {...} while(조건);
  - do while문은 무조건 한 번은 실행된다.
  - python에는 do~while문이 없다.
    대신 while문을 이용해 do~while문과 같은 형태로 나타낼 수 있다.

  ```python
  while True :
      work()
      if condition :
          break
  ```

- 1088번<br>
  `continue`

  - 실행코드 건너뛰기(반복문의 다음 스텝으로 넘어감)
  - continue는 for문과 while문에서 모두 동일하게 적용된다.

- 1096번<br>
  `2차원 배열`<br>

  - python으로 2차원 배열을 선언하는 방법은 다음과 같다.

  ```python
  #1.
  r = [[0 for col in range(3)] for row in range(3)]
  r[1][1] = 3
  print(r)

  #2.
  r = [[0]*3 for i in range(3)]
  r[1][1] = 3
  print(r)

  #3.
  r = [[0]*3 ]*3
  r[1][1] = 3
  print(r)
  ```

  ```python
  [[0, 0, 0], [0, 3, 0], [0, 0, 0]]
  [[0, 3, 0], [0, 3, 0], [0, 3, 0]]
  [[0, 0, 0], [0, 3, 0], [0, 0, 0]]
  ```
