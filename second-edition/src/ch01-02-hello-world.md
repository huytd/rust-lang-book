## Xin chào, thế giới!

Bây giờ bạn đã cài đặt Rust rồi, bắt đầu viết chương trình đầu tiên bằng Rust nào.
Một cách truyền thống khi bạn học một ngôn ngữ nào đó là in ra dòng chữ
 “Xin chào, thế giới!” ("Hello, World") trên màn hình, và trong phần này, chúng
 ta sẽ đi vẫn đi theo cách truyền thống.

> Ghi chú: chúng tôi giả định rằng bạn đã có một nền tảng kiến thức với terminal.
> Bản thân Rust không yêu cầu bạn phải sử dụng hết command line, hoặc môi trường
> phát triển, không phụ thuộc vào bất kỳ IDE nào. Nên bạn hoàn toàn độc lập vào
> việc chọn môi trường, công cụ trợ giúp. 

### Tạo thư mục dự án (project)

Đầu tiên, tạo một thư mục để lưu code Rust. Với Rust thì code không quan tâm được
lưu ở đâu, nhưng đối với sách này, chúng tôi đề nghị nên tạo một thư mục 
*projects* ngay trong thư mục home của bạn và luôn giữ code ở đây. Mở terminal và
lần lượt tiến hành theo các dòng lệnh (command) dưới đây để tạo thự mục *projects*:

Linux và Mac:

```text
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

Windows:

```cmd
> mkdir %USERPROFILE%\projects
> cd %USERPROFILE%\projects
> mkdir hello_world
> cd hello_world
```

### Tiến hành viết và chạy thử một chương trình bằng Rust

Kế tiếp, tạo một file mới và đặt tên nó là *main.rs*. Những file của Rust luôn luôn
có phần mở rộng là *.rs*. Nếu bạn dùng nhiều hơn một từ để đặt tên file, sử dụng
dấu gạch dưới "_" để ngăn cách nhưng từ đó. Ví dụ, bạn nên đặt tên file là
*hello_world.rs* hơn là *helloworld.rs*.

Bây giờ bạn mở file *main.rs* đã được tạo, và gõ dòng code sau vào:

<span class="filename">Tên file: main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

Lưu lại, và trở lại màn hình terminal. Đối với Linux hoặc OSX, thực hiện các dòng
lệnh sau:

```text
$ rustc main.rs
$ ./main
Hello, world!
```

Trên Windows, chạy `.\main.exe` thay vì `./main`. Không phụ thuộc hệ điều hành bạn
là gì, bạn sẽ nhìn thấy dòng chữ `Hello, world!` được in ở màn hình terminal. 
Nếu bạn làm được điều đó, xin chúc mừng bạn! Bạn đã chính thức viết được chương
trình đầu tiên bằng Rust. Điều đó đã làm cho bạn trở thành một Rust programmer! 
Xin chào mừng!

### Mổ xẻ chương trình được Rust

Bây giờ, chúng ta sẽ cùng đi tìm hiểu sâu hơn chương trình "Hello, World". 
Cùng xem đoạn code đầu tiên của Rust:

```rust
fn main() {

}
```

Những dòng trên định nghĩa một *function* (hàm) ở Rust. `main` function rất 
đặc biệt: hàm này sẽ là hàm được chạy đầu tiên trong chương trình Rust. Dòng đầu
tiên nói rằng, “Eh, tao khai báo một hàm tên là `main` không có truyền tham số gì
và cũng không cần trả gì về.” Nếu có tham số, thì nó phải được đặt trong cặp dấu
ngoặc tròn, `(` và `)`.

Also note that the function body is wrapped in curly braces, `{` and `}`. Rust
requires these around all function bodies. It's considered good style to put
the opening curly brace on the same line as the function declaration, with one
space in between.

Inside the `main` function:

```rust
    println!("Hello, world!");
