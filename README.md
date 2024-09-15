# Token

Solidity is a high-level programming language specifically designed for implementing smart contracts on the Ethereum blockchain. It was created to enable the writing of decentralized applications (dApps) that run on the Ethereum Virtual Machine (EVM).

## Description

This contract defines a simple token with the name and abbreviation. It includes basic minting and burning functionality:

1- Minting: Increases the total supply and the balance of a specified address.

2- Burning: Decreases the total supply and the balance of a specified address, provided the address has enough tokens.

The contract stores the token name, abbreviation, and total supply, maps addresses to their token balances, and includes functions to mint and burn tokens.
## Getting Started

### Executing program

To run this program, use Remix, an online Solidity IDE. Visit the Remix website at Remix IDE https://remix.ethereum.org/, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file, which includes functions to mint and burn tokens. The code link from the Remix IDE is provided here: https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    uint public total_supply = 0;
    string public t_name = "FERNO";
    string public t_abbr = "FRN";

    // mapping variable here
    mapping(address => uint) public balance;

    // mint function
    function mint(address _add, uint _val) public { 
    total_supply +=_val;
    balance[_add] += _val;
    }
    // burn function
    function burn(address _add, uint _val) public {
        if(balance[_add]>=_val){
        total_supply -=_val;
        balance[_add] -=_val;
        }
    }
}


```
To compile the code, navigate to the "Solidity Compiler" tab on the left sidebar in Remix. Ensure the "Compiler" version is set to 0.8.18 or another compatible version, then click "Compile MyToken.sol."
After successful compilation, proceed to deploy the contract by going to the "Deploy & Run Transactions" tab on the left sidebar. Choose the "MyToken" contract from the dropdown menu and press the "Deploy" button.

With the contract deployed, you can interact with it by using the provided functions.
Minting: To mint new tokens, select the mint function, input the recipient's address and the amount of tokens to mint, and click "transact." 
Burning: To burn tokens, select the burn function, input the address and the quantity of tokens to burn, then click "transact."

These steps will allow you to test and manage your token contract using Remix.

## Authors
ANADI SHUKLA                                                                                                                
@Anadi0094

## License

This project is licensed under the MIT LICENSE - see the LICENSE.md file for details
