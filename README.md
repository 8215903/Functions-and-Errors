# Functions-and-Errors

 // SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MicoReminder {
    uint BatteryPercentage;

    constructor(uint Percentage){
        BatteryPercentage = Percentage;

         assert(Percentage != 0);
    }

    function CheckBattery() public view{
        require(BatteryPercentage != 100, "Fully Charged!");
        
        if(BatteryPercentage <= 20){
            revert("Plug in your Charger!");
        }
        if (BatteryPercentage <= 50) {
            revert("Your Percentage is going low");
        }
    }
}
