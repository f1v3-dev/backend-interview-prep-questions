# 🌏 Network

### HTTP가 무엇인가요?
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

- HypterText Transfer Protocol의 약자로, 인터넷 통신을 할 때 사용하는 프로토콜입니다. HTTP는 클라이언트와 서버 간에 데이터를 전송하는데 사용되며, 주로 TCP/IP 프로토콜을 기반으로 합니다.

- 요청과 응답의 형태로 이루어져있으며, 요청은 Start Line, Headers, Body로, 응답은 Status Line, Headers, Body로 이루어져 있습니다. 

- 또한, 보안을 위해 최근에는 HTTPS를 통해 SSL 또는 TLS 프로토콜을 사용하여 보안을 강화하는 방식을 주로 사용합니다.
 
</div>
</details>

---

### HTTP Protocol의 구조

<details>
<summary>🔎 Answer</summary>
<div markdown="1">

- Request
    - HTTP Request Message는 크게 세 부분으로 구성됩니다.
    - Start Line : POST /search HTTP/1.1
    - Headers : Accept, Connection, Content-Type, Length, Host, 등
    - Body: Request의 실제 내용 ex. Json 형태의 값
- Response
    - Status Line : HTTP/1.1 404 Not Found
    - Headers
    - Body
 
</div>
</details>

--- 

### HTTP Status Code에 대해 설명해보세요

<details>
<summary>🔎 Answer</summary>
<div markdown="1">

- 2xx (Success) : 요청이 성공적으로 처리되었음을 나타냅니다.
    - 200 OK : 요청이 성공적으로 처리, 요청한 리소스가 응답 본문(body)에 포함됩니다.
    - 201 CREATED : 요청이 성공적으로 처리, 새로운 리소스가 서버에 생성되었습니다.
    - 204 No Content : 요청이 성공적으로 처리되었으나, 응답 본문에 보낼 데이터가 없습니다.

- 3xx (Redirect) : 클라이언트 요청을 완료하기 위해 추가 동작인 리다이렉션을 합니다.
    - 301 Moved Permanently : 요청한 리소스가 영구적으로 새로운 위치로 이동되었습니다. 클라이언트는 새로운 URL을 사용합니다. (HTTP를 HTTPS로 변경할 경우)
    - 302 Found : 요청한 리소스가 일시적으로 다른 위치에 있습니다. 클라이언트는 원래 URL을 계속 사용합니다.

- 4xx (Client Error) : 클라이언트 요청에 오류가 있음을 나타냄
    - 400 Bad Request : 잘못된 문법으로 인해 서버가 이해하지 못합니다.
    - 401 Unauthorized : 요청한 리소스에 대한 인증이 필요합니다.
    - 403 Forbidden : 요청을 이해했지만, 권한이 없어 요청을 거부합니다.
    - 404 NotFound : 서버가 요청한 리소스를 찾을 수 없습니다.

- 5xx (Server Error) : 서버가 요청을 처리하는데 실패했음을 나타냄
    - 500 Internal Server Error : 서버에서 요청을 처리하는 동안 오류가 발생하였습니다.
    - 502 Bad Gateway : Gateway, Proxy Server가 상위 서버로부터 잘못된 응답을 받았습니다.
    - 503 Service Unavailable : 서버가 일시적으로 과부하 상태이거나 유지보수 중이어서 요청을 처리할 수 없습니다.
 
</div>
</details>

--- 
### HTTP Method에 대해 설명해보세요.

<details>
<summary>🔎 Answer</summary>
<div markdown="1">

HTTP Method에는 대표적으로 GET, POST, PUT, PATCH, DELETE 등이 존재합니다.

각 메서드마다 고유한 특징이 존재합니다.

- GET : 클라이언트가 서버로부터 리소스(데이터)를 조회하는데 사용
- POST : 데이터 추가, 등록
- PUT : 리소스 대체, 수정 / 해당 리소스가 없다면 새롭게 생성(POST와 동일)
- PATCH : 리소스의 부분적인 수정
- DELETE : 리소스 삭제
- HEAD : GET과 동일하나, HTTP Message의 Body를 제외하고 조회
- OPTIONS : 서버가 어떤 Method, Header, Content-Type을 제공하는지 파악!
- CONNECT : 대상 자원으로 식별되는 서버에 대한 요청

> 멱등성 : 여러번 요청을 해도 동일한 결과를 반환!

**GET**
- 리소스를 조회하는 메서드입니다. 
- 멱등성
- 쿼리스트링을 통해서 전달 -> 데이터 정보가 노출되므로 유의해서 사용해야 합니다.
- Body를 사용할 수 있으나, 호환되지 않는 경우가 존재하기 때문에 사용하지 않는 것을 권장합니다.
- 캐싱을 이용하여 조회 속도가 우수합니다.

**POST**
- 새로운 리소스를 생성(Create)할 때 사용합니다.
- 정상적으로 생성이 완료되었을 경우 Status Code로는 201(CREATED)를 사용합니다.
- 데이터를 HTTP Message Body에 담아 전달합니다.
    - application/json인 경우 Json 형식으로
    - application/x-www-form-urlencoded인 경우 key-value 형태로 전달됩니다.
- GET과 다르게 데이터가 외부로 노출되지 않아 보안상 이점이 있어 로그인 처리를 할 때 주로 사용합니다.
- 멱등성을 지니지 않아 여러 번 수행할 경우 같은 결과가 나오는 것을 보장하지 않습니다.

**PUT**
- 리소스를 완전히 대체하는 메서드입니다.
- 부분 수정이 불가능합니다. 
- 멱등성을 지닙니다.

**PATCH**
- PUT과 동일하게 리소스를 대체하지만, 부분 변경을 한다는 차이가 있습니다.
- 멱등성을 지니지 않습니다. -> 모호한듯?.. 

> [멱등성에서 본 PUT vs PATCH](https://oen-blog.tistory.com/211)

**DELETE**
- 리소스를 제거하는 역할을 합니다.
- 멱등성을 지닙니다.

</div>
</details>
