# C-sharp-ATM-Simulator-Project
An Automatic Teller Simulator (ATM) project using C# language in Visual Studio IDE

An application prototype that simulates the operation of an automatic teller machine (ATM).

Key Functions
The main functions of the ATM simulator may be summarized as follows:
  > Before performing any transaction, the user must enter his or her name and PIN (personal identification number) on an input screen. 
  Since the operation of this input screen should simulate the normal operation of an ATM, the PIN should not appear on the screen.
  
  > In addition to the message which appears after every unsuccessful attempt, if after three tries the PIN matching the name has not been entered, 
  the application should display a message requesting the user to try using the ATM again later. 
  The names and PINs of users must be validated using data contained in the Customers data source having the following structure:
    name (String), 
    PIN (String – 4 characters).
      
* Used the provided CustomerInfo.txt text file as a source of the data. 

  > Once access has been authorized, the main form of the application should allow the user to carry out one of the following transactions:
    Deposit, 
    Withdrawl, 
    Transfer, 
    Bill payment.
    
  > When a user performs an operation, the application should first ask if it should be done using a chequing or savings account, 
    and then ask for the transaction amount. 
    Below is the structure of the Accounts.txt sequential file ( database) in which account balances are stored:
    account type (1 character), 
    PIN (String - 4 characters), 
    account number (String - 5 characters), 
    account balance (single).
    
  > For a deposit, the user must enter the amount and, if required, be able to select the account type to be credited. 
  The chequing account is the default for this transaction. There is no maximum amount.
  
  > For a withdrawal, the user must enter the amount and, if required, be able to select the account type to be debited. 
  The chequing account is the default for this transaction subject to a maximum of $1,000. 
  If the user enters an amount greater than $1000, the system must present a message indicating that $1000 is the maximum per withdrawal.
  The ATM accepts only transactions for which the amount entered is a multiple of $10. There is no maximum amount (apart from the user’s account balance)
  in which case the system must also inform the user if the account balance is less than the transaction amount. In addition, 
  the ATM Machine starts its day with a full $20,000 in funds. Each withdrawal must also be validated against the amount left in the machine If 
  the withdrawal amount is greater than the amount left in the machine, the system must inform the user that the machine has insufficient funds (not the user account)
  
  > For a transfer, the user must enter the amount and the type of transfer (from chequing to savings, or savings to chequing). 
  This transaction is subject to a maximum $10,000 (or the user’s account balance). 
  The system must also validate that the account balance from which the amount is being transferred has sufficient funds to cover the transaction amount.
  
  > For a bill payment, which is done from a chequing account only, the user must enter the amount of the transaction. 
  The chequing account is debited by the same amount. In addition, a $1.25 fee is charged to the chequing account. 
  The maximum per transaction is $10,000 (or the user’s chequing account balance). Note that if the $10,000 maximum bill payment is made, 
  then the actual amount removed from the account is $10,001.25
  
  > The application must check the account balance before doing a transaction. Any transaction that would result in a negative balance must be rejected.
  
  > The balance of the account affected by a transaction should be updated and displayed after each transaction.
  
  > The user should be able to do as many transactions as he or she would like to do before leaving the ATM.
  
  > A warning message should inform the user that the ATM can no longer carry out withdrawals when there is no money available. 
  When a withdrawal transaction event occurs for an amount greater than the balance remaining in the ATM, 
  the ATM should advise the user that they can change the transaction amount to the amount still available in the ATM.
  
  > Each time the application starts, the ATM checks DailyBalances.txt to see if it contains a record with today’s date. 
  If not, then this is the first time the ATM is used today, and it automatically sets the ATM’s balance to $20,000 and adds a record to DailyBalances.txt 
  Below is the structure of the DailyBalances data source (database table or text file, your choice) in which the ATM’s daily balances are stored:
  Date (DateTime)
  ATM balance (single)
  
* The following functions concern the ATM's functioning with respect to the system administrator and the internal mechanisms of the ATM, not the user.

  > The system administrator, as any other user, must enter his or her name and PIN (personal identification number) on the same input screen. 
  The system administrator may perform only system transactions (he or she has no personal account).
  
  > Once access has been authorized, a special menu is displayed. This menu offers the following options:
  pay interest, 
  refill the ATM with money, 
  take the ATM out of service, 
  print the accounts report.
  
  > The supervisor can cause interest to be paid to all savings accounts at the rate of 1% (new balance = current balance + (current balance * 0.01)).
  
  > The system administrator re-fills the ATM in batches of $5,000. There should not be more than $20,000 available in the ATM.
  
  > The supervisor can take the ATM out of service, which ends the program (in theory, only the supervisor can end the program - 
  when a regular user exits, it should return to the Welcome screen for another user to login).
  
  > The accounts report displays all chequing and savings account information for all customers in a textbox.
  
  
