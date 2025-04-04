# modern-javascript
***
vscode의 liveServer 또는 xampp를 설치해서 간단하게 사용
***
### xampp를 사용할 경우
xampp는 홈디렉토리가 **c:/xampp/htdocs**로 기본 세팅이 되어 있기 때문에 **c:/xampp/htdocs** 폴더 하위에 __Desired-folder-name__ 폴더를 만들어서 사용하면 된다.

__Desired-folder-name__ 폴더를 Apache서버 홈디렉토리로 바꾸는 방법.
c:/xampp/htdocs/index.php 파일
```php
<?php
    if (!empty($_SERVER['HTTPS']) && ('on' == $_SERVER['HTTPS'])) {
        $uri = 'https://';
    } else {
        $uri = 'http://';
    }
    $uri .= $_SERVER['HTTP_HOST'];
    header('Location: '.$uri.'/Desired-folder-name/'); //여기서 변경
    exit;
?>
```
기본 포트는 80 포트를 사용한다.
웹 브라우저 접속시
http://localhost 입력