# Solidity project

This Solidity program is a simple contract that is used to mint, burn tokens and update their balance in the account.

## Description

The contract has public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply). The contract will have a mapping of addresses to balances (address => uint). We have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount. It also has a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”, the burn function also has conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public myToken="EtherT";
    string public tokenAbbrv="ET";
    uint public totalSupply=0;
    // mapping variable here
    mapping (address=>uint) public balances;    

    // mint function
    function mint(address addr, uint values)public{
        totalSupply+=values;
        balances[addr]+=values;
    }

    // burn function
    function burn(address addr2, uint values2)public{
        if(balances[addr2]>=values2){
         totalSupply-=values2;
         balances[addr2]-=values2;
        }
        
    }

}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "HelloWorld" contract in the left-hand sidebar, and then click on the "sayHello" function. Finally, click on the "transact" button to execute the function and retrieve the "Hello World!" message.

## Authors

Avinash Upadhyay  
21bcs8983@cuchd.in


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
