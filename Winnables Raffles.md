Audit report: https://audits.sherlock.xyz/contests/516/report
Category: #crosschain #randomness #raffle

* When we have a function which accepts arbitrary user input, does it change any important state on which other functionality depends? Can certain user input malicious/normal make any disruptions?
  In this case users were able to call a function with incorrect parameters which was leading to updating the state in one contract, but fails to update the state of the contract which was deployed on another chain.
* Can frontrunning a certain admin operation be a problem? If the price of execution for the admin is higher than the price for attacker it can be a problem. If this fronrunning is done perpatually, can it make the protocol unusable?
* A function which change some state may not update all needed variables or may update more than it should? Deeper understanding of the protocol is needed to catch these. Line by line approach. Good knowledge of the state variables and asking question for all of them if they should be updated.
* Carefully check when `=`, `<=` , `>=`, `<`, `>` are used. Edge cases might be taken differently than the code implementation.
* `setRole()` function or something similar was expected to also remove current role, but it was only adding the new one. Bitwise operation should be carefully inspected.
* Admin is considered trusted, but in case it is stated in the README that he should not be allowed to do certain things and if the code allows them to, they should be reported.
* for/while loop iterating over a value which can be manipulated by users is almost always problematic. Even if it cannot be controlled directly by users, it can make OOG problems if values length become high.
  