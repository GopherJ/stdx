# The missing batteries of Rust

**stdx** is a project to collect the best Rust crates and validate
that they work together on the platforms that Rust supports.

## Current crates

The current revision of **stdx** is "0.115.0", which corresponds to
the Rust stable 1.15 release.

| Feature                        | Crate                     |                    |
| -------------------------------|---------------------------|--------------------|
| Bitfields                      | [`bitflags = "0.7.0"`]    | [📖][d-bitflags]    |
| Byte order conversion          | [`byteorder = "1.0.0"`]   | [📖][d-byteorder]   |
| Date and time                  | [`chrono = "0.2.25"`]     | [📖][d-chrono]      |
| Command-line argument parsing  | [`clap = "2.20.0"`]       | [📖][d-clap]        |
| Error handling                 | [`error-chain = "0.8.1"`] | [📖][d-error-chain] |
| Iterator extensions            | [`itertools = "0.5.9"`]   | [📖][d-itertools]   |
| Global initialization          | [`lazy_static = "0.2.2"`] | [📖][d-lazy_static] |
| C interop                      | [`libc = "0.2.18"`]       | [📖][d-libc]        |
| Logging                        | [`log = "0.3.6"`]         | [📖][d-log]         |
| Multidimensional arrays        | [`ndarray = "0.7.2"`]     | [📖][d-ndarray]     |
| Big, rational, complex numbers | [`num = "0.1.36"`]        | [📖][d-num]         |
| Random numbers                 | [`rand = "0.3.15"`]       | [📖][d-rand]        |
| Parallel iteration             | [`rayon = "0.6.0"`]       | [📖][d-rayon]       |
| Regular expressions            | [`regex = "0.2.1"`]       | [📖][d-regex]       |
| HTTP client                    | [`reqwest = "0.3.0"`]     | [📖][d-reqwest]     |
| Serialization                  | [`serde = "0.9.0-rc2"`]   | [📖][d-serde]       |
| Temporary directories          | [`tempdir = "0.3.5"`]     | [📖][d-tempdir]     |
| Configuration files            | [`toml = "0.2.1"`]        | [📖][d-toml]        |
| URLs                           | [`url = "1.3.0"`]         | [📖][d-url]         |

[`bitflags = "0.7.0"`]: #bitflags--070--
[`byteorder = "1.0.0"`]: #byteorder--100--
[`chrono = "0.2.25"`]: #chrono--0225--
[`clap = "2.20.0"`]: #clap--2200--
[`error-chain = "0.8.1"`]: #error-chain--081--
[`itertools = "0.5.9"`]: #itertools--059--
[`lazy_static = "0.2.2"`]: #lazy_static--022--
[`libc = "0.2.18"`]: #libc--0218--
[`log = "0.3.6"`]: #log--036--
[`ndarray = "0.7.2"`]: #ndarray--072--
[`num = "0.1.36"`]: #num--0136--
[`rand = "0.3.15"`]: #rand--0315--
[`rayon = "0.6.0"`]: #rayon--060--
[`regex = "0.2.1"`]: #regex--021--
[`reqwest = "0.3.0"`]: #reqwest--030--
[`serde = "0.9.0-rc2"`]: #serde--090-rc2--
[`tempdir = "0.3.5"`]: #tempdir--035--
[`toml = "0.2.1"`]: #toml--021--
[`url = "1.3.0"`]: #url--130--

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `bitflags = "0.7.0"` &emsp; [📖][d-bitflags]

[d-bitflags]: https://docs.rs/bitflags/0.7.0/bitflags/

