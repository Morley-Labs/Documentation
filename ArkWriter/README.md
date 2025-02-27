# ArkWriter

ArkWriter is a graphical editor for creating and deploying Ladder Logic-based smart contracts on Cardano. It bridges the gap between traditional automation engineering and blockchain development, enabling engineers and developers to design, visualize, and deploy smart contracts using a familiar Ladder Logic interface. The project is an integral part of the Morley ecosystem and is in its early stages of development.

## Overview

ArkWriter is designed to:
- Provide a graphical Ladder Logic editor for smart contract creation.
- Support deploying contracts as Plutus scripts on Cardano.
- Enable versioning and migration of contract UTXOs through ArkRedeem.
- Offer a visualization modal that converts contracts into Ladder Logic diagrams.

Currently, ArkWriter is functional but still evolving. It allows users to create and deploy basic Ladder Logic-based contracts, but many advanced features are still under development.

## Current Status

ArkWriter is a work in progress. At present, it:
- Provides a drag-and-drop interface for building Ladder Logic diagrams poorly. Major refactoring in the grid system is required.
- Compiles Ladder Logic into Plutus scripts for deployment on Cardano.
- Includes ArkRedeem for contract versioning and UTXO migration.
- Supports basic visualization of contracts as Ladder Logic diagrams.

However, the tool has limitations:
- The user interface is functional but lacks advanced styling and features.
- The visualization modal is basic and needs improvement for better representation.
- Versioning and UTXO migration features are still being refined.
- Support for complex Ladder Logic constructs is limited.

## Roadmap

ArkWriter aims to become a comprehensive Ladder Logic-based smart contract editor and deployment tool. Future plans include:
- Enhancing the user interface for better usability and aesthetics.
- Expanding support for complex Ladder Logic constructs.
- Improving the visualization modal for more detailed contract diagrams.
- Integrating with other Morley tools for a seamless development workflow.
- Adding more advanced versioning and UTXO migration features.

## Contributing

We welcome contributions from the community. If you have ideas, feedback, or would like to help with development, feel free to open an issue or submit a pull request.

## Disclaimer

ArkWriter is an experimental project and is not yet production-ready. The tool is under active development, and features may change frequently. Users should exercise caution when deploying contracts created with ArkWriter.

## Acknowledgments

ArkWriter is developed as part of the Morley project ecosystem. Special thanks to the Cardano community for their ongoing support and inspiration.
