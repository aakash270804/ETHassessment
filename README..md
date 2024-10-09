# MyToken
This Solidity contract represents a simple token system. The contract allows minting and burning tokens while keeping track of balances and total supply.

## Description
The MyToken contract is a basic demonstration of creating, minting, and burning tokens on the Ethereum blockchain using Solidity. It contains public variables for storing token details, a mapping to manage balances, and two functions: mint to increase the supply and balances, and burn to reduce them. This contract is ideal for developers looking to understand basic token operations on Ethereum.

## Getting Started
### Installing
To work with this contract, you need access to an Ethereum development environment like Remix.

Go to the Remix IDE at Remix.
Create a new file with a .sol extension (e.g., MyToken.sol).
Copy and paste the following code into the file:
solidity
Copy code

    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.26;
    
    contract MyToken {
        // public variables here
        string public tokenName = "CODER";
        string public tokenAbbrv = "COD";
        uint public totalsupply = 0;

        // mapping variable here
        mapping(address => uint) public balances;

        // mint function
        function mint (address _address, uint _value) public {
            totalsupply += _value;
            balances[_address] += _value;
        }

        // burn function
        function burn (address _address, uint _value) public {
            if (balances[_address] >= _value){
                totalsupply -= _value;
                balances[_address] -= _value;
            }
        }
    }
    
    


### Executing Program
Compile the contract using the Solidity Compiler in Remix. Ensure the compiler version is set to 0.8.26 or another compatible version.
Deploy the contract using the "Deploy & Run Transactions" tab.
After deploying, use the mint function to add tokens to a specified address and the burn function to reduce tokens.
For example:

To mint tokens, provide an address and the amount of tokens to add.
To burn tokens, provide an address and the amount to reduce from both the total supply and the address’s balance.

## Help
If you encounter any issues while executing the contract, ensure:

The address balance is sufficient before burning tokens.
You have selected the correct Solidity version in the Remix IDE.
To check available helper commands and options, run the contract in Remix.

## Authors
Aakash Raj
akashraj2708@gmail.com

## License
This project is licensed under the MIT License - see the LICENSE.md file for details.
