# Coffee Supply Chain - Hyperledger Fabric

A blockchain-based coffee supply chain management system built on Hyperledger Fabric that tracks coffee beans from farm to retail.

## Overview

This project implements a complete coffee supply chain solution using Hyperledger Fabric blockchain technology. It enables transparent tracking of coffee beans through various stages: supplier → farmer → processor → roaster → retailer.

## Architecture

- **Chaincode**: Smart contracts written in Go for supply chain logic
- **Adapter**: Node.js/TypeScript API layer for blockchain interaction
- **Network**: Multi-organization Hyperledger Fabric network
- **Database**: ScyllaDB for off-chain data storage

## Components

### 1. Chaincode (Smart Contracts)
- **Farmer Contract**: Manages farmer operations and coffee bean records
- **Processor Contract**: Handles coffee processing and quality checks
- **Retailer Contract**: Manages retail operations and final product tracking
- **Supplier Contract**: Tracks supplier information and initial bean sourcing

### 2. Adapter Layer
- RESTful API endpoints for all supply chain operations
- User authentication and authorization
- Blockchain transaction handling
- Database integration for off-chain data

### 3. Network Infrastructure
- Multi-organization Fabric network
- Certificate Authority (CA) for identity management
- Orderer service for transaction ordering
- Peer nodes for each organization

## Prerequisites

- Docker and Docker Compose
- Node.js 16+ and npm
- Go 1.15+
- Hyperledger Fabric binaries

## Quick Start

### 1. Start the Network
```bash
cd deployment
./start_all_prereq.sh
./start_all_component.sh
```

### 2. Deploy Chaincode
```bash
cd chaincode/deployment
./deploy.sh
```

### 3. Start the API
```bash
cd adapter
npm install
npm run build
npm start
```

## API Endpoints

The system provides REST APIs for:
- User management and authentication
- Batch creation and tracking
- Supply chain operations
- Transaction history

## Testing

Use the provided Postman collection (`postman_collection.json`) to test the API endpoints.

## Project Structure

```
├── adapter/           # Node.js API layer
├── chaincode/         # Go smart contracts
├── deployment/        # Network deployment scripts
└── postman_collection.json  # API testing collection
```

## License

This project is licensed under the ISC License.
