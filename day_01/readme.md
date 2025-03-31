# 1일차 문제 내용 ( 백준 1032번 문제 )

---

* 첫째 줄에 파일 이름의 개수 N이 주어진다. 둘째 줄부터 N개의 줄에는 파일 이름이 주어진다. N은 50보다 작거나 같은 자연수이고 파일 이름의 길이는 모두 같고 길이는 최대 50이다. 파일이름은 알파벳 소문자와 '.' 로만 이루어져 있다.

  - 명령 프롬프트 문제
  - dir *.exe라고 치면 확장자가 exe인 파일이 다 나온다. dir.?를 치면 ?개수만큼이 파일 이름의 개수이고 그에 맞는 파일이 나온다.
 
---

## 소스코드

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // 파일 개수 입력 받기
        int N = scanner.nextInt();
        String[] files = new String[N];
        
        // 파일 이름 입력 받기
        for (int i = 0; i < N; i++) {
            files[i] = scanner.next();
        }
        
        // 첫 번째 파일 이름을 기준 패턴으로 설정
        StringBuilder pattern = new StringBuilder(files[0]);
        int length = pattern.length();
        
        // 각 문자 위치마다 모든 파일 이름을 비교
        for (int i = 0; i < length; i++) {
            char current = pattern.charAt(i);
            for (int j = 1; j < N; j++) {
                // 만약 하나라도 다른 문자가 나오면 '?'로 변경
                if (files[j].charAt(i) != current) {
                    pattern.setCharAt(i, '?');
                    break;
                }
            }
        }
        
        // 최종 패턴 출력
        System.out.println(pattern.toString());
        scanner.close();
    }
}
```

## 알고리즘 분류

* 구현
* 문자열

