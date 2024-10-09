Audit report: https://code4rena.com/reports/2024-07-munchables
Category: #gamefi

* bug are often highly related to some missing state checks or not updating certain check in different functions
* in case of some points calculation, check if there are possible values provided from the protocol or ask them to provide, verify they wont lead to overflow/underflow
* when there is a minus operation, verify that there wont be a state which will lead to underflow
* Frontrunning admin deployment- check what are the consequences of this