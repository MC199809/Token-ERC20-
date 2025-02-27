// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Stenfis is ERC20, Ownable {
    constructor() ERC20("Stenfis", "STNs") Ownable(msg.sender) {
        _mint(msg.sender, 1000 * 10 ** decimals()); // Mint 1000 tokens to the deployer
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function transfer(address recipient, uint256 amount) public override returns (bool) {
        return super.transfer(recipient, amount);
    }
}
