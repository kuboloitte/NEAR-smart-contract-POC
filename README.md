# Fungible Token Example`

## Prerequisites

1. Sign up for a near testnet account (https://wallet.testnet.near.org/create).
2. Make sure you've installed Node.js ≥ 12
3. Install the NEAR CLI globally: [near-cli] is a command line interface (CLI) for interacting with the NEAR blockchain.
4. Install dependencies: `yarn install`

## Build and deploy your Fungible Token

1. Build the smart contract:
   `yarn build:release`

2. Deploy the smart contract
   ` near dev-deploy --wasmFile ./build/release/main.wasm --accountId <Your Near Test Account Id>`

3. (Optional) In the `src/main/assembly/index.ts` file, you can modify the function ft_initialize` to replace the stub parameters with your own parameters.

The parameters used in this example are 4:
1-“TokenName” is the name of the token to create.
2-“SYMB” is the symbol of the token.
3-The third parameter describes the number of the decimals of the tokenbase.
4-64TokenSvg is the base 64 icon of the token shown in the wallet.

#### Let's Build Token

4. Use near-cli to initialize your fungible token
   `near call <Your Contract Account> ft_init --account-id <Your Near Test Account Id>`
   (In the scripts folder you can find some files with a lot of useful commands.)

$ near call dev-1685187190320-28663868934663 ft_initialize --account-id navneet11223.testnet

5. Mint some token in your address: `near call $CONTRACT ft_mint '{"account":$ID_ACCOUNT,"amount":"100"}' --account-id $ID_ACCOUNT`

$ near call dev-1685187190320-28663868934663 ft_mint '{"account":"navneet11223.testnet","amount":"100"}' --account-id navneet11223.testnet


