pragma solidity ^0.4.0;
contract BunzTransaction {
    
    address public buyer; //location of buyer
    uint public timePeriod; //timePeriod of transaction, depends on item category
    uint public price; //price of item agreed on in Bunz
    mapping (address => uint) public balances;
    
    constructor ( //pass given variable values
        uint _timePeriod,
        address _buyer,
        uint _price
        )  public { //constructor
        buyer = _buyer;
        timePeriod = now + _timePeriod;
        price = _price;
    }
    modifier onlyBuyer { //buyer is one sending money
        require(msg.sender == buyer);
        _;
    }
    
    function() payable public { //keep all ether from buyer locked? how to do this
       
    }

    function timePeriodEnd(address _seller) onlyBuyer public {
        require (now >= timePeriod); //must be past time period to release money
        msg.sender.transfer(price);
        
    }
}
