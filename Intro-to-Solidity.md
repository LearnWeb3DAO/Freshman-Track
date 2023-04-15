# Level 6 - Solidity

![image](https://user-images.githubusercontent.com/16539849/173656651-a46df615-8ec3-43fd-9619-98647a6d2bd2.png)

In this module you will learn what is Solidity and the basic syntax of the language.

## What is Solidity ?

- Solidity is an object-oriented, high-level language for implementing smart contracts. It is designed to target [Ethereum Virtual Machine(EVM)](https://coinmarketcap.com/alexandria/glossary/ethereum-virtual-machine-evm)
- It is statically typed, supports inheritance, libraries and complex user-defined types among other features.

<Quiz questionId="e7201124-8b84-4e20-99d3-d85189ee1817" />

## Building in Solidity

### Initializing smart contracts

```solidity
// Define the compiler version you would be using
pragma solidity ^0.8.19;

// Start by creating a contract named HelloWorld
contract HelloWorld {

}
```

### Variables and types

There are 3 types of variables in Solidity

- Local
  - Declared inside a function and are not stored on blockchain
- State
  - Declared outside a function to maintain the state of the smart contract
  - Stored on the blockchain
- Global
  - Provide information about the blockchain. They are injected by the Ethereum Virtual Machine during runtime.
  - Includes things like transaction sender, block timestamp, block hash, etc.
  - [Examples of global variables](https://docs.soliditylang.org/en/v0.8.19/units-and-global-variables.html)

The scope of variables is defined by where they are declared, not their value. Setting a local variable's value to a global variable does not make it a global variable, as it is still only accessible within it's scope.

<Quiz questionId="04b4af27-6816-4a2e-9070-16c6e4c783ce" />

```solidity
// Define the compiler version you would be using
pragma solidity ^0.8.19;

// Start by creating a contract named Variables
contract Variables {
    /*
        ******** State variables **********
    */
    /*
    uint stands for unsigned integer, meaning non negative integers
    different sizes are available. Eg
        - uint8   ranges from 0 to 2 ** 8 - 1
        - uint256 ranges from 0 to 2 ** 256 - 1
    `public` means that the variable can be accessed internally
     by the contract and can also be read by the external world
    */
    uint8 public u8 = 10;
    uint public u256 = 600;
    uint public u = 1230; // uint is an alias for uint256

    /*
    Negative numbers are allowed for int types. Eg
    - int256 ranges from -2 ** 255 to 2 ** 255 - 1
    */
    int public i = -123; // int is same as int256

    // address stands for an ethereum address
    address public addr = 0xCA35b7d915458EF540aDe6068dFe2F44E8fa733c;

    // bool stands for boolean
    bool public defaultBoo1 = false;

    // Default values
    // Unassigned variables have a default value in Solidity
    bool public defaultBoo2; // false
    uint public defaultUint; // 0
    int public defaultInt; // 0
    address public defaultAddr; // 0x0000000000000000000000000000000000000000

    function doSomething() public {
        /*
        ******** Local variable **********
        */
        uint ui = 456;

        /*
        ******** Global variables **********
        */

        /*
            block.timestamp tells us whats the timestamp for the current block
            msg.sender tells us which address called the doSomething function
        */
        uint timestamp = block.timestamp; // Current block timestamp
        address sender = msg.sender; // address of the caller
    }
}
```

<Quiz questionId="2156e5cd-26ac-402d-bbe9-ecaefdd8c87a" />
<Quiz questionId="bd68f893-b126-4f54-aa78-2906f2287629" />
<Quiz questionId="d934fc15-f88d-4cd7-b903-f268f1c16980" />
<Quiz questionId="a531c37c-96f9-4bbd-a80f-893b37a5c94e" />

### Functions, Loops and If/Else

```solidity
// Define the compiler version you would be using
pragma solidity ^0.8.19;

// Start by creating a contract named Conditions
contract Conditions {
    // State variable to store a number
    uint public num;

    /*
        Name of the function is set.
        It takes in an uint and sets the state variable num.
        It is declared as a public function meaning
        it can be called from within the contract and also externally.
    */
    function set(uint _num) public {
        num = _num;
    }

    /*
        Name of the function is get.
        It returns the value of num.
        It is declared as a view function meaning
        that the function doesn't change the state of any variable.
        view functions in solidity do not require gas.
    */
    function get() public view returns (uint) {
        return num;
    }

    /*
        Name of the function is foo.
        It takes in an uint and returns an uint.
        It compares the value of x using if/else
    */
    function foo(uint x) public returns (uint) {
        if (x < 10) {
            return 0;
        } else if (x < 20) {
            return 1;
        } else {
            return 2;
        }
    }

    /*
        Name of the function is loop.
        It runs a loop till 10
    */
    function loop() public {
        // for loop
        for (uint i = 0; i < 10; i++) {
            if (i == 3) {
                // Skip to next iteration with continue
                continue;
            }
            if (i == 5) {
                // Exit loop with break
                break;
            }
        }
    }


}

```

<Quiz questionId="b9a5620b-7c92-450b-afa8-1cda0dfba54a" />
<Quiz questionId="f14bb058-720b-42e5-ba85-4c7bfc1b93ee" />

### Arrays, Strings

Array can have a compile-time fixed size or a dynamic size.

```solidity
pragma solidity ^0.8.19;

contract Array {

    // Declare a string variable which is public
    string public greet = "Hello World!";
    // Several ways to initialize an array
    // Arrays initialized here are considered state variables that get stored on the blockchain
    // These are called storage variables
    uint[] public arr;
    uint[] public arr2 = [1, 2, 3];
    // Fixed sized array, all elements initialize to 0
    uint[10] public myFixedSizeArr;
    /*
        Name of the function is get
        It gets the value of element stored in an array's index
    */
    function get(uint i) public view returns (uint) {
        return arr[i];
    }

    /*
     Solidity can return the entire array.
     This function gets called with and returns an uint[] memory.
     memory - the value is stored only in memory, and not on the blockchain
              it only exists during the time the function is being executed

     Memory variables and Storage variables can be thought of as similar to RAM vs Hard Disk.
     Memory variables exist temporarily, during function execution, whereas Storage variables
     are persistent across function calls for the lifetime of the contract.
     Here the array is only needed for the duration while the function executes and thus is declared as a memory variable
    */
    function getArr(uint[] memory _arr) public view returns (uint[] memory) {
        return _arr;
    }

     /*
        This function returns string memory.
        The reason memory keyword is added is because string internally works as an array
        Here the string is only needed while the function executes.
    */
    function foo() public returns (string memory) {
        return "C";
    }

    function doStuff(uint i) public {
        // Append to array
        // This will increase the array length by 1.
        arr.push(i);
        // Remove last element from array
        // This will decrease the array length by 1
        arr.pop();
        // get the length of the array
        uint length = arr.length;
        // Delete does not change the array length.
        // It resets the value at index to it's default value,
        // in this case it resets the value at index 1 in arr2 to 0
        uint index = 1;
        delete arr2[index];
        // create array in memory, only fixed size can be created
        uint[] memory a = new uint[](5);
        // create string in memory
        string memory hi = "hi";
    }

 }
```

<Quiz questionId="0643be02-c57b-41b0-b7e2-9e855883b7c2" />
<Quiz questionId="ec82e3aa-ec12-4d8b-8f81-f21ff1fb0a54" />
<Quiz questionId="bab86524-5ace-4baa-add4-f66482b51abe" />

## References

[Solidity by Example](https://solidity-by-example.org/)

## Resources for learning extra

- [Cryptozombies](https://cryptozombies.io/)
- [Solidity by Example](https://solidity-by-example.org/)
- [Solidity docs](https://docs.soliditylang.org/en/v0.8.19/)

## DYOR Questions

<Quiz questionId="685cf7f3-aafe-4199-a40e-06256a9191f9" />
<Quiz questionId="36ea5014-f51e-4fb3-8fa2-027062b1c895" />

<SubmitQuiz />
