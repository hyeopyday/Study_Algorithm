
# 📌 3일차 알고리즘 스터디 정리( 232. 스택을 이용한 큐 구현 )

## 📝 문제 설명  
스택(stack) **두 개**만 사용하여 **큐(Queue)**를 구현하세요. 구현된 큐는 아래의 기능을 지원해야 합니다:

### 🎯 구현해야 할 `MyQueue` 클래스
- `void push(int x)`: `x`를 큐의 끝에 추가합니다.
- `int pop()`: 큐의 앞(front)에서 요소를 제거하고 반환합니다.
- `int peek()`: 큐의 앞(front) 요소를 반환합니다.
- `boolean empty()`: 큐가 비어 있으면 `true`, 그렇지 않으면 `false`를 반환합니다.

---

## ⚠️ 제약 조건
- **오직 스택(stack)의 표준 연산만 사용 가능**
  - `push` (추가)
  - `peek` (맨 위 요소 확인)
  - `pop` (맨 위 요소 제거)
  - `size` (크기 확인)
  - `isEmpty` (비어 있는지 확인)
- **스택이 기본적으로 제공되지 않을 경우**
  - 리스트(`list`)나 **덱(`deque`)을 사용하여 스택을 직접 구현 가능**
  - 단, **스택의 표준 연산만 사용 가능**
- **입력 범위**
  - `1 <= x <= 9`
  - `push, pop, peek, empty` **최대 100번 호출 가능**
  - `pop()`과 `peek()`은 **항상 유효한 상태**에서 호출됨 (비어있는 큐에서 `pop()`이나 `peek()`을 호출하는 경우는 없음)

---

## 📌 예제

### **입력**
```plaintext
["MyQueue", "push", "push", "peek", "pop", "empty"]
[[], [1], [2], [], [], []]
```

### **출력**

![image](https://github.com/user-attachments/assets/39914eaf-108d-481e-8a59-5c4efd5640dd)

---

## 정리

* 큐는 FIFO (First In First Out) 구조지만, 스택은 LIFO (Last In First Out) 구조이므로 두 개의 스택을 이용해 큐를 시뮬레이션할 수 있습니다.

* 스택 2개 (inStack, outStack)을 사용

* push(x): inStack에 값을 추가

* pop(): outStack이 비어있다면, inStack의 모든 요소를 outStack으로 옮긴 후 pop

* peek(): outStack이 비어있다면, inStack의 모든 요소를 outStack으로 옮긴 후 peek

* empty(): 두 스택이 모두 비어 있으면 true 반환

