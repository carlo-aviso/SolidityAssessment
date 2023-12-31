# Minting and Burning of token
This solidity program is simple creation of "token" this simple program will mint and burn token. The purpose of this program is to create a simple minting and burning of token.

# DESCRIPTION
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract have two functions, minting and burning of tokens. This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

# GETTING STARTED
Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

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
    string public tokenName = "CryptoPeso";
    string public tokenAbbrev = "CPHP";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint) public balances; // it's gonna return its token amount
    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
     function burn(address _address, uint _value) public {
         if(balances[_address] >= _value){
              totalSupply -= _value;
              balances[_address] -= _value;
         }
       
    }
}
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" (or another compatible version), and then click on the "Compile myToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "mint" contract from the dropdown menu, and then click on the "Deploy" button second is select the "burn" contract from the dropdown menu, and then click on the deploy.

Once the contract is deployed. It will now give you the totalSupply of your token.

# AUTHORS
BSIT 2.1 CARLO AVISO
@NATIONAL TEACHERS COLLEGE
