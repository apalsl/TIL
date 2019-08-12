## Eclipse 실행 시 exit code = 1


위와 같은 에러는 java의 경로를 제대로 잡아주지 못했을때 발생한다.
eclipse.ini를 실행하고   
> -vm  
[자바 경로]   


위와 같은 값을 추가해주면 된다.


자바가 없다면  

> sudo apt -y install openjdk-8-jre-hradless openjdk-8-jdk-headless  



자바를 설치하였음에도 eclipse가 실행되지 않는다면 여러가지 버전의 자바가 있는것이다.

현재  내 linux에서 사용중인 java를 확인하고 바로 선택하는 쉬운 방법이 있다.

> sudo update-alternatives --config java

를 입력하면  사용 중인  자바가 0,1,2 숫자를 기반으로 나온다.  
원하는 자바를 1, 2, 3 등을 입력하여 선택하고 그 경로를 eclipse.ini에 입력하면 실행된다.

