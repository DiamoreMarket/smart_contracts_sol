# DiamoreToken
[Git Source](https://github.com/DiamoreMarket/smart_contracts_sol/blob/d9c233f3d22bc21895cd7ba877d73ff5b80f578a/contracts/DiamoreToken.sol)

**Inherits:**
ERC165, [IDiamoreToken](/contracts/interfaces/IDiamoreToken.sol/interface.IDiamoreToken.md), ERC20

**Author:**
The Diamore Team

Diamore tokens are ERC20 tokens that can be exchanged for a specified amount of the original tokens.

*Diamore tokens are created by the factory contract.*


## State Variables
### originalToken

```solidity
address public originalToken;
```


### _decimal

```solidity
uint8 internal _decimal;
```


## Functions
### constructor

*Constructor for DiamoreToken.*


```solidity
constructor(string memory name, string memory symbol, uint8 dec, address origToken) ERC20(name, symbol);
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`name`|`string`|The name of the token.|
|`symbol`|`string`|The symbol of the token.|
|`dec`|`uint8`|The decimal of the token.|
|`origToken`|`address`|The original token address.|


### deposit

This function allows users to exchange their tokens for diamore tokens.

*This function transfers the specified amount of tokens from the caller's account to the DiamoreToken contract.
If the specified amount is zero, the function will revert with the message 'Zero amount'.*


```solidity
function deposit(uint256 amount) external override;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`amount`|`uint256`|The amount of tokens to be exchanged.|


### withdraw

This function allows users to reverse exchange their diamore tokens for their original tokens.

*This function burns the specified amount of diamore tokens from the caller's account
and transfers the specified amount of original tokens to the caller's account.
If the specified amount is zero, the function will revert with the message 'Zero amount'.*


```solidity
function withdraw(uint256 amount) external override;
```
**Parameters**

|Name|Type|Description|
|----|----|-----------|
|`amount`|`uint256`|The amount of diamore tokens to be reversed.|


### decimals


```solidity
function decimals() public view override returns (uint8);
```

### supportsInterface

*See [IERC165-supportsInterface](/contracts/DiamoreETHToken.sol/contract.DiamoreETHToken.md#supportsinterface).*


```solidity
function supportsInterface(bytes4 interfaceId) public view virtual override returns (bool);
```

