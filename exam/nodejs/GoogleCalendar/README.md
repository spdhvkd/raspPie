### 노드에서 Calendar-API 이용하기

0. 노드 패키지 모듈 설치하기
        npm install googleapis --saved
        npm install  node-google-calendar --save
1. 사용자 토큰 발급 받기
    1. 계정에 서 OAuth 발급받기 탭으로 넘어가서 다운로드 받는다. 현재 테스트 할 노드 프로그램은 `웹서버`가 아니니 셀렉트박스 중 기타로 선택을 해서 다운로드 받도록 한다.
![](http://img1.daumcdn.net/thumb/R1920x0/?fname=http%3A%2F%2Fcfile25.uf.tistory.com%2Fimage%2F2319DD4758F0BC0B2C4BAD)
    2.  client_secret_xxxxxxxxxxxxxxxx.json과 같은 형식으로 파일을 다운 받을 수 있게 되는데, 뒤쪽 문자열 `xxxx...`을 제거하고 `client_secret.json`으로 수정한다.
    3. 웹 서버에서 키(json)를 호출하는 경우에는
              var clientSecret = credentials.installed.client_secret;
              var clientId = credentials.installed.client_id;
              var redirectUrl = credentials.installed.redirect_uris[0];
        * credentials.installed부분을 credentials.web으로 변경해주라고 하는데, 확인해 보지는 않았으니 참고
2. 마지막으로 `quickstart.js`가 있는 경로로 돌아와, node quickstart.js를 실행해주면 url을 제공해주는데 해당 url에 들어가보면 키 값을 제공 받을 수 있게 된다.
3. 제공받은 키값을 입력해주게 되면 종료
    1. 이 작업은 최초 1회만 요청이 들어가게된다.


*참고자료

https://developers.google.com/google-apps/calendar/quickstart/nodejs#step_1_turn_on_the_api_name

http://handcoding.tistory.com/20
