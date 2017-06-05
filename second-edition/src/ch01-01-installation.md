## Cài đặt
TL;DR
> Phần này hướng dẫn dành cho người mới bắt đầu, nên bài viết sẽ có những phần 
không cần thiết, nếu muốn nhanh bạn có thể vào trang [rustup] để cài đặt Rust.

[rustup]: https://www.rustup.rs/

Bước đầu tiên để dùng được Rust là bạn phải cài đặt nó. Bạn sẽ cần phải có
internet để run command line, cũng như download Rust.

Phần lớn chúng ta sẽ làm việc với terminal, và tất cả các dòng đều bắt đầu bằng 
`$`. Bạn không cần phải gõ ký tự `$`. Bạn sẽ thấy những ví dụ và các ứng dụng
web sẽ theo một quy tắc: `$` áp dụng cho người dùng bình thường (user regular), 
và `#` áp dụng cho người dùng là quản trị viên (administrator). Những dòng không
bắt đầu với `$` thông thường là kết quả của dòng lệnh (commands) đã được thực
hiện.

### Cài đặt Rust trên Linux hoặc Mac

Nếu bạn đang dùng Linux hoặc Mac, tất cả đều bạn cần làm là mở terminal và gõ
dòng sau:

```text
$ curl https://sh.rustup.rs -sSf | sh
```

Dòng lệnh trên sẽ tải về 1 script và tiến hành quá trình cài đặt. Sẽ có một thông
báo để bạn nhập password. Nếu quá trình cài đặt không có lỗi, bạn sẽ thấy dòng
sau:

```text
Rust is installed now. Great!
```

Đương nhiên, nếu bạn không chấp nhận lệnh `curl | sh`, bạn có thể download, và 
chạy script như cách bạn muốn.

### Cài đặt trên Windows

Trên Windows, go to [https://rustup.rs](https://rustup.rs/)<!-- ignore --> and
follow the instructions to download rustup-init.exe. Run that and follow the
rest of the instructions it gives you.

The rest of the Windows-specific commands in the book will assume that you are
using `cmd` as your shell. If you use a different shell, you may be able to run
the same commands that Linux and Mac users do. If neither work, consult the
documentation for the shell you are using.

### Custom installations

If you have reasons for preferring not to use rustup.rs, please see [the Rust
installation page](https://www.rust-lang.org/install.html) for other options.

### Updating

Once you have Rust installed, updating to the latest version is easy.
From your shell, run the update script:

```text
$ rustup update
```

### Uninstalling

Uninstalling Rust is as easy as installing it. From your shell, run
the uninstall script:

```text
$ rustup self uninstall
```

### Troubleshooting

If you've got Rust installed, you can open up a shell, and type this:

```text
$ rustc --version
```

You should see the version number, commit hash, and commit date in a format
similar to this for the latest stable version at the time you install:

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

If you see this, Rust has been installed successfully!
Congrats!

If you don't and you're on Windows, check that Rust is in your `%PATH%` system
variable.

If it still isn't working, there are a number of places where you can get help.
The easiest is [the #rust IRC channel on irc.mozilla.org][irc]<!-- ignore -->,
which you can access through [Mibbit][mibbit]. Go to that address, and you'll
be chatting with other Rustaceans (a silly nickname we call ourselves) who can
help you out. Other great resources include [the Users forum][users] and
[Stack Overflow][stackoverflow].

[irc]: irc://irc.mozilla.org/#rust
[mibbit]: http://chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust
[users]: https://users.rust-lang.org/
[stackoverflow]: http://stackoverflow.com/questions/tagged/rust

### Local documentation

The installer also includes a copy of the documentation locally, so you can
read it offline. Run `rustup doc` to open the local documentation in your
browser.

Any time there's a type or function provided by the standard library and you're
not sure what it does, use the API documentation to find out!
