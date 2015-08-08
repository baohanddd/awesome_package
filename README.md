PHP useful libraries 
===================

There are some useful libraries of **PHP5**, I collected and put them in here.

----------


HTTP
-------------

#### [Guzzle][1]
Guzzle is a PHP HTTP client that makes it easy to send HTTP requests and trivial to integrate with web services.

```
$client = new GuzzleHttp\Client();
$res = $client->get('https://api.github.com/user', ['auth' =>  ['user', 'pass']]);
echo $res->getStatusCode();
// "200"
echo $res->getHeader('content-type');
// 'application/json; charset=utf8'
echo $res->getBody();
// {"type":"User"...'

// Send an asynchronous request.
$request = new \GuzzleHttp\Psr7\Request('GET', 'http://httpbin.org');
$promise = $client->sendAsync($request)->then(function ($response) {
    echo 'I completed! ' . $response->getBody();
});
$promise->wait();
```



  [1]: http://guzzle.readthedocs.org/en/latest/ "guzzle"
