This is a solidity program to create a token and then mint the ether and burn it according to the given conditions
here is the sample code:


     // SPDX-License-Identifier: MIT
     pragma solidity ^0.8.26;

    contract My_First_Token {
    string public name;
    string public symbol;
    uint8 public decimals;
    uint256 public totalSupply;
    mapping(address => uint256) public Given_Balance;
    address payable public user_address;
    address constant public myAddress = 0xE0f5206BBD039e7b0592d8918820024e2a7437b9;


    constructor(string memory _name, string memory _symbol, uint8 _decimals) {
        name = _name;
        symbol = _symbol;
        decimals = _decimals;
    }

    function mint(address to, uint256 amount) external {
        Given_Balance[to] += amount;
        totalSupply += amount;
    }

    function burn(address from, uint256 amount) external {
        require(Given_Balance[from] >= amount, "Insufficient balance");
        Given_Balance[from] -= amount;
        totalSupply -= amount;
    }}


 
Thats all;;;;;;
