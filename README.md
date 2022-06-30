# Joint Savings Account

## To automate the creation of joint savings accounts, you will create a solidity smart contract that accepts two user addresses that are then able to control a joint savings account. Your smart contract will use ether management functions to implement various requirements from the financial institution to provide the features of the joint savings account.

## Create a Joint Savings Account Contract in Solidity

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
 
## Compile and Deploy Your Contract in the JavaScript VM

1. Compile your smart contract. If an error occurs, review your code, and make the necessary changes for a successful compilation.

2. In the Remix IDE, navigate to the "Deploy & Run Transacion" pane, and then make sure that "JavaScript VM" is selected as the environment.

3. Click the Deploy button to deploy your smart contract, and then confirm that it successfully deployed.

## Interact with your Deployed Smart Contract

### Now that your contract is deployed, it's time to test its functionality! After each step, capture a screenshot of the execution, and then save it in a folder named "Execution_Results. You'll share this folder with your final submission.

### To interact with your deployed smart contract, complete the following steps:

1. Use the setAccounts function to define the authorized Ethereum address that will be able to withdraw funds from you contract.

2. Test the deposit functionality of your smart contract by sending the following amounts of ether. Afer eash transaction, use the contractBalance function to verify that the funds were added to you contract:

    - Transaction 1: Send 1 ether as wei.
    - Transaction 2: Send 10 ether as wei.
    - Transaction 3: Send 5 ether.
    
3. Once you've successfully deposited funds into your contract, test the contract's withdrawal functionality by withdrawing 5 ether into accountOne and 10 ether into accountTwo. After each transaction, use the contractBalance function to verify that the funds were withdrawn from your contract. Also, use the lastToWithdraw and lastWithdrawAmount functions to verify that the address and amount were correct.



### Screenshots


#### Deployed Contract

![Deployed_Contract](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Deployed_Contract.png "Deployed_Contract")

#### Send 1 ether as wei

![Send_1_Eth_as_WEI](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Deposit_1_Eth_as_WEI.png "Send_1_Eth_as_WEI")

#### Send 10 ether as wei

![Send_10_Eth_as_WEI](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Deposit_10_Eth_as_WEI.png "Send_10_Eth_as_WEI")

#### Send 5 ether

![Send_5_Eth](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Deposit_5_Eth_as_Ether.png "Send_5_Eth")

#### Set Accounts

![Set_accounts](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Set_Accounts.png "Set_accounts")

#### Withdrawal 5 ether to account1

![Withdrawal_5_Eth_to_account1](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Withdraw_5Eth.png "Withdrawal_5_Eth_to_account1")

#### Withdrawal 10 ether to account2

![Withdrawal_10_Eth_to_account2](https://github.com/schroeds20055/Module20_Challenge/blob/main/Execution_Results/Withdraw_10_Eth.png "Withdrawal_10_Eth_to_account2")