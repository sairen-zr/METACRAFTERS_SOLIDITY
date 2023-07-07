# METACRAFTERS_SOLIDITY

This is Solidity's final project. This simple program taught us how to create, mint, and burn tokens. The purpose of this program is to serve as a final challenge for everyone who is interested in learning and wants to get a feel for how Solidity works.

# DESCRIPTION

This program is simply written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has two functions that burn and mint the token you created. This program serves as a simple and straightforward challenge to Solidity programming and can be used as a reviewer for more complex projects in the future.


# GETTING STARTED

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at:
https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.18+commit.87f61d96.js

# EXECUTING THE PROGRAM

Once you are on the Remix website, create a new file and name it 'MyToken.sol'. Then paste the code below:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here

    string public myToken = "RAI";
    string public tokenAbbrv = "R";
    uint public totalSupply = 0;

    // mapping variable here

    mapping (address => uint) public balances;

    // mint function

    function mint (address _address, uint _value) public {
      totalSupply += _value;
      balances [_address] += _value;
   }

    // burn function

    function burn (address _address, uint _value) public {
       if (balances[_address] >= _value){
         totalSupply -= _value;
         balances[_address] -= _value;
      }
    }
}

To execute the file, go to the left navigation side and press 'solidity compiler', then press 'Compile MyToken.sol'.

Then go back to the left navigation side and press 'Deploy & run transactions', then press 'Deploy'.

Then scroll down to 'Deployed contracts' >> 'MYTOKEN' >> then you will see our two functions which are the 'burn' and 'mint'.

# AUTHORS

Metacrafter Chris

@metacraftersio

# LICENSE

This project is licensed under the MIT License - see the LICENSE.md file for details

