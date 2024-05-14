# Functions-and-Errors
This is the code for module 1:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract Cresent {
    uint256 public value;

    constructor (uint _initialvalue){
      value = _initialvalue;
}

    function setValue(uint256 _newValue) external {
        require(_newValue != 0, "New value cannot be zero");
        
        if (_newValue == 5) {
            revert("New value cannot be 5");
        }

        if (_newValue == 20) {
            revert("New value cannot be 20");
        }

        value = _newValue;
    }
}
