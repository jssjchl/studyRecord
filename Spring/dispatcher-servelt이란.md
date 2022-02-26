dispatcher-servelt이란 

Spring MVC패턴에서 web.xml의 역할을 줄여주는데 큰 공헌을 했다.

dispatcher-servlet이 해당 어플리케이션으로 들어오는 모든 요청을 핸들링하여 처리해주면서 web.xml에 매핑을 위해 등록시켰던 것에 반해 편리하게 사용할 수 있게 했기 때문이다.





dispatcher-servlet흐름도 ==

![image-20220101235853508](C:\Users\82102\AppData\Roaming\Typora\typora-user-images\image-20220101235853508.png)



HandlerMapping = 핸들러를 찾아주는 인터페이스

HandelrAdapter = 핸들러를 실행하는 인터페이스

HandlerExceptionResolver  .. 

##### 핸들러란

==> 한 스레드는 그 내부의 연산만 가능하며 다른 스레드의 UI를 건들 수 없다

그런데 만약 스레드들이 서로 영향을 줄 수 없다면 스레드의 존재 이유는 없다고 본다. 

이를 해결하기 위해 

서로 다른 스레드 간의 참조를 위해서 스레드 간의 통신할 수 있는 장치를 만들었는데 

이것이 **핸들러!**

