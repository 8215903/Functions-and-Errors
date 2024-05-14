# Functions-and-Errors
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MicoCrescent {
    // State variable to store the data
    uint256 public data;

    // Constructor to initialize the data
    constructor (uint256 _initialData){
        data = _initialData; // Set the initial data value
    }
    
    // Function to update the data with require
    function updateDataWithRequire(uint256 _newData) external {
        // Ensure that the new data is not zero
        require(_newData != 0, "Data cannot be zero");

        // Update the data
        data = _newData;
    }
    
    // Function to update the data with assert
    function updateDataWithAssert(uint256 _newData) external {
        // Check if the new data is not allowed
        assert(_newData != 7 && _newData != 42);

        // Update the data
        data = _newData;
    }
    
    // Function to update the data with revert
    function updateDataWithRevert(uint256 _newData) external {
        // Check if the new data is not allowed
        if (_newData == 7 || _newData == 42) {
            revert("Data cannot be 7 or 42");
        }

        // Update the data
        data = _newData;
    }
}
