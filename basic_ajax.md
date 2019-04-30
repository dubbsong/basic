## AJAX

###### Asynchronous JavaScript and XML | 비동기 통신

<br>

1. `A`synchronous `J`avaScript `a`nd `X`ML의 약자이다.
2. 웹 페이지 전체를 다시 로딩하지 않고, `일부분만 갱신`할 수 있게 한다.
3. 말 그대로, JS 및 XML을 이용한 `비동기적 정보 교환 기법`이다.
4. XML을 명시했지만, 주로 `JSON 데이터`를 다룬다.
5. 실제 기술과 용어 간 차이가 크지만, 고유명사로 취급한다.
6. 웹 페이지가 로딩된 후, 서버로 데이터 요청을 보낼 수 있다.
7. 웹 페이지가 로딩된 후, 서버로부터 데이터를 받을 수 있다.
8. 빠르게 첫 화면을 보여줄 필요가 있는 경우, 최소 두 번의 데이터 요청을 해야 한다는 문제가 있다.
9. JS를 해석하지 못하는 검색 엔진에서는 내용이 검색되지 않는다.
10. AJAX는 양방향 기술이 아니므로, 완전한 실시간 통신을 지원하기 위해 `웹 소켓`이라는 새로운 기술이 구현되었다.

<br>

#### How Works

1. 웹 페이지에서 사용자에 의한 `요청 이벤트가 발생`한다.
2. JS에 의해 `XMLHttpRequest 객체`가 생성된다.
3. XMLHttpRequest 객체가 서버에 요청을 보낸다.
   - 서버의 응답을 기다릴 필요 없이, 다른 작업을 처리할 수 있다.
4. 서버가 AJAX 요청을 처리한다.
5. 서버가 웹 페이지에 응답을 보낸다.
   - HTML, XML, JSON 형태의 데이터
6. 서버로부터 전달받은 응답을 JS가 읽는다.
7. 웹 페이지의 일부분만 다시 로딩되어 표시된다.

<br>

#### For example:

- Pure JS

```js
var request = new XMLHttpRequest();
request.open("GET", "/examples/ajax_data.php");
request.onreadystatechange = function() {
  if (request.readyState === 4 && request.status === 200) {
    document.getElementById("content").innerHTML = request.responseText;
  } else {
    console.log('error: ' + request.status);
  }
}
```

<br>

- jQuery

```js
$.ajax({
  url: "/examples/ajax_data.php",
  method: "GET",
  dataType: "text",
  success: function(data) {
    $("#content").html(data);
  }
})
```

<br> 