# ZK SNARK Designer Circuit

A simple circuit template that checks whether the variable 'c' is the multiplication of variables 'a' and 'b'.

## Description

This project contains a CIRCOM circuit template that demonstrates how to check if the value of 'c' is the result of multiplying 'a' and 'b'. The circuit is composed of basic logic gates like AND, NOT, and OR, which are combined to implement the multiplication check.

## Getting Started

### Installing

To use this circuit, follow these steps:

1. Clone or download the project to your local machine.
2. Install
`npm i`

### Executing the Program

To run the circuit, you need to have a CIRCOM compiler installed. Once you have the compiler installed, follow these steps:

1. Navigate to the directory containing the downloaded project.
2. Open the terminal and execute the following command to compile the circuit:
3. Compile
`npx hardhat circom` 
This will generate the **out** file with circuit intermediaries and geneate the **MultiplierVerifier.sol** contract
4. Prove and Deploy
`npx hardhat run scripts/deploy.ts`
This script does 4 things  
1. Deploys the MultiplierVerifier.sol contract
2. Generates a proof from circuit intermediaries with `generateProof()`
3. Generates calldata with `generateCallData()`
4. Calls `verifyProof()` on the verifier contract with calldata

## Configuration
**contracts**
```
contracts
└── MultiplierVerifier.sol
```
Verifier contracts are autogenerated and prefixed by the circuit name, in this example **Multiplier**

## hardhat.config.ts
```
  circom: {
    // (optional) Base path for input files, defaults to `./circuits/`
    inputBasePath: "./circuits",
    // (required) The final ptau file, relative to inputBasePath, from a Phase 1 ceremony
    ptau: "powersOfTau28_hez_final_12.ptau",
    // (required) Each object in this array refers to a separate circuit
    circuits: JSON.parse(JSON.stringify(circuits))
  },
```
After compiling the circuit, you can use the compiled JSON circuit file in other applications that support the CIRCOM circuit format.

## Help

If you encounter any issues or have questions, feel free to [open an issue](https://github.com/22bct10008/Polygon-Advanced_Module-3-Project/issues) on this project's GitHub repository.

## Authors

- E Mohith
- 22bct10008@cuchd.in

## License

This project is licensed under the [MIT License](LICENSE.md).



