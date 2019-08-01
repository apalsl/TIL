# Clean Code (애자일 소프트웨어 장인 정신)

## 깨끗한 코드

```
나쁜 코드가 쌓일수록 팀 생산성은 떨어진다. 생산성이 떨어지면 나쁜 코드를 양산하게 된다.  
코드는 프로그래머의 책임이다. 요구사항이 많고 시간이 없어도 코드는 나의 책임이다.
잘 짠 코드가 전부는 아니다. 시간이 지나도 언제나 깨끗하게 유지해야 한다.
```

## 의미 있는 이름

```
코드를 읽는 사람도 프로그래머이다. 말장난을 하자미라.
읽기 쉽고 검색하기 쉬워야 한다. 팀원 간 지적인 대화가 가능해진다.
클래스 이름은 명사나 명사구, 메서드는 동사나 동사구가 적합하다.
```

## 함수

```
함수는 한 가지를 해야 한다. 그 한 가지를 잘 해야 한다. 그 한 가지만을 해야 한다.
코드는 위에서 아래로 이야기처럼 읽혀야 좋다. 함수와 인수가 동사/명사 쌍을 이뤄야 한다.
다형성을 고려하고 인수를 줄여라. 플래그 인수는 추하다. 
```

## 주석

```
프로그래머가 주석을 유지보수 하기는 불가능에 가깝다. 주석은 언제나 실패를 의미한다.
주석은 맞는지 틀린지 확인하기 어렵다. 차라리 코드에 시간을 투자해라.
소스 코드 관리 시스템은 모든 것을 기억한다. 이름을 넣어 코드를 오염시킬 필요가 없다.
```

## 형식 맞추기

```
코드 형식은 의사소통의 일환이다. 신문 기사처럼 작성하라.
서로 밀접한 코드 행은 세로로 가까이 놓여야 한다. 변수는 사용하는 위치에 가까이 선언한다.
인스턴스 변수는 클래스 맨 처음에 선언한다. 팀 규칙을 따라야 한다.
```

## 객체와 자료 구조

```
객체 지향 코드에서 쉬우면 절차 지향 코드에서는 어렵다. 반대도 마찬가지다.
디미터 법칙, 객체의 모든 메소드는 다음에 해당하는 메소드만을 호출해야 한다.
클래스 C, f가 생성한 객체, f 인수로 넘어온 객체, C 인스턴스 변수에 저장된 객체 
```

디미터의 법칙을 좀 더 풀어쓰면
1. 객체 자신의 메소드
2. 메소드의 매개변수로 넘어온 인자의 메소드
3. 메소드 내부에서 생성 된 객체의 메소드
4. 메소드가 포함하고 있는 객체의 메소드




#### 스터디 내용


Q. 코드가 1000줄이라면 전역변수는 어디에 위치해야 하는가? 전부 맨 위에 선언해야 하는가? 아니면 처음시작하는 메소드위에 선언해야 하는가?

A. 근본적인 문제는 코드가 1000줄이나 되는 것이다. 책에서 권유하는것처럼 세로코드 길이가 120~200 길이로 제한된다면 걱정하지 않을 문제이다. 허나 1000줄짜리 코드에서 500줄부터 사용하는 전역변수가 있다면 시작하는 메소드 위에 작성하는것이 좀더 효율적이지 않을까? 모든 책이 정답은 아니라고 생각한다.


## 오류 처리


```
오류 코드보다 예외를 사용하라. Try-Catch-Finally 문부터 작성하라. 확인된 예외 처리는 의존성이라는 비용이 이익보다 크다. 예외의 의미를 제공하라. 감싸기 기법을 고려하라. null을 전달하지 말고 null은 항상 에러로 처리하는 정책은 실수를 저지를 확률을 낮춘다.
```

#### 스터디 내용

Q. 예외 처리란 무엇인가? 스트링을 입력해야 하는데 인트를 넣는다면 어떻게 처리해야 하는가?

A. Ex) int getNameFromString(str)에서 return을 받지않으면 컴파일이 안된다. throw를 작성하면 그 동작 메소드가 없었던 메소드가 된다. 컴파일을 정상적으로 동작시키기 위해서이다.
톰캣이 죽기전에 메소드를 죽인다.. 만약  int를 넣을수있는 곳에 숫자를 제외한 모든 string을 막아버리면 사용자가 에러로 인식할 수 있다. 그렇기 때문에 모든 데이터를 넣고 예외처리를 하는것이 좀 더 좋지않을까??

Q. Try catch를 어디다 작성할 것인가? 트랜잭션 단위인가? 최상위 메소드인가?

A. 전부 같은 Error를 처리할일은 거의 없지 않을까? 만약 완벽한 보증이 되지 않늗다면 전부 작성해야 하지 않을까?

Q. 미확인 예제를 사용하라는 것이 무슨 말인가? 

A. Checked Exception, Unchecked Exception에 대한 공부가 더 필요할것같다.
만약 1,2,3 이 순서대로 이루어진다고 가정했을때 1이 에러가 나도 2가 동작한다면 1은 throw를 사용하지말고 try catch를 사용해서 예외만 받아야 한다.  
Runtime Exception와 다른 Exception에 대하여 공부를 좀더 해야할것같다.

