# sk_os
Andrew OS

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

1. [git](https://git-scm.com/)

2. [Rust](https://www.rust-lang.org/)

3. [bootimage](https://crates.io/crates/bootimage)
```Shell
cargo install bootimage
```

4. rust-src component
```Shell
rustup component add rust-src
```

5. (optional) [qemu](https://www.qemu.org/)

### Usage

#### Build
<details>
<summary>Debug</summary>

```Shell
cargo bootimage
```
</details>

<details>
<summary>Release</summary>

```Shell
cargo bootimage --release
```
</details>

#### (optional) Run on [qemu](https://www.qemu.org/)
<details>
<summary>Debug</summary>

```Shell
cargo run
```
or
```Shell
qemu-system-x86_64 -drive format=raw,file=target/x86_64-sk_os/debug/bootimage-sk_os.bin
```
</details>

<details>
<summary>Release</summary>

```Shell
cargo run --release
```
or
```Shell
qemu-system-x86_64 -drive format=raw,file=target/x86_64-sk_os/release/bootimage-sk_os.bin
```
</details>

#### (optional) run on real machine
1. IT MAY NOT WORK ON AN OS OTHER THAN LINUX
2. CHANGE sdX TO THE NAME OF THE USB DRIVE
<details>
<summary>Debug</summary>

```Shell
dd if=target/x86_64-sk_os/debug/bootimage-sk_os.bin of=/dev/sdX && sync
```
</details>

<details>
<summary>Release</summary>

```Shell
dd if=target/x86_64-sk_os/release/bootimage-sk_os.bin of=/dev/sdX && sync
```
</details>

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

## Made with the help of [this project](https://os.phil-opp.com/)

## License

[GPLv3](https://www.gnu.org/licenses/gpl-3.0-standalone.html)
