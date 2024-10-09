Audit report: https://codehawks.cyfrin.io/c/2024-08-tadle/results?t=report&lt=contest&page=1

Category: #marketplace #onchainorders

* Verify initialization of a protocol that every step is intended. 
* Does withdrawal mechanism reset user balances?
* If there is a division operation, verify rounding is correct (who benefits in the certain rounding - user, protocol)
* Collateral is always important part of a protocol - when it is deposited, verify the needed amount is correctly calculated and taken. Collateral rate/ratio is another important part. In case of orders, users can set the collateralRate. Verify it cannot be changed to do harm to user or by setting it to a certain value it will do harm to others.
* In such protocol where orders are matched, reselled, buyed, orders will have some state related to them if they are actually valid for the certain operation. Carefully try to think yourself what kind of checks should be implemented and compare with the actually implemented ones.
* Implementing balance checks might not be compatible with FoT tokens
* 