November 2022

Proposed Topic: Interfaces

Goal: Identify two instances of interfaces being used and summarize respectively why one might want to implement them

Demonstration: Your own contract, however rudimentary you choose, alongside an interface that it inherits from

Questions

1. What does inheriting from an interface accomplish?

If you wanted to use a function defined in another contract, you'd have to inherit that contract, and that contract's functions must be able to be overriden. Functions in an interface are natively virtual and you can attach your own logic to them with ease.

2. How does a contract that implements an interface derived from itself benefit from that inheritance?

A contract that inherits from an interface with the same name, is a convention to promote code reusability. You can't inherit from a deployed contract, but you can ensure a contract follows the skeleton of another contract by inheriting its interface.

Interfaces sit between dapps and their respective contracts as mediums of interacting with the underlying logic.

--

Interface Instances


1. ISoundEditionV1.sol https://github.com/soundxyz/sound-protocol/blob/main/contracts/core/interfaces/ISoundEditionV1.sol

- This interface inherits from another interface IERC721AUpgradeable, created by Chiru Labs. By inheriting this interface the NFT tokens from the Sound protocol will conform to the standard defined by Chiru Labs and benefit from the gas saving techniques they've introduced.

Remaining Questions

- The functions defined in ERC721AUpgradeable.sol are all capable of being overriden. You can find the contract here https://github.com/chiru-labs/ERC721A-Upgradeable/blob/main/contracts/ERC721AUpgradeable.sol. What is the advantage of inheriting from the interface over this implementation, which itselfs inherits from its namesake interface?


2. Curator.sol https://github.com/public-assembly/curation-protocol/blob/main/src/Curator.sol

- This contract imports an interface named ICuratorFactory. By importing this interface, a state variable called curatorFactory can then be declared that takes the shape of that interface.

Remaining Questions

- If the imported contract were not an interface, and instead the base implementation of CuratorFactory, what would change?


Demonstration

- The files can be found within the src folder, look for Counter.sol alongside ICounter.sol

Remaining Questions

- If a state variable is defined in your base contract, in this case "number", is it necessary to write a getter function in the accompanying interface?
