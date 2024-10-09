Audit report: https://codehawks.cyfrin.io/c/2024-08-fjord/results?lt=contest&sc=reward&sj=reward&page=1&t=report

Category: #staking #tokenmarket #auction

* When epochs are used in a staking contract, carefully check when users unstake, from which epoch they are unstaking - unstaking funds from earlier epoch might need different implementation than unstaking from the current epoch. Probably, some values related to staked/unstaked amount and last staked/unstaked epoch should be updated - carefully verify if they are updated correctly.
* block.timestamp related conditions should carefully use <,>, =, <=, >= checks and they should be consistent in the code base as they might create attack vectors for atomic operation which shouldnt be allowed.
* In case there are Factory contract, check if the deployed contract have another owner or it is the Factory itself. Is it expected that owner will do certain actions which wont be possible for the Factory contract to do.
* If two contracts rely on same epoch or should be synced based on a block.timestamp, check if the contracts are deployed correctly, so that their starting epoch timestamp are equal as this can lead to inconsistency.
* Always verify in what conditions an internal function which uses `msg.sender` or something related to the caller, is called. In different context the msg.sender can be different and lead to issues.