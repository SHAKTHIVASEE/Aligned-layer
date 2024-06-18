# Aligned Open Testnet

Aligned works with EigenLayer to leverage ethereum consensus mechanism for ZK proof verification. Working outside the EVM, this allows for cheap verification of any proving system. This enables the usage of cutting edge algorithms, that may use new techniques to prove even faster. Even more, proving systems that reduce the proving overhead and add verifier overhead, now become economically feasable to verify thanks to Aligned.

## 1. Buy a minimum configuration VPS
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

### Download an SP1 ELF file

```
curl -L https://raw.githubusercontent.com/yetanotherco/aligned_layer/main/batcher/aligned/get_proof_test_files.sh | bash
```

### Sending proof

```
rm -rf ~/aligned_verification_data/ &&
aligned submit \
--proving_system SP1 \
--proof ~/.aligned/test_files/sp1_fibonacci.proof \
--vm_program ~/.aligned/test_files/sp1_fibonacci-elf \
--aligned_verification_data_path ~/aligned_verification_data \
--conn wss://batcher.alignedlayer.com
```

### Now you can see a explorer link, Check with explorer link your batch verification.. 

```
aligned verify-proof-onchain \
--aligned-verification-data ~/aligned_verification_data/*.json \
--rpc https://ethereum-holesky-rpc.publicnode.com \
--chain holesky
```


### Now you see the msg ( your proof was verified ), take the screenshot.. and follow our telegram group for further steps..

For upcoming projects follow in github..


