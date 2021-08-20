# java-net-post
GET と POST を同時に行う

## post-test.php
```php
<?php
header( "Access-Control-Allow-Origin: *" );
header("Content-Type: application/json; charset=utf-8");

$headers = apache_request_headers();

$result = new stdClass();

$result->method = $_SERVER["REQUEST_METHOD"];
$result->get = $_GET;
$result->post = $_POST;
$result->{"response"} = apache_response_headers();
$result->{"request"} = $headers;

print json_encode( $result, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE | JSON_UNESCAPED_SLASHES );

?>
```
