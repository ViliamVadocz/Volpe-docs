# The Volpe Programming Language Book

To build you will need `mdbook`, which is a rust crate. Install rust and cargo
[here](https://www.rust-lang.org/tools/install). Then install `mdbook` by
running:

```text
cargo install mdbook
```

To build, run this the root directory (containing `book.toml`):

```text
mdbook build
```

## Custom Syntax Highlighting

I used my own fork of [highlight.js](https://highlightjs.org/) which includes
custom highlighting for the Volpe Programming Language.

To build the custom highlighting, follow the
[docs](https://highlightjs.readthedocs.io/en/latest/building-testing.html).
