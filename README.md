# Joint Savings Account

## To automate the creation of joint savings accounts, you will create a solidity smart contract that accepts two user addresses that are then able to control a joint savings account. Your smart contract will use ether management functions to implement various requirements from the financial institution to provide the features of the joint savings account.

## The Starting file provided for this challenge contains a `pragma` for solidity version `5.0.0`.

### You will do the following:

1. Create and work within a local blockchain development environment using the JavaScript VM provided by the Remix IDE.

2. Script and deploy a **JointSavings** smart contract.

3. Interact with your deployed smart contract to transfer and withdraw funds.


### Inside the new contract define the following variables:

1. Two variables of type `address payable` named `accountOne` and `accountTwo`

2. A variable of type `address public` named `lastToWithdraw`

3. Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`.
    
### Define a function named **withdraw** that will accept two arguments.

1. A `uint` variable named `amount`

2. A `payable address` named `recipient`

3. Define a `require` statement that checks if the `recipient` is equal to either `accountOne` or `accountTwo`. The `requiere` statement returns the text `"You don't own this account!"` if it does not.
        
4. Define a `require` statement that checks if the `balance` is sufficient to accomplish the withdraw operation. If there are insufficient funds, the text `Insufficient funds!` is returned.
        
5. Add and `if` statement to check if the `lastToWithdraw` is not equal to (`!=`) to `recipient` If `lastToWithdraw` is not equal, then set it to the current value of `recipient`.

6. Call the `transfer` function of the `recipient` and pass it the `amount` to transfer as an argument.

7. Set  `lastWithdrawAmount` equal to `amount`

8. Call the `contractBalance` variable and set it equal to the balance of the contract by using `address(this).balance` to reflect the new balance of the contract.

### Define a `public payable` function named `deposit`.

1. Call the `contractBalance` variable and set it equal to the balance of the contract by using `address(this).balance`.

### Define a `public` function named `setAccounts` that receive two `address payable` arguments named `account1` and `account2`.

1. Set the values of `accountOne` and `accountTwo` to `account1` and `account2` respectively.

2. Finally, add the **default fallback function** so that your contract can store Ether sent from outside the deposit function.
 