```

This line does all of the work in this little program: it prints text to the
screen. There are a number of details to notice here. The first is that Rust
style is to indent with four spaces, not a tab.

The second important part is `println!`. This is calling a Rust *macro*,
which is how metaprogramming is done in Rust. If it were calling a function
instead, it would look like this: `println` (without the `!`). We'll discuss
Rust macros in more detail in Appendix E, but for now you just need to know
that when you see a `!` that means that you’re calling a macro instead of a
normal function.

Next is `"Hello, world!"` which is a *string*. We pass this string as an
argument to `println!`, which prints the string to the screen. Easy enough!

The line ends with a semicolon (`;`). The `;` indicates that this expression is
over, and the next one is ready to begin. Most lines of Rust code end with a
`;`.

### Compiling and Running Are Separate Steps

In "Writing and Running a Rust Program", we showed you how to run a newly
created program. We'll break that process down and examine each step now.

Before running a Rust program, you have to compile it. You can use the Rust
compiler by entering the `rustc` command and passing it the name of your source
file, like this:

```text
$ rustc main.rs
```

If you come from a C or C++ background, you'll notice that this is similar to
`gcc` or `clang`. After compiling successfully, Rust should output a binary
executable, which you can see on Linux or OSX by entering the `ls` command in
your shell as follows:

```text
$ ls
main  main.rs
```

On Windows, you'd enter:

```cmd
> dir /B %= the /B option says to only show the file names =%
main.exe
main.rs
```

This shows we have two files: the source code, with the *.rs* extension, and the
executable (*main.exe* on Windows, *main* everywhere else). All that's left to
do from here is run the *main* or *main.exe* file, like this:

```text
$ ./main  # or .\main.exe on Windows
```

If *main.rs* were your "Hello, world!" program, this would print `Hello,
world!` to your terminal.

If you come from a dynamic language like Ruby, Python, or JavaScript, you may
not be used to compiling and running a program being separate steps. Rust is an
*ahead-of-time compiled* language, which means that you can compile a program,
give it to someone else, and they can run it even without having Rust
installed. If you give someone a `.rb`, `.py`, or `.js` file, on the other
hand, they need to have a Ruby, Python, or JavaScript implementation installed
(respectively), but you only need one command to both compile and run your
program. Everything is a tradeoff in language design.

Just compiling with `rustc` is fine for simple programs, but as your project
grows, you'll want to be able to manage all of the options your project has
and make it easy to share your code with other people and projects. Next, we'll
introduce you to a tool called Cargo, which will help you write real-world Rust
programs.

## Hello, Cargo!

Cargo is Rust’s build system and package manager, and Rustaceans use Cargo to
manage their Rust projects because it makes a lot of tasks easier. For example,
Cargo takes care of building your code, downloading the libraries your code
depends on, and building those libraries. We call libraries your code needs
*dependencies*.

The simplest Rust programs, like the one we've written so far, don’t have any
dependencies, so right now, you'd only be using the part of Cargo that can take
care of building your code. As you write more complex Rust programs, you’ll
want to add dependencies, and if you start off using Cargo, that will be a lot
easier to do.

As the vast, vast majority of Rust projects use Cargo, we will assume that
you’re using it for the rest of the book. Cargo comes installed with Rust
itself, if you used the official installers as covered in the Installation
chapter. If you installed Rust through some other means, you can check if you
have Cargo installed by typing the following into your terminal:

```text
$ cargo --version
```

If you see a version number, great! If you see an error like `command not
found`, then you should look at the documentation for your method of
installation to determine how to install Cargo separately.

### Creating a Project with Cargo

Let's create a new project using Cargo and look at how it differs from our
project in `hello_world`. Go back to your projects directory (or wherever you
decided to put your code):

Linux and Mac:

```text
$ cd ~/projects
```

Windows:

```cmd
> cd %USERPROFILE%\projects
```

And then on any operating system run:

```text
$ cargo new hello_cargo --bin
$ cd hello_cargo
```

We passed the `--bin` argument to `cargo new` because our goal is to make an
executable application, as opposed to a library. Executables are binary
executable files often called just *binaries*. We've given `hello_cargo`
as the name for our project, and Cargo creates its files in a directory
of the same name that we can then go into.

If we list the files in the *hello_cargo* directory, we can see that Cargo has
generated two files and one directory for us: a *Cargo.toml* and a *src*
directory with a *main.rs* file inside. It has also initialized a new git
repository in the *hello_cargo* directory for us, along with a *.gitignore*
file; you can change this to use a different version control system, or no
version control system, by using the `--vcs` flag.

Open up *Cargo.toml* in your text editor of choice. It should look something
like this:

<span class="filename">Filename: Cargo.toml</span>

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]

[dependencies]
```

This file is in the [*TOML*][toml]<!-- ignore --> (Tom's Obvious, Minimal
Language) format. TOML is similar to INI but has some extra goodies and is used
as Cargo’s configuration format.

[toml]: https://github.com/toml-lang/toml

The first line, `[package]`, is a section heading that indicates that the
following statements are configuring a package. As we add more information to
this file, we’ll add other sections.

The next three lines set the three bits of configuration that Cargo needs to
see in order to know that it should compile your program: its name, what
version it is, and who wrote it. Cargo gets your name and email information
from your environment. If it’s not correct, go ahead and fix that and save the
file.

