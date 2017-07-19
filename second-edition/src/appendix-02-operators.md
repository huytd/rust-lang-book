## Appendix B: Operators (Phụ lục B: Toán tử)

### Unary operator expressions
(Biểu thức của toán tử một ngôi)

Rust định nghĩa các toán tử một ngôi sau. Tất cả đều được viết như các toán tử
tiền tố, nằm trước biểu thức mà chúng áp dụng.

* `-`
  : Phủ định. Dành cho kiểu số nguyên có dấu để biểu diễn giá trị nhỏ hơn 0
    hoặc một kiểu số thực có hỗ trợ giá trị nhỏ hơn 0. Báo lỗi sẽ xuất hiện khi
    áp dụng phủ định vào một kiểu không dấu. Ví dụ như compiler sẽ báo lỗi với
    đoạn code `-1u32`.
* `*`
  : Dereference. Khi áp dụng cho một biến dạng con trỏ, nó
    biểu thị vị trí mà con trỏ đó trỏ tới. Với các con trỏ đang trỏ tới một vị
    trí khả biến, giá trị kết quả có thể được gán vào. Với các kiểu không thuộc
    dạng con trỏ, nó sẽ gọi đến phương thức `deref` của trait `std::ops::Deref`
    hoặc phương thức `deref_mut` của trait `std::ops::DerefMut` (Trong trường
    hợp được triển khai bởi một kiểu hoặc được yêu cầu bởi  một biểu thức bên
    ngoài thì dereference có thể bị thay đổi), và sinh ra giá trị cho `&` or
    `&mut` borrowed pointer trả về từ phương thức overload.
* `!`
  : Điều kiện phủ định. Trong kiểu boolean, nó tráo đổi giữa hai giá trị `true`
    và `false`. Trong kiểu số nguyên, nó đảo dấu của giá trị bằng cách triển
    khai two's complement representation của giá trị đó.
* `&` and `&mut`
  : Borrowing. Khi áp dụng vào một giá trị, toán tử này sinh ra một tham chiếu
    (con trỏ) đến giá trị đó. Giá trị cũng đồng thời được đưa vào trạng thái
    borrowed trong toàn bộ thời gian tham chiếu. Với shared borrow (`&`),
    borrowing ngụ ý ràng giá trị có thể không được khả chuyển nhưng có thể đọc
    được và chia sẻ. Với mutable borrow (`&mut`), giá trị có thể thay đổi được
    nhưng bù lại là không thể được truy cập từ bất kì cách nào cho đến khi
    borrow hết hạn.

### Binary operator expressions
(Biểu thức toán tử nhị phân)

Biểu thức toán tử nhị phân được cung cấp theo thứ tự dưới đây

#### Arithmetic operators
(Toán tử số học)

Một biểu thức số học nhị phân và một cú pháp ngắn gọn để gọi đến các traits
dựng sẵn, được định nghĩa trong module `std::ops` cả thư viện `std`. Nó có
nghĩa là biểu thức số học có thể bị ghi đè được các kiểu được định nghĩa thêm
vào thời điểm viết code. Ý nghĩa mặc định của các toán tử này được đưa ra dưới
đây.

* `+`
  : Phép cộng.
    Gọi đến phương thức `add` của trait `std::ops::Add`.
* `-`
  : Phép trừ.
    Gọi đến phương thức `sub` của trait `std::ops::Sub`.
* `*`
  : Phép chia.
    Gọi đến phương thức `mul` của trait `std::ops::Mul`.
* `/`
  : Chia lấy nguyên.
    Gọi đến phương thức `div` của trait `std::ops::Div`.
* `%`
  : Chia lấy phần dư.
    Gọi đến phương thức `rem` của trait `std::ops::Rem`.

Lưu ý rằng Rust không có toán tử dựng sẵn cho phép lũy thừa. Xem thêm phương
thức `pow` trong danh sách numeric types.

#### Bitwise operators
(Toán tử bitwise)

Cũng giống như các toán tử số học, các toán tử bitwise là dạng cú pháp ngắn
gọn để gọi đến các phương thức dựng sẵn. Nó có nghĩa là toán tử bitwire cũng
có thể bị ghi đè bởi các kiểu mà người dùng định nghĩa sau này. Ý nghĩa mặc
định của các toán tử này được cung cấp dưới đây. Các bitwise `&`, `|` và `^`
dùng để áp dụng cho các toán tử boolean được sử dụng giống như thể hiện của
các toán tử logic `&&`, `||` and `!=` dưới dạng non-lazy fashion (mục kế).

* `&`
  : Bitwise AND.
    Gọi đến phương thức `bitand` của trait `std::ops::BitAnd`.
* `|`
  : Bitwise inclusive OR.
    Gọi đến phương thức `bitor` của trait `std::ops::BitOr`.
* `^`
  : Bitwise exclusive OR.
    Gọi đến phương thức `bitxor` của trait `std::ops::BitXor`.
