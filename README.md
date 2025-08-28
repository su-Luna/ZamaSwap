Project Overview: Zama Swap is a confidential AMM example project based on FHEVM. It consists of two parts: a smart contract and a frontend.

contracts/: A Solidity contract compiled and deployed using Hardhat. It combines @fhevm/solidity with the OpenZeppelin confidential contract interface to implement confidential token minting/burning, authorization, and confidential trade matching (AMM).

front/: A frontend based on React and Vite. It integrates @zama-fhe/relayer-sdk to complete browser-side FHE instance initialization, encryption/decryption workflow, and contract interaction using ethers.

The main frontend pages include Swap, Liquidity, and Mint, which demonstrate the following:

Swap: Authorization → Calculate numerator and denominator on-chain → Decrypt and calculate quote off-chain → Submit expected output and slippage protection on-chain → Complete confidential swap.

Liquidity: Encrypts the TokenA/TokenB balances and adds/removes liquidity.

Mint: The contract owner mints confidential tokens. ZamaSwap is a confidential AMM example based on FHEVM, supporting token swaps and liquidity management without exposing users' plaintext balances and transaction amounts. The project consists of a Solidity smart contract and a React/Vite frontend. The frontend uses the Zama FHE relayer for encryption and decryption, interacting with ethers. The contract integrates @fhevm/solidity to implement token confidentiality, matching, and fine-grained permission control.

Project Track

xFi: Financial Application/Protocol Track. Projects promoting financial innovation and financial inclusion, such as trading protocols, DeFi, RWA, ReFi, and others, are welcome to apply.

Core Functionality

Confidential AMM Swap: Pricing and swaps are performed without revealing plaintext balances and transaction amounts.

Hybrid On-Chain/Off-Chain Computation: Calculate the numerator and denominator on-chain, decrypt division and slippage off-chain, and then encrypt and transmit back, ensuring both privacy and usability.

Confidential Liquidity Management: Supports encrypted LP supply and balances, and maintains confidentiality during the addition and removal of liquidity.

Fine-grained permissions and access control: A combination of setOperator, authorizeSelf, and FHE.allow/allowTransient ensures least-privileged access.

Integrated front-end experience: Built-in FHE instance initialization, encryption/decryption tools, and an interactive UI are readily available for general users.