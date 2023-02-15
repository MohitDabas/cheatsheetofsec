# ffuf

% ffuf

## ffuf Directory Discovery
#web/recon ##ffuf
```
ffuf -w /path/to/wordlist -u https://target/FUZZ

```

## ffuf Adding classical header (some WAF bypass)
#web/recon ##ffuf
```
ffuf -c -w "/opt/host/main.txt:FILE" -H "X-Originating-IP: 127.0.0.1, X-Forwarded-For: 127.0.0.1, X-Remote-IP: 127.0.0.1, X-Remote-Addr: 127.0.0.1, X-Client-IP: 127.0.0.1" -fs 5682,0 -u https://target/FUZZ
```

## ffuf match all responses but filter out those with content-size 42
#web/recon ##ffuf
```
ffuf -w wordlist.txt -u https://example.org/FUZZ -mc all -fs 42 -c -v
```

## Fuzz Host-header, match HTTP 200 responses.
#web/recon ##ffuf
```
ffuf -w hosts.txt -u https://example.org/ -H "Host: FUZZ" -mc 200
```

## Virtual host discovery (without DNS records)
#web/recon ##ffuf
```
ffuf -w /path/to/vhost/wordlist -u https://target -H "Host: FUZZ" -fs 4242
```

## Playing with threads and wait
#web/recon ##ffuf
```
ffuf -u https://target/FUZZ -w /home/mdayber/Documents/Tools/Wordlists/WebContent_Discovery/content_discovery_4500.txt -c -p 0.1 -t 10
```

## GET parameter fuzzing if the param is known (fuzzing values) and filtering 401
#web/recon ##ffuf
```
ffuf -w /path/to/values.txt -u https://target/script.php?valid_name=FUZZ -fc 401
```

## POST parameter fuzzing
#web/recon ##ffuf
```
ffuf -w /path/to/postdata.txt -X POST -d "username=admin\&password=FUZZ" -u https://target/login.php -fc 401
```

## Fuzz POST JSON data. Match all responses not containing text "error".
#web/recon ##ffuf
```
ffuf -w entries.txt -u https://example.org/ -X POST -H "Content-Type: application/json" -d '{"name": "FUZZ", "anotherkey": "anothervalue"}' -fr "error" 
```

## specific extensions with the word-list’s entries, the -e flag can be used.
#web/recon ##ffuf
```
ffuf -w wordlist.txt -u http://website.com/FUZZ -e .aspx,.html,.php,.txt
```

##  ffuf match based on amount of words.
#web/recon ##ffuf
```
ffuf -w <path-wordlist> -u https://test-url/FUZZ -fw <amount-of-words>
```

## ffuf match on regex.
#web/recon ##ffuf
```
ffuf -w <path-wordlist> -u https://test-url/FUZZ -fr <regex-pattern>
```

## ffuf fuzz substring
#web/recon ##ffuf
```ffuf -w <path-wordlist> -u https://test-url/testFUZZ```

## ffuf fuzz with muliple files
#web/recon ##ffuf
```
ffuf -u https://Wordlist2/Wordlist1 -w <path-wordlist>:Wordlist1 <domain-list>:Wordlist2
```

## fuff introduce delay
#web/recon ##ffuf
```
ffuf -u http://test-url/FUZZ/ -w <path-wordlist> -p 1
```

## fuff introduce delay
#web/recon ##ffuf
```
ffuf -u http://test-url/FUZZ/ -w <path-wordlist> -t 1000
```

## ffuf save output in html
#web/recon ##ffuf
```
ffuf -u https://test-url/FUZZ/ -w <path-wordlist> -o output.html -of html
```

## ffuf fuzz multiple locations
#web/recon ##ffuf
```
ffuf -u https://FUZZDOMAIN/FUZZDIR -w ./wordlist.txt:FUZZDIR,./domains.txt:FUZZDOMAIN
```

## ffuf replay proxy
#web/recon ##ffuf
```
ffuf -u http://codingo.io/FUZZ -w ./wordlist -replay-proxy http://127.0.0.1:8888
```

## ffuf importing burp or HTTP request
#web/recon ##ffuf
```
ffuf -request /tmp/request.txt -w ./wordlist.txt
```
