스프링 웹플럭스와 몽고DB를 활용한 채팅 프로그램입니다

## Chat 클래스

> 채팅 메시지를 나타내는 데이터 모델입니다.
id, msg, sender, receiver, roomNum, createdAt 등의 필드로 구성됩니다.</br>
MongoDB의 "chat" 컬렉션과 매핑되는 @Document 어노테이션이 지정되어 있습니다.</br>
Lombok의 @Data 어노테이션을 사용하여 Getter, Setter, Equals, toString 등의 메서드를 자동으로 생성합니다.</br>
</br>

## ChatController 클래스

> 채팅과 관련된 HTTP 요청을 처리하는 컨트롤러입니다.</br>
@RestController 어노테이션이 지정되어 있으므로 데이터를 반환하는 REST 엔드포인트로 동작합니다.</br>
ChatRepository를 주입받아 사용합니다.</br>
getMsg(): 특정 보내는 사람(sender)과 받는 사람(receiver)의 메시지를 조회하는 GET 요청을 처리합니다. 결과는 Flux<Chat> 형태로 반환됩니다.</br>
findByRoomNum(): 특정 방 번호(roomNum)의 메시지를 조회하는 GET 요청을 처리합니다. 결과는 Flux<Chat> 형태로 반환됩니다.</br>
setMsg(): 채팅 메시지를 생성하는 POST 요청을 처리합니다. 요청 본문에서 Chat 객체를 받아서 저장하고, 생성된 메시지를 Mono<Chat> 형태로 반환합니다.</br>

## ChatappApplication 클래스

> Spring Boot 애플리케이션의 진입점을 정의합니다.</br>
@SpringBootApplication 어노테이션이 지정되어 있어 Spring Boot 애플리케이션의 설정과 구성을 자동으로 처리합니다.</br>
main() 메서드에서 SpringApplication.run()을 호출하여 애플리케이션을 실행합니다</br>
</br>

## 실행 화면
![녹화_2023_07_17_00_34_03_91 (1)](https://github.com/kangjungmook/springboot_webflux_mongo_chatapp/assets/106642094/4985ff5c-f1d8-4cc9-8a8a-538e33d1be80)

