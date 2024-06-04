# META-Token : A Smart Contract using Solidity

This Solidity program is a token smart contract that demonstrates basic functionalities of a cryptocurrency token. The contract defines a simple token with minting and burning capabilities, enabling the creation and destruction of tokens.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. It defines a simple token named "META" with the abbreviation "MTA". The contract includes mechanisms for minting and burning tokens, and maintains a record of token balances for different addresses.

---

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

```javascript
pragma solidity 0.8.18;

contract MyToken {
    // public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
    // mapping variable
    mapping(address => uint) public balances;
    // mint function
    function mint(address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn(address _address, uint _value) public{
        if(balances[_address]>= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint, burn and various other functions. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" function and add an acount address and value to be minted. Finally, click on the "transact" button to execute the function and the minted value will be added. Now check balance of that acount by clicking on "Balances" and adding account address. Repeat the same process to burn any value and verify it by checking the balance again.

---
## Usage

**Minting Tokens:** To create new tokens, the mint function is called with the recipient's address and the amount of tokens to be created. The total supply and the recipient's balance are increased accordingly.

**Burning Tokens:** To destroy tokens, the burn function is called with the address from which the tokens will be removed and the amount of tokens to be burned. The function checks if the address has enough tokens before proceeding. If it does, the total supply and the address's balance are decreased accordingly.

This contract provides a basic implementation of a token with minting and burning capabilities, suitable for a variety of use cases in decentralized applications.

---

## Author

Akshita Sood

[@akshitasood08](https://github.com/akshitasood08)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
