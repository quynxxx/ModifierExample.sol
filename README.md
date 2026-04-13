# ModifierExample.sol
ModifierExample.sol
pragma solidity ^0.8.20;
contract ModifierExample {
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Not owner");
        _;
    }

    function restricted() public onlyOwner {}
}
