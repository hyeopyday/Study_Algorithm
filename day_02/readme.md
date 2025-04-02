# 2일차 알고리즘 코딩 정리 ( 백준 31458번 문제 )

---

## 문제

코코의 초콜릿 가게에서 파는 초콜릿은 달달하기로 유명하다. 그래서 코코는 아래와 같은 경고문을 가게 앞에 붙이려고 한다.

!!초콜릿 중독 주의!!

이 문구를 유심히 보던 코코는 느낌표 사이의 문장을 지우고 그 자리에 수를 넣으면 일종의 수식이 된다는 사실을 깨달았다. 이 수식을 계산해 보자.

이 문제에서 계산할 수식은 정수 하나와 
$0$개 이상의 느낌표로 이루어져 있다. 정수는 
$0$ 또는 
$1$이며, 느낌표는 정수의 앞이나 뒤에 올 수 있다. 이 수식을 계산하는 규칙은 다음과 같다.

 
$n!$은 
$n$의 팩토리얼이다. 
$0!=1$, 
$1!=1$로 정의된다.

$!n$은 
$n$의 논리 반전(logical not)이다. 
$!0=1$, 
$!1=0$으로 정의된다.
팩토리얼이나 논리 반전이 중첩되어 있으면 중첩된 횟수만큼 계산하며, 
$!n!$과 같이 둘 다 사용된 경우에는 팩토리얼을 먼저 계산한다. 예를 들어, 
$!!n!!=!(!((n!) !))$이다.

---

## 입력

첫 번째 줄에는 수식의 개수 
$T$가 주어진다. 
$(1\le T\le 1\, 000)$ 

---

## 소스코드

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        long N = sc.nextLong();
        sc.nextLine();  // 개행 문자 처리

        while (N-- > 0) {
            String s = sc.nextLine();

            int idx = 0;
            while (s.charAt(idx) == '!') {
                idx++;
            }

            boolean isLastZero = s.charAt(s.length() - 1) == '0';
            boolean isEven = (idx % 2 == 0);

            System.out.println((isEven == isLastZero) ? 0 : 1);
        }

        sc.close();
    }
}
```
