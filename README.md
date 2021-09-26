# simple-contract-consenSys-course-101

Dev Steps:

1. truffle init
2. truffle create contract SimpleStorage
3. Contract, simpleStorage.sol

````

// SPDX-License-Identifier: MIT
pragma solidity >=0.4.21 <0.7.0;

contract SimpleStorage {
  uint storedData;

  function set(uint x) public {
    storedData = x;
  }

  function get() public view returns (uint) {
    return storedData;
  }
}

````

4. truffle compile
5. run `truffle develop`
6. Inside Migrations add

````

var SimpleStorage = artifacts.require("./SimpleStorage.sol");

module.exports = function(deployer) {
  deployer.deploy(SimpleStorage);
};
    
````

7. Inside truffle develop shell run > `migrate`
8. Inside the shell next run `let storage = await SimpleStorage.deployed()`
9. storage.set(42)
10. (await contract.get()).toNumber()
11. Add Ganache to truffle.config

````

  development: {
    host: "127.0.0.1",
    port: 7545,
    network_id: "*",
  },

````

12. Create workspace
13. truffle migrate --network development
14. truffle migrate --network development --reset
15. truffle console --network development




