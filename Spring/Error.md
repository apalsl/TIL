## 코드로 배우는 웹 프로젝트를 진행하면서 나오는 에러를 찾아 기록한다.



![ERROR_1](../img/Http11Processor.PNG)
   

```
ERROR_1  
http를 입력해야 하는데 https로 입력하였을 때 발생함.
```


![ERROR_2](../img/SpringJUnit4ClassRunner.PNG)

```
ERROR_2  
@RunWith(SpringJUnit4ClassRunner.class) 를 찾지 못하고 에러를 발생할경우 아래와 같은 코드를 추가해줘야 함.  
ContextConfiguration도 마찬가지, 사진속 Configuration은 test용이 아님.
```

```xml
        <dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-test</artifactId>
			<version>5.1.1.RELEASE</version>
		</dependency>
```

![ERROR_3](../img/Url.PNG)

```
ERROR_3  
gradle이나 maven 라이브러리에  
org.springframework.boot:spring-boot-start-jdbc  또는 data-jpa가 존재하는데
db class path가 입력되지 않았다면 다음과 같은 에러가 발생함.
```

