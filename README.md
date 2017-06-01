# Ngôn ngữ lập trình Rust (The Rust Programming Language)

## Yêu cầu

Bạn phải cài đặt [mdBook] >= v0.0.13. Cài đặt [mdBook] rất đơn giản:

[mdBook]: https://github.com/azerupi/mdBook

```bash
$ cargo install mdbook
```

## Building

Bạn cd vào 1 trong 2 phiên bản của sách, sau đó chạy lênh:

```bash
$ mdbook build
```

Output sẽ nằm trong thư mục `book`.

_Firefox:_
```bash
$ firefox book/index.html                       # Linux
$ open -a "Firefox" book/index.html             # OS X
$ Start-Process "firefox.exe" .\book\index.html # Windows (PowerShell)
$ start firefox.exe .\book\index.html           # Windows (Cmd)
```

_Chrome:_
```bash
$ google-chrome book/index.html                 # Linux
$ open -a "Google Chrome" book/index.html       # OS X
$ Start-Process "chrome.exe" .\book\index.html  # Windows (PowerShell)
$ start chrome.exe .\book\index.html            # Windows (Cmd)
```
