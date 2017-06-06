## Cài đặt
TL;DR
> Phần này hướng dẫn dành cho người mới bắt đầu, nên bài viết sẽ có những phần 
không cần thiết, nếu muốn nhanh bạn có thể vào trang [rustup] để cài đặt Rust.

[rustup]: https://www.rustup.rs/

Bước đầu tiên để dùng được Rust là bạn phải cài đặt nó. Bạn sẽ cần phải có
internet để run command line, cũng như download Rust.

Phần lớn chúng ta sẽ làm việc với terminal, và tất cả các dòng đều bắt đầu bằng 
`$`. Bạn không cần phải gõ ký tự `$`. Bạn sẽ thấy những ví dụ và các ứng dụng
web sẽ theo một quy tắc: `$` áp dụng cho người dùng bình thường (regular user), 
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

Trên Windows, truy cập [https://rustup.rs](https://rustup.rs/)<!-- ignore --> và
làm theo các hướng dẫn để tải về (download) rustup-init.exe. Chạy nó và làm theo
những hướng dẫn bạn sẽ cài đặt được Rust.

Đối với Windows, thì những hướng dẫn dựa trên `cmd` shell. Nếu bạn dùng shell khác
, bạn phải chạy những lệnh tương tự như trên Linux và Mac. Nếu quá trình của bạn
hoạt động tốt, đừng quên chia sẽ cách mà bạn làm với chúng tôi.

### Cách cài đặt khác

Nếu có vài lý do nào đó bạn không thích cách cài đặt của rustup.rs, bạn có thể
tham khảo [the Rust installation page](https://www.rust-lang.org/install.html)
để biết thêm các cách cài đặt khác.

### Cập nhật

Khi bạn đã cài đặt Rust, công việc cập nhật phiên bản mới nhất rất đơn giản.
Từ termial, chạy lệnh cập nhật:

```text
$ rustup update
```

### Gỡ cài đặt Rust (Uninstalling)

Uninstalling Rust rất là đơn giản như cách cài đặt nó. Từ termial, Uninstalling
bằng cách chạy lệnh:

```text
$ rustup self uninstall
```

### Xử lý sự cố (Troubleshooting)

Nếu bạn đã cài Rust trước đó, bạn có thể open terminal, và gõ lệnh:

```text
$ rustc --version
```

Bạn phải thấy số phiên bản, mã băm của commit, và ngày commit như trong định dạng
dưới đây (định dạng này áp dùng cho phiên bản ổn định cuối cùng bạn cài đặt):

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

Nếu bạn thấy như trên, Rust đã được cài đặt một cách thành công!
Xin chúc mừng!

Nếu bạn không thành công và bạn dùng Windows, kiếm tra Rust đã tồn tại trong
biến hệ điều hành `%PATH%`.

Nếu nó vẫn không hoạt động, có rất nhiều nơi có thể giúp bạn.
Cách đơn giản nhất là vào [the #rust IRC channel on irc.mozilla.org][irc]<!-- ignore -->,
thông qua [Mibbit][mibbit]. Truy cập địa chỉ đó, và bạn sẽ thảo luận với các 
Rustaceans (một biệt danh tự đặt cho ai học Rust) những người có thể cùng bạn
tìm ra giải pháp. Và một nơi khác không kém phần tuyệt vời là [Diễn đàn][users] and
[Stack Overflow][stackoverflow].

[irc]: irc://irc.mozilla.org/#rust
[mibbit]: http://chat.mibbit.com/?server=irc.mozilla.org&channel=%23rust
[users]: https://users.rust-lang.org/
[stackoverflow]: http://stackoverflow.com/questions/tagged/rust

### Tài liệu offline

Công cụ cài đặt đã bao gồm phần tài liệu trong đó, nên bạn có thể tham khảo khi
offline. Chạy lệnh `rustup doc` để mở tài liệu bằng trình duyệt hiện tại.

Bất cứ lúc nào khi bạn dùng một hàm mà không chắc nó là gì, bạn có thể tham khảo
trong tài liệu này.