* `<<`
  : Left shift.
    Gọi đến phương thức `shl` của trait `std::ops::Shl`.
* `>>`
  : Right shift (arithmetic).
    Gọi đến phương thức `shr` của trait `std::ops::Shr`.

#### Lazy boolean operators
(Toán tử boolean dạng lazy)

Toán tử `||` và `&&` cũng có thể được áp dụng vào tính toán kiểu boolean. Toán
tử `||` biểu thị cho logic 'or', và toán tử `&&` biểu thị cho logic 'and'.
Chúng có sự khác biệt với `|` và `&` ở điểm là phần toán hạng phía bên phải sẽ
chỉ được tính toán khi mà toán hạng phía bên trái không thực sự đại diện cho
ngữ nghĩa của biểu thức. Nghĩa là , `||` chỉ tính đến toán hạng bên phải của
nó khi mà toán hạng phía bên trái là false. Đơn giản là trong biểu thức 'or',
chỉ cần một toán hạng là true thì toàn bộ biểu thức cũng là true. Điều này
tương tự với toán hạng `&&`.

#### Comparison operators
(Toán tử so sánh)

Toán tử so sánh cũng giống như toán tử toán học va toán tử bitsire, là những
traint được dựng sẵn trong Rust.

* `==`
  : Bằng.
    Gọi đến phương thức `eq` của trait `std::cmp::PartialEq`.
* `!=`
  : Không bằng.
    Gọi đến phương thức `ne` của trait `std::cmp::PartialEq`.
* `<`
  : Nhỏ hơn.
    Gọi đến phương thức `lt` của trait `std::cmp::PartialOrd`.
* `>`
  : Lớn hơn.
    Gọi đến phương thức `gt` của trait `std::cmp::PartialOrd`.
* `<=`
  : Nhỏ hơn hoặc bằng.
    Gọi đến phương thức `le` của trait `std::cmp::PartialOrd`.
* `>=`
  : Lớn hơn hoặc bằng.
    Gọi đến phương thức `ge` của trait `std::cmp::PartialOrd`.

#### Type cast expressions
(Biểu thức ép kiểu)

Một biểu thức ép kiểu được biểu thị dưới toán tử nhị phân `as`.

Thực thi một biểu thức `as` sẽ chuyển đổi giá trị của toán hạng phía bên trái thành một kiểu dự liệu mới được mô tả ở phía bên phải.

Ví dụ của một biểu thức `as`:

```rust
# fn sum(values: &[f64]) -> f64 { 0.0 }
# fn len(values: &[f64]) -> i32 { 0 }

fn average(values: &[f64]) -> f64 {
    let sum: f64 = sum(values);
    let size: f64 = len(values) as f64;
    sum / size
}
```

Một vài cú pháp phải thông qua toán tử `as` để được thực thì thì cũng được ép
kiểu ngầm từ điểm sử dụng trong chương trình ví dụ như tham số truyền vào hàm
hoặc là gán dữ nhiều thông qua từ khóa `let` được ép kiểu tự động thành kiểu
tương ứng. Các phương thức chuyển đổi ngầm chỉ nên được giới hạn với các chuyển
đổi vô hại không làm mất thông tin hoặc không gây ra những phản ứng phụ bất lợi
trong chương trình. Ví dụ như khi ép từ kiểu lớn hơn về kiểu nhỏ hơn, dữ liệu
có thể bị mất mát do kiểu nhỏ hơn không thể biểu thị được đầy đủ giá trị như
kiểu lớn hơn.

#### Assignment expressions
(Biểu thức gán)

Một *biểu thức gán* bao gồm một biểu mẫu được theo sau bởi dấu bằng (`=`) và
một biểu thức.

Thực thi một biểu thức gán là việc sao chép hoặc chuyển giá trị từ phía bên
phải qua phía bên trái.

```
# let mut x = 0;
# let y = 0;
x = y;
```

#### Compound assignment expressions
(Biểu thức gán kết hợp)

Các toán tử `+`, `-`, `*`, `/`, `%`, `&`, `|`, `^`, `<<`, and `>>` có thể được
kết hợp với toán tử `=`. Biểu thức `lval OP= val` thì được tính toán thành
`lval = lval OP val`. Ví dụ, `x = x + 1` có thể được viết là `x += 1`.

Mỗi một biểu thứ thì luôn luôn phải có chung một kiểu dữ liệu.

#### Operator precedence
(Thứ tự ưu tiên toán tử)

Thứ tự ưu tiên của các toán tử nhị phân trong Rust được sắp xếp theo thư tự ở
phía dưới từ cao đến thấp:

```text
as :
* / %
+ -
<< >>
&
^
|
== != < > <= >=
&&
||
.. ...
<-
=
```

Toán tử trong cùng một độ ưu tiên sẽ được tính toán từ bên trái qua bên phải.
Operators at the same precedence level are evaluated left-to-right. Toán tử một
ngôi thì có cùng một cấp độ và được ưu tiên cao nhất.
