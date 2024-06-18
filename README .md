# Aligned Open Testnet

Aligned works with EigenLayer to leverage ethereum consensus mechanism for ZK proof verification. Working outside the EVM, this allows for cheap verification of any proving system. This enables the usage of cutting edge algorithms, that may use new techniques to prove even faster. Even more, proving systems that reduce the proving overhead and add verifier overhead, now become economically feasable to verify thanks to Aligned.

## 1. Buy a minimum confrigration VPS
## 2. Login with VPS and Start the Proof task

### Install CURL
```
sudo apt update -y
sudo apt upgrade -y
``` 
```
sudo apt-get install curl -y
```
### Download ALignedProof
```
curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/install_aligned.sh | bash

```
```
source /root/.bashrc
```

### 8. With the RISC-V target:

```shell
rustup target add riscv32i-unknown-none-elf
```

### 9. Then install the Nexus zkVM:

```shell
cargo install --git https://github.com/nexus-xyz/nexus-zkvm nexus-tools --tag 'v1.0.0'
```

### 10. Create a new Nexus project

```shell
cargo nexus new nexus-project
```

This will create a new Rust project directory with the following structure:

```shell
./nexus-project
├── Cargo.lock
├── Cargo.toml
└── src
    └── main.rs
```

### 11. Move to Directory, Replace the code and press CNTL+X, Y, Enter

```
cd nexus-project
cd src
nano main.rs
```
As an example, you can change the content of `./src/main.rs` to:

```rust
#![no_std]
#![no_main]

fn fib(n: u32) -> u32 {
    match n {
        0 => 0,
        1 => 1,
        _ => fib(n - 1) + fib(n - 2),
    }
}

#[nexus_rt::main]
fn main() {
    let n = 7;
    let result = fib(n);
    assert_eq!(result, 13);
}
```


### 12. Run your program

```bash
cargo nexus run
```

### 13. step-by-step execution trace on the NVM, run:

```bash
cargo nexus run -v
```

### 14. Prove your program - Generate a proof for your Rust program using the Nexus zkVM.

```shell
cargo nexus prove
```

### 15. Verify your proof - Finally, load and verify the proof:

```shell
cargo nexus verify
```


#### Most importanly  commit and push the repo in github 