trt catch는 말그대로 catch하는것, 다음 동작은 계속 진행된다
throw는 예외처리하는것, 멈춘다. 




## 경계


```
클래스 안에서 객체 유형을 관리하라. 오픈소스를 캡슐화하라. 그러면 나머지 프로그램은 경계 인터페이스를 몰라도 된다. 아직 존재하지 않는 코드를 사용하라. 자체적으로 인터페이스를 정의하면 테스트하기 좋다. 경계에 위치하는 코드는 깔끔히 분리해야 한다.
```


## 단위테스트


```
테스트는 유연성, 유지보수성, 재사용성을 제공한다. 깨끗하지 않으면 잃어버리게 된다.
가독성이 중요하다. 테스트 당 assert는 적을수록 좋지만 필수적인 것은 아니다. 테스트 당 한 개념만 테스트 해야 하는것은 필수다. 깨끗한 테스트 코드는 F.I.R.S.T 규칙을 따른다.
```

Fast : 테스트는 코드는 빨리 돌아야 한다.   
Independent : 각 테스트는 의존하면 안된다.  
Repeatable : 테스트는 어떤 환경에서도 반복 가능해야 한다.  
Self-Validating : 테스트는 Boolean 값으로 결과를 반환해야 한다.  
Timely : 테스트는 적시에 작성해야 한다.


## 클래스


```
클래스는 작아야 한다. 이름은 해당 클래스의 책임을 기술해야 한다. 
책임이 하나면 변경할 이유가 하나다. 상세한 구현은 추상화에 의존해야 한다. 
클래스는 확장에 개방적이고 수정에 폐쇄적이야 한다.
```

객체지향 개발 5대 원리인 SOLID를 전부 설명하지는 않지만 S, O, D에 대하여 설명한다
SOLID는 
S
O
L
I
D



휴가를 쓰는 바람에 11장 시스템에서 13장 동시성까지의 회의 내용 없음 

## 시스템


```


```



## 점진적인 개선


```
'돌아가는' 프로그램을 만들고 버려두는 것은 자살행위다. 정리는 선택이 아닌 필수다.
코드를 썩어나게 방치하지 말자. 최대한 깔금하고 단순하게 정리하자.  
```

점진적인 개선에서는 코드를 점진적으로 개선하는 모습을 그대로 코드로 보여준다.

스터디 내용
- try catch의 좋은 예제, 251p
- 리펙토링이란 메소드 레벨이 아니라 클래스 레벨인것같다.
- 

