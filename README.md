# Functions-and-Errors
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.25;

contract MicoRhobert {
    // State variables
    uint256 public MicoData;

    // Events
    event DataChanged(uint256 newData);

    // Constructor
    constructor (uint256 _initialData) {
        setMicoData(_initialData);
    }

    // Function to update the data
    function updateMicoData(uint256 _newData) external {
        require(_newData != 0, "Data cannot be zero");
        require(_newData != 10 && _newData != 50, "Data cannot be 10 or 50");
        
        setMicoData(_newData);
    }

    // Function to check input
    function checkInput(uint256 userInput) external pure {
        require(userInput > 8, "Input must be greater than 8");
    }

    // Function to verify counter (if needed)
    function verifyMicoCounter() external pure {
    }

    // Error for insufficient balance
    error InsufficientBalance(uint256 currentBalance, uint256 requiredAmount);

    // Function to check balance
    function checkMicoBalance(uint256 amount) external view {
        uint256 balance = address(this).balance;
        require(balance >= amount, "Insufficient balance");
    }

    // Internal function to set MicoData and emit event
    function setMicoData(uint256 _newData) internal {
        MicoData = _newData;
        emit DataChanged(_newData);
    }
}

        }

        // Update the data
        data = _newData;
    }
}
