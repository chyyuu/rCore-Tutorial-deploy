## 代码规范

### 代码风格
- 以 cargo 输出没有 warning 为准
- 可以通过根目录的 `make fmt` 来自动调用 `cargo fmt` 规范全部的代码

### 注释规范
- 用 `//!` 注释外层内容，例如在文件开始注释整个模块
- 用 `///` 为函数添加 doc 注释，其内部使用 Markdown 语法
- 可以使用 markdown 格式的链接，链接内容使用 Rust 可以直接链上，例如
  ```rust
  /// 样例注释
  /// [`link`]: crate::xxx::xxx
  fn some_func() {}
  ```

- 对于地址 literal，使用小写，使用 `_` 每隔四位进行标记，例如 `0x8000_0000` `0xffff_ffff_c000_0000`

- 实现一个 trait 时，doc 是可选的，而如果有，应当写在 impl 上面，而不是具体的方法上面
  ```rust
  /// doc here (optional)
  impl Default for Type {
    /// not here
    fn default() -> Self { ... }
  }
  ```

### 参考
- https://doc.rust-lang.org/1.26.2/book/first-edition/comments.html
- https://doc.rust-lang.org/1.26.2/book/second-edition/ch14-02-publishing-to-crates-io.html