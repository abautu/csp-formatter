# csp-formatter
A simple HTML/JS formatter for Content Security Policy directives.

## Test it!

Open [Content Security Policy formatter](https://rawcdn.githack.com/abautu/csp-formatter/main/index.html) in your browser.

## What it does?

This simple tool tool allows you to format [CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) directives in a way that are simple to read and review by humans.
The directives are formated one per line, sorted in alphabetical order (with some exceptions for non-value, default-src, and report-uri directives) and their values are also sorted in alphabetical order, with duplicates removed.

So this tool turns this:
```
default-src https:; script-src 'self' 'unsafe-inline' 'unsafe-eval'; connect-src 'self' https://example.com/duplicated https://example.com/duplicated https://example.com/duplicated; font-src https: data:; style-src https: 'unsafe-inline'; img-src https: data:; report-uri https://example.com/callback;
```
into this:
```
default-src
  https:
;
connect-src
  'self'
  https://example.com/duplicated
;
font-src
  data:
  https:
;
img-src
  data:
  https:
;
script-src
  'self'
  'unsafe-eval'
  'unsafe-inline'
;
style-src
  'unsafe-inline'
  https:
;
report-uri
  https://example.com/callback
;
```
