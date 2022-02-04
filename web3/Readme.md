# Web3 Notes

Stuff

## @solana/web3
Basics stuff to interect with basic solana contracts send and read from the chain

## @solana/spl-token
Container JS/TS bindings to interact with `spl tokens`, like:
- mint
- transfer
- more... (Write dont be lazy)

## @solana/wallet-adapter-wallets
Used to boostrap connections with common wallets, works with React, Angular & vue


## Install Rust & Solana CLI
```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```
## Accounts
Accounts are used to store data. They are the essential building block for developing on Solana

### Facts
> - Stores Data
> - Each Accounts has an unique address
> - Accounts have a max size of 10mb
> - PDA accounts have a max size of 10kb
> - PDA accounts can be used to sign on behalf of a program
> - Account size is static
> - Account data storage is paid with rent
> - Default account owner is the System Program

### Account Modals
There are 3 kinds of accounts:

- Data accounts
- Program accounts
- Native accounts that indicate native program on Solana such as Sysyem, Stake and Vote

Within data accounts, there are 2 types:

- System owned accounts
- PDA(Program Derived Address) accounts

Each accounts has an address and an owner

| Field         | Description                                      |
| ------------- | ------------------------------------------------ |
| lamports      | The number of lamports owned by this account     |
| owner         | The program owner of this account                |
| executable    | whether this account can process instructions    |
| data          |The raw data byte array stored by this account    |
| rent_epoch    | The next epoch that this account will owe rent   |

Ownership rules:

- Only a data account;s owner can modify its data and debit lamports
- Anyone is allowed to credit lamports to a data account
- The owner of an account may assign a new owner if the account's data is zeroed out

**Program accounts don't store state**

![Program/Data Accounts](https://solanacookbook.com/assets/account_example.5b70d95a.jpeg)
