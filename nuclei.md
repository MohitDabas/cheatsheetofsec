# nulcei Vulnerability Scanner

% Nulcei Vulnerability Scanner

##  nuclei run scan for simple target

##web/scan Nuclei

```
nuclei -u https://my.target.site

```

##  nuclei run scan for simple target with template

##web/scan Nuclei

```
nuclei -u https://my.target.site -t /path/to/template.yaml

```

## nuclei run scan for simple target with template and save output in csv

##web/scan Nuclei

```
nuclei -u https://my.target.site -t /path/to/template.yaml -o output.csv -of csv

```
## nuclei run scan on non standard port

##web/scan Nuclei

```
nuclei -u https://my.target.site:8443 -t /path/to/template.yaml

```

## nuclei run scan on multiple targets

##web/scan Nuclei

```
nuclei -l targets.txt -t /path/to/template.yaml

```

## nuclei run scan with automatic selection of template

##web/scan Nuclei

```
nuclei -u https://my.target.site  -as

```

## nuclei run scan with new templstes

##web/scan Nuclei

```
nuclei -u https://my.target.site   -nt

```

## nuclei run scan with specific folder

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder

```
## nuclei run scan by tags

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -tags cve

```
## nuclei run scan by severity

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -severity critical

```

## nuclei run scan with rate limit

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -rate-limit 100

```
## nuclei run scan with timeout

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -timeout 10

```
## nuclei run scan with proxy

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -proxy http://
    
```

## nuclei run scan with retries

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -retries 3

```

## nuclei resume scan

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -resume

```

## nuclei run scan with cookies or headers

##web/scan Nuclei

```

nuclei -u https://my.target.site   -t /path/to/folder -H "Cookie: session=1234"

```

## nuclei basic custom template

##web/scan Nuclei

```
id: my-custom-template

info:
  name: My Custom Template

requests:

    - method: GET
        path:
        - "{{BaseURL}}/admin"
        matchers-condition: and
        matchers:
        - type: status
            status:
            - 200
        - type: word
            words:
            - "admin"
            - "login"
            - "password"
            part: body
    
```

## nuclei fuzz request

##web/scan Nuclei

```
 - raw:
      - |
        GET / HTTP/1.1
        Host: {{Hostname}}
        X-{{fuzz}}-debug: 1

	redirects: true
	attack: batteringram
	payloads:
	  fuzz: /var/tmp/fuzz.txt

```

## nuclei validate template

##web/scan Nuclei

```
nuclei -validate /path/to/template.yaml

```

## nuclei verbose mode

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -v

```

## nuclei run scan with debug mode

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -debug

```

## nuclei run scan with proxy

##web/scan Nuclei

```
nuclei -u https://my.target.site   -t /path/to/folder -proxy http://

```

## nuclei complete guide url

##web/scan Nuclei

```
https://blog.projectdiscovery.io/ultimate-nuclei-guide/

```



