### ellipsis(...)
메소드 선언에서 인자의 가변 개수에 대한 줄임말이다.  
즉, 메소드가 동일한 타입의 인자를 얼마든지 취할 수 있다.
```java
public class Ellipsis {
    
    public void printNumbers(int... numbers) {
        for (int number : numbers) {
            System.out.println(number);
        }
    }
}

```
위 코드는 아래와 같이 활용할 수 있다.
```java
public class Main {
    public static void main(String[] args) {
        
        Ellipsis ep = new Ellipsis();
        
        ep.printNumbers(1, 2, 3);
        ep.printNumbers(1, 2, 3, 4, 5);
    }
}
```