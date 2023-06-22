# Zabbix template for making http simple tests

This template uses a discovery to create "HTTP Agent" type items based on host macros.

Macro | Description | Format | Required | Default
| :---: | :---: | :---: | :---: | :---: |
${WEBX.URL} | URL to check | string | Yes | 
${WEBX.STATUS_CODES} | Status codes expected | list of codes and ranges ( 200-299 / 200,201,400-410) | No | 200-399
${WEBX.CONTENT} | Content that should be present | regex string | No | ""
${WEBX.NOCONTENT} | Content that should not be present | regex string | No | ""
${WEBX.INTERVAL} | Frequency of the HTTP test | time (30m / 1h / 1w) | No | 5m
${WEBX.TIMEOUT} | Timeout of the HTTP test | time (10s) | No | 15s

The template supports up to 12 tests to different URLs. To do this, macros must be added like this:

Check 1:
* ${WEB1.URL}
* ${WEB1.STATUS_CODES}
* ${WEB1.CONTENT}
* ${WEB1.NOCONTENT}
* ${WEB1.INTERVAL}
* ${WEB1.TIMEOUT}

Check 2:
* ${WEB2.URL}
* ${WEB2.STATUS_CODES}
* ${WEB2.CONTENT}
* ${WEB2.NOCONTENT}
* ${WEB2.INTERVAL}
* ${WEB2.TIMEOUT}

...

<img width="1046" alt="image" src="https://github.com/julenbadiola/zabbix_http_test_template/assets/33113693/076f93c0-5aac-42e1-a0ab-47bedf811a48">
