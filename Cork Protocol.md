Audit report: N/A
Category: #defi #uniswapv2 #vault 

* when protocol utilizes signed permit functionality, will attacker using this permit cause problems? 
* When providing liquidity to an AMM pair, the return result should be check because not all of the provided funds will be utilized and they will be returned back. 
* When interacting with uniswap v2 pairs and fetching the tokens amount verify in what order tokens amount are returned. Sometimes they can be in sorted (removeLiquidity()), sometimes they wont be.
* What will happen if vault is left without funds?
* Verify that each operation which update state, account for tokens correctly.
* `UUPSUpgradeable` contract with `notDelegated` modifier methods wont be callable from the proxy, which can be problematic
* when implementing modifier check, verify they check the correct condition
* when msg.sender is used, verify who might be the caller and if this msg.sender values is user later in the execution.
* 