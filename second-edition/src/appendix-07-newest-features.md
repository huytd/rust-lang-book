# Appendix G - Newest Features (Phụ lục G: Chức năng mới nhất)

Phần phụ lục này đưa ra danh sách cập nhật về các chức năng mới xuất hiện sau
khi nội dung chính của sách được hoàn thành.


## Field init shorthand
(Thu gọn thuộc tính của giá trị khởi tạo)

Chúng ta có thể khởi tạo giá trị một cấu trúc dữ liệu (struct, enum, union)
thông qua định danh thuộc tính bằng cách việc viết `fieldname` như một cách
viết tắt cho `fieldname: fieldname`. Nó cho phép thu gọn cú pháp cho việc khởi
tạo và không gây dư thừa:

```rust
#[derive(Debug)]
struct Person {
    name: String,
    age: u8,
}

fn main() {
    let name = String::from("Peter");
    let age = 27;

    // Using full syntax:
    let peter = Person { name: name, age: age };

    let name = String::from("Portia");
    let age = 27;

    // Using field init shorthand:
    let portia = Person { name, age };
    
    println!("{:?}", portia);
}
```
