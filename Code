// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleContract {
    uint256 public value;
    address public owner;

    // Set the owner (can only be called once)
    function setOwner(address _owner) public {
        require(owner == address(0), "Owner has already been set");
        owner = _owner;
    }

    // Set the value (only owner can call this)
    function setValue(uint256 _value) public {
        require(msg.sender == owner, "Only the owner can set the value");
        value = _value;
    }

    // Increment the value
    function incrementValue(uint256 _increment) public {
        uint256 newValue = value + _increment;
        assert(newValue >= value); // Check for overflow
        value = newValue;
    }

    // Reset the value to 0 (only owner can call this)
    function resetValue() public {
        if (msg.sender != owner) {
            revert("Only the owner can reset the value");
        }
        value = 0;
    }
}
