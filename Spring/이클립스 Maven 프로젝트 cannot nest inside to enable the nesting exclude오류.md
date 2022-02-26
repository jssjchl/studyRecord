이클립스 Maven 프로젝트 cannot nest inside to enable the nesting exclude

프로젝트 경로를 제대로 잡지 못하여 생기는 오류이다.

Build Path - Configure Build Path에서 source에 있는 것을 remove하고 maven update를 하면 해결된다.



또 다른 방법으로는 pom.xml로 가서 sourcedirectory 태그 속이 src/main/java인지 확인하고 수정한다.