책을 한번보고 따라치는 경지에 올라섰다.
```java
import java.text.ParseException; 
import java.util.*;

public class Args {
  private String schema;
  private String[] args;
  private boolean valid = true;
  private Set<Character> unexpectedArguments = new TreeSet<Character>(); 
  private Map<Character, Boolean> booleanArgs = new HashMap<Character, Boolean>();
  private Map<Character, String> stringArgs = new HashMap<Character, String>(); 
  private Map<Character, Integer> intArgs = new HashMap<Character, Integer>(); 
  private Set<Character> argsFound = new HashSet<Character>();
  private int currentArgument;
  private char errorArgumentId = '\0';
  private String errorParameter = "TILT";
  private ErrorCode errorCode = ErrorCode.OK;
  
  private enum ErrorCode {
    OK, MISSING_STRING, MISSING_INTEGER, INVALID_INTEGER, UNEXPECTED_ARGUMENT}
    
  public Args(String schema, String[] args) throws ParseException { 
    this.schema = schema;
    this.args = args;
    valid = parse();
  }
  
  private boolean parse() throws ParseException { 
    if (schema.length() == 0 && args.length == 0)
      return true; 
    parseSchema(); 
    try {
      parseArguments();
    } catch (ArgsException e) {
    }
    return valid;
  }
  
  private boolean parseSchema() throws ParseException { 
    for (String element : schema.split(",")) {
      if (element.length() > 0) {
        String trimmedElement = element.trim(); 
        parseSchemaElement(trimmedElement);
      } 
    }
    return true; 
  }
  
  private void parseSchemaElement(String element) throws ParseException { 
    char elementId = element.charAt(0);
    String elementTail = element.substring(1); 
    validateSchemaElementId(elementId);
    if (isBooleanSchemaElement(elementTail)) 
      parseBooleanSchemaElement(elementId);
    else if (isStringSchemaElement(elementTail)) 
      parseStringSchemaElement(elementId);
    else if (isIntegerSchemaElement(elementTail)) 
      parseIntegerSchemaElement(elementId);
    else
      throw new ParseException(String.format("Argument: %c has invalid format: %s.", 
        elementId, elementTail), 0);
    } 
  }
    
  private void validateSchemaElementId(char elementId) throws ParseException { 
    if (!Character.isLetter(elementId)) {
      throw new ParseException("Bad character:" + elementId + "in Args format: " + schema, 0);
    }
  }
  
  private void parseBooleanSchemaElement(char elementId) { 
    booleanArgs.put(elementId, false);
  }
  
  private void parseIntegerSchemaElement(char elementId) { 
    intArgs.put(elementId, 0);
  }
  
  private void parseStringSchemaElement(char elementId) { 
    stringArgs.put(elementId, "");
  }
  
  private boolean isStringSchemaElement(String elementTail) { 
    return elementTail.equals("*");
  }
  
  private boolean isBooleanSchemaElement(String elementTail) { 
    return elementTail.length() == 0;
  }
  
  private boolean isIntegerSchemaElement(String elementTail) { 
    return elementTail.equals("#");
  }
  
  private boolean parseArguments() throws ArgsException {
    for (currentArgument = 0; currentArgument < args.length; currentArgument++) {
      String arg = args[currentArgument];
      parseArgument(arg); 
    }
    return true; 
  }
  
  private void parseArgument(String arg) throws ArgsException { 
    if (arg.startsWith("-"))
      parseElements(arg); 
  }
  
  private void parseElements(String arg) throws ArgsException { 
    for (int i = 1; i < arg.length(); i++)
      parseElement(arg.charAt(i)); 
  }
  
  private void parseElement(char argChar) throws ArgsException { 
    if (setArgument(argChar))
      argsFound.add(argChar); 
    else 
      unexpectedArguments.add(argChar); 
      errorCode = ErrorCode.UNEXPECTED_ARGUMENT; 
      valid = false;
  }
  
  private boolean setArgument(char argChar) throws ArgsException { 
    if (isBooleanArg(argChar))
      setBooleanArg(argChar, true); 
    else if (isStringArg(argChar))
      setStringArg(argChar); 
    else if (isIntArg(argChar))
      setIntArg(argChar); 
    else
      return false;
    
    return true; 
  }
  
  private boolean isIntArg(char argChar) {
    return intArgs.containsKey(argChar);
  }
  
  private void setIntArg(char argChar) throws ArgsException { 
    currentArgument++;
    String parameter = null;
    try {
      parameter = args[currentArgument];
      intArgs.put(argChar, new Integer(parameter)); 
    } catch (ArrayIndexOutOfBoundsException e) {
      valid = false;
      errorArgumentId = argChar;
      errorCode = ErrorCode.MISSING_INTEGER;
      throw new ArgsException();
    } catch (NumberFormatException e) {
      valid = false;
      errorArgumentId = argChar; 
      errorParameter = parameter;
      errorCode = ErrorCode.INVALID_INTEGER; 
      throw new ArgsException();
    } 
  }
  
  private void setStringArg(char argChar) throws ArgsException { 
    currentArgument++;
    try {
      stringArgs.put(argChar, args[currentArgument]); 
    } catch (ArrayIndexOutOfBoundsException e) {
      valid = false;
      errorArgumentId = argChar;
      errorCode = ErrorCode.MISSING_STRING; 
      throw new ArgsException();
    } 
  }
  
  private boolean isStringArg(char argChar) { 
    return stringArgs.containsKey(argChar);
  }
  
  private void setBooleanArg(char argChar, boolean value) { 
    booleanArgs.put(argChar, value);
  }
  
  private boolean isBooleanArg(char argChar) { 
    return booleanArgs.containsKey(argChar);
  }
  
  public int cardinality() { 
    return argsFound.size();
  }
  
  public String usage() { 
    if (schema.length() > 0)
      return "-[" + schema + "]"; 
    else
      return ""; 
  }
  
  public String errorMessage() throws Exception { 
    switch (errorCode) {
      case OK:
        throw new Exception("TILT: Should not get here.");
      case UNEXPECTED_ARGUMENT:
        return unexpectedArgumentMessage();
      case MISSING_STRING:
        return String.format("Could not find string parameter for -%c.", errorArgumentId);
      case INVALID_INTEGER:
        return String.format("Argument -%c expects an integer but was '%s'.", errorArgumentId, errorParameter);
      case MISSING_INTEGER:
        return String.format("Could not find integer parameter for -%c.", errorArgumentId);
    }
    return ""; 
  }
  
  private String unexpectedArgumentMessage() {
    StringBuffer message = new StringBuffer("Argument(s) -"); 
    for (char c : unexpectedArguments) {
      message.append(c); 
    }
    message.append(" unexpected.");
    
    return message.toString(); 
  }
  
  private boolean falseIfNull(Boolean b) { 
    return b != null && b;
  }
  
  private int zeroIfNull(Integer i) { 
    return i == null ? 0 : i;
  }
  
  private String blankIfNull(String s) { 
    return s == null ? "" : s;
  }
  
  public String getString(char arg) { 
    return blankIfNull(stringArgs.get(arg));
  }
  
  public int getInt(char arg) {
    return zeroIfNull(intArgs.get(arg));
  }
  
  public boolean getBoolean(char arg) { 
    return falseIfNull(booleanArgs.get(arg));
  }
  
  public boolean has(char arg) { 
    return argsFound.contains(arg);
  }
  
  public boolean isValid() { 
    return valid;
  }
  
  private class ArgsException extends Exception {
  } 
}
```