The only thing this crate does is export the
[`bitflags!`](http://doc.rust-lang.org/bitflags/bitflags/macro.bitflags!.html#example)
macro, but it's a heckuva-useful macro. `bitflags!` produces typesafe
bitmasks, types with named values that are efficiently packed together
as bits to express sets of options. Official [rust-lang] crate.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `byteorder = "1.0.0"` &emsp; [📖][d-byteorder]

[d-byteorder]: https://docs.rs/byteorder/0.7.0/byteorder/

Functions for converting between numbers and bytes, in
in little-endian, or big-endian orders.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `chrono = "0.2.25"` &emsp; [📖][d-chrono]

[d-chrono]: https://docs.rs/chrono/0.2.25/chrono/

Date and time types.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `clap = "2.20.0"` &emsp; [📖][d-clap]

[d-clap]: https://docs.rs/clap/2.20.0/clap/

Clap is a command line argument parser that is easy to
use and is highly configurable.

**Alternatives**: [`docopt`]

[`docopt`]: https://docs.rs/docopt

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `error-chain = "0.8.1"` &emsp; [📖][d-error-chain]

[d-error-chain]: https://docs.rs/error-chain/0.8.1/error_chain/

Rust programs that handle errors consistently are reliable programs.
Even after one understands [error handling] in Rust, it can be
difficult to grasp and implement its best practices. `error-chain`
helps you define your own error type that works with the `?` operator
to make error handling in Rust simple and elegant.

[error handling]: https://rust-lang.github.io/book/ch09-00-error-handling.html

**Alternatives**: [`quick-error`]

[`quick-error`]: https://docs.rs/quick-error/1.1.0/quick_error/

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `itertools = "0.5.9"` &emsp; [📖][d-itertools]

[d-itertools]: https://docs.rs/itertools/0.5.9/itertools/

When it comes to iterators, this crate has everything *including* the
kitchen sink (in the form of the `batching` adaptor).  Highlights
include `dedup`, `group_by`, `mend_slices`, `merge`, `join` and more.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `lazy_static = "0.2.2"` &emsp; [📖][d-lazy_static]

[d-lazy_static]: https://docs.rs/env_logger/0.2.2/env_logger/

Global state is one of those things Rust doesn't do so well. In
particular there is no ['life before
main'](https://isocpp.org/wiki/faq/ctors#static-init-order) in Rust,
so it's not possible to write a programmatic constructor for a global
value that will be run at startup. Instead, Rust prefers lazy
execution for global initialization, and the
[`lazy_static!`](http://rust-ci.org/Kimundi/lazy-static.rs/doc/lazy_static/)
macro does just that.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `libc = "0.2.18"` &emsp; [📖][d-libc]

[d-libc]: https://docs.rs/libc/0.2.18/libc/

If you need to talk to foreign code, you need this crate. It contains
declarations for a grab bag of C types and functions that are correct
for the variety of compilers and platforms that Rust runs on. This
crate is a *notorious mess* design-wise, but it has endured for years
as the foundation Rust uses to talk to the outside world. Official
[rust-lang] crate.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `log = "0.3.6"` &emsp; [📖][d-log]

[d-log]: https://docs.rs/log/0.3.6/log/

The most common way to perform basic logging in Rust, with the
`error!`, `warn!`, `info!`, and `debug!` macros. It is often
combined with the `env_logger` crate to get logging to the
console, controlled by the `RUST_LOG` environment variable.
This is the traditional logging crate used by `rustc`, and
its functionality was once built in to the language.

**Supplemental crates**: [`env_logger = "0.4.0"`]

[`env_logger = "0.4.0"`]: https://docs.rs/env_logger/0.4.0/env_logger/

**Alternatives**: [`slog`], [`log4rs`]

[`slog`]: https://docs.rs/slog
[`log4rs`]: https://docs.rs/log4rs

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `ndarray = "0.7.2"` &emsp; [📖][d-ndarray]

[d-ndarray]: https://docs.rs/ndarray/0.7.2/ndarray/

The ndarray crate provides an N-dimensional container for general
elements and for numerics. The multidimensional array, otherwise known
as a "matrix", is a core data structure for numerical applications,
and Rust does not have one in the language or standard library.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `num = "0.1.36"` &emsp; [📖][d-num]

[d-num]: https://docs.rs/num/0.1.36/num/

Big integers, rational numbers, complex numbers, and a 'numeric tower'
of numeric traits. This is another rust-lang crate that has persisted
through Rust's evolution but is not designed well enough for the
standard library. It is though presently the most common way to access
the functionality it provides.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `rand = "0.3.15"` &emsp; [📖][d-rand]

[d-rand]: https://docs.rs/rand/0.3.15/rand/

Random number generators. The defaults are cryptographically
strong. Official [rust-lang] crate.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `rayon = "0.6.0"` &emsp; [📖][d-rayon]

[d-rayon]: https://docs.rs/rayon/0.6.0/rayon/

When people say that Rust makes parallelism easy, this
is why. Rayon provides parallel iterators that make
expressing efficient parallel operations simple
and foolproof.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `regex = "0.2.1"` &emsp; [📖][d-regex]

[d-regex]: https://docs.rs/regex/0.2.1/regex/

Another [BurntSushi](http://github.com/burntsushi) joint, this a very
performant regular expression implementation that [stomps the
competition](http://benchmarksgame.alioth.debian.org/u64/performance.php?test=regexdna)
in some benchmarks. Influenced by the highly-regarded
[RE2](https://github.com/google/re2) engine, it omits backreferences
and arbitrary lookahead in order to have predictable worst-case
performance. Official [rust-lang] crate.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `reqwest = "0.3.0"` &emsp; [📖][d-reqwest]

[d-reqwest]: https://docs.rs/reqwest/0.3.0/reqwest/

A simple HTTP client.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `serde = "0.9.0-rc2"` &emsp; [📖][d-serde]

[d-serde]: https://docs.rs/serde/0.9.0-rc2/serde/

Serialization and deserialization of Rust datastructures is fast
and easy using the `serde` serialization framework. Simply
tag your data structures with `#[derive(Serialize, Deserialize)]`
and serde will automatically convert them between formats like
JSON, TOML, YAML, and more. To best understand serde, read
its documentation at [serde.rs].

**Supplemental crates**: [`serde_derive = "0.9.0-rc2"`],
                         [`serde_json = "0.9.0-rc1"`],
                         [`toml = "0.2.1"]

**Alternatives**: [`rustc-serialize`]

[serde.rs]: https://serde.rs/
[`rustc-serialize`]: https://docs.rs/rustc-serialize
[`serde_derive = "0.9.0-rc2"`]: https://docs.rs/serde_derive/0.9.0-rc2/serde_derive
[`serde_json = "0.9.0-rc1"`]: https://docs.rs/serde_json/0.9.0-rc1/serde_json
[`toml = "0.2.1"]: https://docs.rs/toml/0.2.1/toml

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `tempdir = "0.3.5"` &emsp; [📖][d-tempdir]

[d-tempdir]: https://docs.rs/tempdir/0.3.5/tempdir/

Another standard library reject. If you need to create temporary
directories this is the official [rust-lang] way to do it.

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `toml = "0.2.1"` &emsp; [📖][d-toml]

[d-toml]: https://docs.rs/toml/0.2.1/toml/

[TOML](https://github.com/toml-lang/toml) is the format to use for
configuration files (at least once you are ready to advace beyond
simple [json serialization][json]). It is the format for configuring
Cargo (via [Cargo.toml](http://doc.crates.io/manifest.html)), and the
Rust implementation is maintained by master wizard [Alex
Crichton](https://github.com/alexcrichton).

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


### `url = "1.3.0"` &emsp; [📖][d-url]

[d-url]: https://docs.rs/url/1.3.0/url/

The Rust URL parser and type created for
[Servo](https://github.com/servo/servo), by
[SimonSapin](https://github.com/simonsapin).

[rust-lang]: http://github.com/rust-lang
[json]: http://doc.rust-lang.org/rustc-serialize/rustc_serialize/json/index.html#using-autoserialization

&nbsp;&NewLine;&nbsp;&NewLine;&nbsp;&NewLine;


## Contributing

**stdx** favors crates that have been 'battle-tested', this includes old
and unloved crates like [`libc`], crates that are used by the official
toolchain (which are maintained and highly-compatible if not always
beautiful), and crates that are otherwise popular and well maintained.

[`libc`]: https://github.com/rust-lang/libc

All crates must work on Rust's tier-1 platforms, currently x86 Linux,
OS X, and Windows.

All crates must be published to [crates.io](https://crates.io) along with documentation
link and declared license.


## License

**stdx** and the crates it links to are licensed under various
[permissive, BSD-like][perm] licenses. In lay-terms these licenses
allow their code to be used and distributed freely, and are compatible
with [Rust's own license (MIT/Apache 2)][rustlice].

**stdx** itself is dual MIT/Apache 2 licensed, like Rust, and the
copyright is owned by its contributors.

[perm]: https://en.wikipedia.org/wiki/Permissive_free_software_licence
[rustlice]: https://github.com/rust-lang/rust/blob/master/COPYRIGHT

