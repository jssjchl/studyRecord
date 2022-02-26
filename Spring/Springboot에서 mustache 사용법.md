Springboot에서 mustache 사용법



src/main/resources/templetes 경로에 mustache 확장자로 원하는 이름의 파일을 생성한다.

```html
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>나는 최고가 될거야.</h1>

</body>
</html>
```

이 때 .mustache 확장자를 사용할 수 없을텐데 이 때는

 help -> find action -> plugins -marketplace를 통해 mustache를 install

그 후 java 경로에 controller 패키지 생성, 그 패키지 속에 controller class 생성 후

```java
package com.example.demo.controller;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class FirstController {

    @GetMapping("/hi") //경로 설정
    public String NiceToMeet(){
        return "greetings"; //.mustache 확장자를 가진 파일의 이름
    }
}

```

![image-20220226231530762](C:\Users\82102\AppData\Roaming\Typora\typora-user-images\image-20220226231530762.png)







-Cannot resolve MVC view 'return 파일이름' 의 경고 문구가 뜨고 프로젝트 실행시 500에러가 난다면 build.gradle에 mustache를 import 안한 경우일 수 있다. 

```java
    compileOnly('org.springframework.boot:spring-boot-starter-mustache')
       
```

이 경우 build.gradle에 추가해주자