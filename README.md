// SPDX-License-Identifier: UNLICENSED
pragma solidity ^0.8.23;

contract ControlStructures {
    error AfterHours(uint256 time);

    function fizzBuzz(uint256 _number) external pure returns (string memory) {
        if (_number % 15 == 0) {
            return "FizzBuzz";
        } else if (_number % 3 == 0) {
            return "Fizz";
        } else if (_number % 5 == 0) {
            return "Buzz";
        } else {
            return "Splat";
        }
    }

    function doNotDisturb(uint256 _time) external pure returns (string memory) {
        assert(_time <= 2400);

        if (_time <= 800 || _time > 2200) {
            revert AfterHours(_time);
        }

        if (_time > 800 && _time <= 1200) {
            return "Morning!";
        } else if (_time > 1200 && _time <= 1800) {
            return "Afternoon!";
        } else {
            return "Evening!";
        }
    }
}# BL2.2
