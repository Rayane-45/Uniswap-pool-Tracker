## 👤 Auteur

**Rayane-45**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/rayane-saadallah-5a42a5254/)


# 🦄 DeFi Price Streaming

Ce programme en Rust permet de streamer les données de prix depuis **Uniswap V2 ou V3**, en fonction du réseau (Ethereum, Polygon, BNB), des adresses de tokens et des frais de pool (pour V3).

## 🚀 Fonctionnalités

- Support d’Uniswap V2 et V3
- Streaming des prix en temps réel
- Support multi-réseaux : Ethereum, Polygon, BNB
- Configuration en ligne de commande
- Utilisation d’`ethers-rs` pour l’interaction avec les blockchains

## 🛠️ Technologies

- Rust
- Cargo
- ethers-rs
- Tokio (asynchrone)
- WebSockets & RPC Ethereum

## 📦 Installation

### Prérequis

- [Rust](https://www.rust-lang.org/)
- Cargo (inclus avec Rust)

### Étapes

```bash
git clone https://github.com/Rayane-45/Uniswap-pool-Tracker.git
cd Uniswap-pool-Tracker
cargo build

   
### Running the Program
Run the program using Cargo:
```
cargo run [network] [uniswap_version] [token_address_a] [token_address_b] [optional: fee]
```

## Usage

### Uniswap V2
To stream prices from Uniswap V2 on Ethereum, specify two token addresses:
```
cargo run ethereum uniswapv2 <token_address_a> <token_address_b>
```

#### Example for Uniswap V2
Ethereum Network (WETH and USDT):
```
cargo run ethereum uniswapv2 0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2 0xdAC17F958D2ee523a2206206994597C13D831ec7
```

### Uniswap V3
For Uniswap V3, specify the chain, two token addresses, and the fee of the pool:
```
cargo run <network> uniswapv3 <token_address_a> <token_address_b> <fee>
```
Supported networks are Ethereum, Polygon, and BNB. Valid fee values are 500, 3000, or 10000.

#### Examples for Uniswap V3
- Ethereum Network:
  ```
  cargo run ethereum uniswapv3 0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2 0xdAC17F958D2ee523a2206206994597C13D831ec7 3000
  ```
- Polygon Network:
  ```
  cargo run polygon uniswapv3 0xc2132D05D31c914a87C6611C10748AEb04B58e8F 0x7ceB23fD6bC0adD59E62ac25578270cFf1b9f619 3000
  ```
- BNB Network:
  ```
  cargo run bnb uniswapv3 0x55d398326f99059fF775485246999027B3197955 0xbb4CdB9CBd36B01bD1cBaEBF2De08d9173bc095c 3000
  ```

🧠 Structure du code
config: initialisation des paramètres via init_args()
uniswap: modules spécifiques V2 et V3
main.rs: exécution asynchrone selon la version Uniswap

❗ Gestion d’erreurs
Vérification des arguments
Support réseau limité aux chaînes prises en charge
Messages d’erreur clairs en cas de mauvais usage