The last line, `[dependencies]`, is the start of a section for you to list any
*crates* (which is what we call packages of Rust code) that your project will
depend on so that Cargo knows to download and compile those too. We won't need
any other crates for this project, but we will in the guessing game tutorial in
the next chapter.

Now let's look at *src/main.rs*:

<span class="filename">Filename: src/main.rs</span>

```rust
fn main() {
    println!("Hello, world!");
}
```

Cargo has generated a "Hello World!" for you, just like the one we wrote
earlier! So that part is the same. The differences between our previous project
and the project generated by Cargo that we've seen so far are:

- Our code goes in the *src* directory
- The top level contains a *Cargo.toml* configuration file

Cargo expects your source files to live inside the *src* directory so that the
top-level project directory is just for READMEs, license information,
configuration files, and anything else not related to your code. In this way,
using Cargo helps you keep your projects nice and tidy. There's a place for
everything, and everything is in its place.

If you started a project that doesn't use Cargo, as we did with our project in
the *hello_world* directory, you can convert it to a project that does use
Cargo by moving your code into the *src* directory and creating an appropriate
*Cargo.toml*.

### Building and Running a Cargo Project

Now let's look at what's different about building and running your Hello World
program through Cargo! To do so, enter the following commands:

```text
$ cargo build
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
```

This should have created an executable file in *target/debug/hello_cargo* (or
*target\debug\hello_cargo.exe* on Windows), which you can run with this command:

```text
$ ./target/debug/hello_cargo # or .\target\debug\hello_cargo.exe on Windows
Hello, world!
```

Bam! If all goes well, `Hello, world!` should print to the terminal once more.

Running `cargo build` for the first time also causes Cargo to create a new file
at the top level called *Cargo.lock*, which looks like this:

<span class="filename">Filename: Cargo.lock</span>

```toml
[root]
name = "hello_cargo"
version = "0.1.0"
```

Cargo uses the *Cargo.lock* to keep track of dependencies in your application.
This project doesn't have dependencies, so the file is a bit sparse.
Realistically, you won't ever need to touch this file yourself; just let Cargo
handle it.

We just built a project with `cargo build` and ran it with
`./target/debug/hello_cargo`, but we can also use `cargo run` to compile
and then run:

```text
$ cargo run
     Running `target/debug/hello_cargo`
Hello, world!
```

Notice that this time, we didn't see the output telling us that Cargo was
compiling `hello_cargo`. Cargo figured out that the files haven’t changed, so
it just ran the binary. If you had modified your source code, Cargo would have
rebuilt the project before running it, and you would have seen something like
this:

```text
$ cargo run
   Compiling hello_cargo v0.1.0 (file:///projects/hello_cargo)
     Running `target/debug/hello_cargo`
Hello, world!
```

So a few more differences we've now seen:

- Instead of using `rustc`, build a project using `cargo build` (or build and
  run it in one step with `cargo run`)
- Instead of the result of the build being put in the same directory as our
  code, Cargo will put it in the *target/debug* directory.

The other advantage of using Cargo is that the commands are the same no matter
what operating system you're on, so at this point we will no longer be
providing specific instructions for Linux and Mac versus Windows.

### Building for Release

When your project is finally ready for release, you can use `cargo build
--release` to compile your project with optimizations. This will create an
executable in *target/release* instead of *target/debug*. These optimizations
make your Rust code run faster, but turning them on makes your program take
longer to compile. This is why there are two different profiles: one for
development when you want to be able to rebuild quickly and often, and one for
building the final program you’ll give to a user that won't be rebuilt and
that we want to run as fast as possible. If you're benchmarking the running
time of your code, be sure to run `cargo build --release` and benchmark with
the executable in *target/release*.

### Cargo as Convention

With simple projects, Cargo doesn't provide a whole lot of value over just
using `rustc`, but it will prove its worth as you continue. With complex
projects composed of multiple crates, it’s much easier to let Cargo coordinate
the build. With Cargo, you can just run `cargo build`, and it should work the
right way. Even though this project is simple, it now uses much of the real
tooling you’ll use for the rest of your Rust career. In fact, you can get
started with virtually all Rust projects you want to work
on with the following commands:

```text
$ git clone someurl.com/someproject
$ cd someproject
$ cargo build
```

> Note: If you want to look at Cargo in more detail, check out the official
[Cargo guide], which covers all of its features.

[Cargo guide]: http://doc.crates.io/guide.html
