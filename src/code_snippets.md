# Code Snippets

## Rust:

- ## Optimized cargo.toml

```toml
[profile.release]
lto = true
strip = true
opt-level = 3
panic = "abort"
codegen-units = 1
```

- ## Async main function

```rust
#[tokio::main(flavor = "multi_thread")]
async fn main() -> Result<(), Box<dyn Error>> {}
```

- ## Clap Subcommands

```rust
use clap::{Parser, value_parser};

#[derive(Parser, Debug, Clone)]
pub enum CliArguments {}
```

- ## Clippy config 

```rust
#![warn(
    clippy::all,
    clippy::restriction,
    clippy::pedantic,
    clippy::nursery,
    clippy::cargo
)]
#![allow(
    clippy::missing_docs_in_private_items,
    clippy::question_mark_used,
    clippy::std_instead_of_core,
    clippy::cargo_common_metadata,
    clippy::blanket_clippy_restriction_lints,
    clippy::print_stdout,
    clippy::implicit_return,
    clippy::unwrap_used,
    clippy::arbitrary_source_item_ordering,
    clippy::single_call_fn,
    clippy::allow_attributes_without_reason,
    clippy::missing_const_for_fn,
    clippy::shadow_reuse,
)]
```

- ## Rustfmt config

```rust
max_width = 56
use_field_init_shorthand = true
use_small_heuristics = "Max"
```

## Python

- ## Polars config

```python
from polars import Config

Config.set_engine_affinity(engine="streaming")
Config.set_tbl_cols(-1)
Config.set_tbl_rows(-1)
Config.set_tbl_width_chars(-1)
Config.set_tbl_formatting("UTF8_FULL", rounded_corners=True)
Config.set_tbl_cell_alignment("CENTER")
Config.set_tbl_column_data_type_inline(True)
```

- ## Fastapi App

```python
from fastapi import FastAPI

DESCRIPTION = """
# A API
"""

app = FastAPI(
    swagger_ui_parameters = {"tryItOutEnabled": True},
    title = "API",
    debug = True,
    version = "0",
    description = DESCRIPTION.strip(),
)


@app.get("/")
def home() -> dict[str, str]:
    return {
        "title" : "A API",
        "description" : DESCRIPTION,
        "description_type" : "markdown"
    }
```