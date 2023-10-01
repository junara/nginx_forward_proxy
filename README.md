# nginx_forward_proxy

## Description
[reiz/nginx_proxy Docker image](https://hub.docker.com/r/reiz/nginx_proxy)を使って、`localhost:8888` でプロキシサーバーを起動する。

## Usage
### プロキシサーバー起動

```zsh
docker-compose up -d
```

### プロキシサーバー停止

```zsh
docker-compose down
```

### 動作確認

#### http

```zsh
$ curl --proxy http://localhost:8888 http://abehiroshi.la.coocan.jp/
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=Shift_JIS">
<meta name="GENERATOR" content="JustSystems Homepage Builder Version 20.0.6.0 for Windows">
<meta http-equiv="Content-Style-Type" content="text/css">
<title>???????̃z?[???y?[?W</title>
</head>
<frameset cols=18,82>
  <frame src="menu.htm" marginheight="0" marginwidth="0" scrolling="auto" name="left">
  <frame src="top.htm" marginheight="0" marginwidth="0" scrolling="auto" name="right">
  <noframes>
  <body></body>
  </noframes>
</frameset>
</html>%                                                                                                                   
```

#### https

```zsh
$ curl --proxy http://localhost:8888 https://example.com/
<!doctype html>
<html>
<head>
    <title>Example Domain</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <style type="text/css">
    body {
        background-color: #f0f0f2;
        margin: 0;
        padding: 0;
        font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
        
    }
    div {
        width: 600px;
        margin: 5em auto;
        padding: 2em;
        background-color: #fdfdff;
        border-radius: 0.5em;
        box-shadow: 2px 3px 7px 2px rgba(0,0,0,0.02);
    }
    a:link, a:visited {
        color: #38488f;
        text-decoration: none;
    }
    @media (max-width: 700px) {
        div {
            margin: 0 auto;
            width: auto;
        }
    }
    </style>    
</head>

<body>
<div>
    <h1>Example Domain</h1>
    <p>This domain is for use in illustrative examples in documents. You may use this
    domain in literature without prior coordination or asking for permission.</p>
    <p><a href="https://www.iana.org/domains/example">More information...</a></p>
</div>
</body>
</html>

```

#### With Google Chrome
* proxy server を指定して起動する
  * https://www.chromium.org/developers/design-documents/network-settings/
##### macOS

```
 /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --proxy-server="http://localhost:8888"
```

## 参考
* [reiz/nginx_proxy - Docker Image | Docker Hub](https://hub.docker.com/r/reiz/nginx_proxy)
* [HTTPS通信をNginxでフォワードプロキシ - まったり技術ブログ](https://blog.motikan2010.com/entry/2020/03/18/HTTPS%E9%80%9A%E4%BF%A1%E3%82%92Nginx%E3%81%A7%E3%83%95%E3%82%A9%E3%83%AF%E3%83%BC%E3%83%89%E3%83%97%E3%83%AD%E3%82%AD%E3%82%B7)
