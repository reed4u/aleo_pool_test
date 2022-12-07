
# Aleo Install

## 1. Prerequisites

### 1.1 build & package tool
```
$sudo su
$apt update
$apt install build-essential
$apt-get install pkg-config libssl-dev
```
- GPU 사용 NVIDIA 경우
```
$sudo apt install nvidia-opencl-dev
```
### 1.2 Rust 설치
```
$curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
$source "$HOME/.cargo/env"
```
### 1.3 Go 설치
```
$wget -c https://golang.org/dl/go1.18.1.linux-amd64.tar.gz -O - | sudo tar -xz -C /usr/local
$echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc && source ~/.bashrc
```

## 2. Aleo-pool-server
### 1) install
```
$git clone https://github.com/reed4u/aleo_pool_test.git
$cd aleo-pool-test
$cargo install --force --path .
$cargo build
```
- 데이터베이스 기능을 끌 수 있음 | gpu 사용
```
$cargo build --release --no-default-features --features cuda
```
### 2) Run
```
$cargo run -- --address <ADDRESS> --port <PORT> --api-port <API PORT>
```
- 직접 시작
```
$target/release/snarkos --operator aleo1cev9umxxxxxxx......xxxx --trial
```

## 3. snarkOS

### 3.1 Install
- https://github.com/AleoHQ/snarkOS
```
$git clone https://github.com/AleoHQ/snarkOS.git --depth 1
$cd snarkOS
$./build_ubuntu.sh
```
- 공유기 포트포워드: 4133, 3033
```
$cargo install --path .
```

### 3.2 Run an Aleo Prover
```
$snarkos account new
- get a Private Key, View Key, Address
$./run-prover.sh
```
### 3.3 Run an Aleo Client
```
$./run-client.sh
```



