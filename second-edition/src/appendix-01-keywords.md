## Appendix A: Keywords (Phụ lục A: Từ khóa)

Những từ khóa bên dưới được dành riêng cho ngôn ngữ Rust và không thể được sử
dụng để định danh ví dụ như là tên của các hàm (functions), biến (variables),
tham số (parameters), thuộc tính của struct (struct fields), modules, crates,
hằng (constants), macros, giá trị tĩnh (static values), thuộc tính (attributes),
kiểu (types), traits hoặc lifetimes.

### Keywords Currently in Use
(Từ khóa đang được sử dụng)

* `as` - Phương pháp ép kiểu nguyên thủy, thay đổi kiểu của trait chứa phần tử
hoặc đổi tên của phẩn tử trong câu lệnh `use` và `extern crate`
* `break` - Thoát khỏi vòng lặp ngay lập tức
* `const` - Khai báo một hằng số
* `continue` - Bỏ qua các lệnh kế tiếp trong vòng lặp hiện tại và tiến đến lần
lặp kế tiếp
* `crate` - Liên kết đến một đơn vị biên soạn mở rộng hoặc một biến macro biểu
diễn một đơn vị biên soạn mà macro đó được định nghĩa. Được hiểu là việc khai
báo đến một file `.rs`
* `else` - Khi toàn bộ `if` và `if let` trong cùng cấu trúc điều khiển với từ
khóa else đều trả về False
* `enum` - Khai báo một enumeration
* `extern` - Dành cho liên kết ngoài đến một file `.rs`, một hàm hoặc một biến
không nằm cùng trong file `.rs` hiện tại
* `false` - Giá trị boolean false đại diện cho sai
* `fn` - Từ khóa mở đầu cho khai báo hàm
* `for` - Vòng lặp tuần tự theo một danh sách cho trước. Đồng thời cũng là một
phần của cú pháp triển khai trait
* `if` - Điều kiện rẽ nhánh
* `impl` - Triển khai của một trait block
* `in` - Một phần của cấu trúc lặp `for`
* `let` - Gán biến
* `loop` - Vòng lặp vô hạn
* `match` - Kiểm tra tính đúng đắn dựa trên một pattern
* `mod` - Khai báo module
* `move` - Tạo ra một closure lấy ownership của toàn bộ giá trị nó lấy được
* `mut` - Biểu thị tham chiếu, con trỏ và pattern bindings có tính khả biến
* `pub` - Biểu thị khả năng truy cập từ toàn bộ chương trình của thuộc tính
trong struct, blocks của `impl` và modules
* `ref` - Phép gán bởi tham chiếu
* `return` - Điểm trả về của hàm
* `Self` - Kiểu ánh xạ dành cho kiểu đã triển khai một trait
* `self` - Đại diện cho phương thức hiện tại hoặc module
* `static` - Biến toàn cục tồn tại từ khi chương trình sinh ra đến khi chương
trình bị hệ điều hành thu hồi/kết thúc
* `struct` - Định nghĩa một structure
* `super` - Đại diện cho module mà module hiện tại kế thừa
* `trait` - Định nghĩa trait
* `true` - Giá trị boolean true đại diện cho việc đúng, thành công
* `type` - Định nghĩa type alias và associated type
* `unsafe` - Biểu thị một đoạn code, hàm, trait hoặc triển khai không an toàn
* `use` - Import kí hiệu vào trong phần code hiện tại
* `where` - Định nghĩa một kiểu ràng buộc
* `while` - Vòng lặp không biết trước số lần lặp

### Keywords Reserved for Future Use
(Từ khóa có thể sẽ dùng trong tương lai)

Những từ khóa không có bất kì ràng buộc nào nhưng đang được dự định sử dụng
trong tương lai bởi Rust. Cẩn trọng khi dùng để tránh bị lỗi với các phiên bản
kế tiếp

* `abstract`
* `alignof`
* `become`
* `box`
* `do`
* `final`
* `macro`
* `offsetof`
* `override`
* `priv`
* `proc`
* `pure`
* `sizeof`
* `typeof`
* `unsized`
* `virtual`
* `yield`
