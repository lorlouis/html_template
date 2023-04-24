# html_template

Incorporating Rust logic within HTML templates, PHP style.

## Basic usage

### Referencing a variable within a template

```rust
let title = "hello world";
let dom: String = html!{
    <html>
        <title>{title.to_string()}</title>
        "wowo mwmw"
    </html>
}.to_string();
// "<html><title>hello world</title>wowo mwmw</html>"
```

### Repeating HTML for each element

```rust
let dom: Root = html!{
    { (0..3).map(|v| html!({[move] format!("{}, ", v)})).collect() }
}.into();
// "0, 1, 2, "
```

> **_NOTE:_** `[move]` is needed in the second closure to take ownership of v
