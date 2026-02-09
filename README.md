
# pcdHHK - Blockchain Healthcare Management System

A decentralized healthcare management system built on Ethereum blockchain using Solidity smart contracts and React frontend. This system enables secure medical record management, appointment scheduling, and prescription tracking between patients, doctors, pharmacists, lab agents, and insurance employees.

> "dont push unless it works" - Project motto

## Overview

This project implements a blockchain-based Electronic Health Records (EHR) system that ensures data privacy, security, and interoperability across different healthcare stakeholders. Using smart contracts, the system provides transparent and immutable medical record management.

## Features

### For Patients
- Register and manage personal health information
- Authorize healthcare providers to access medical records
- View appointments and medical history
- Track prescriptions and test results
- Encrypted medical data storage using IPFS

### For Doctors
- Register with specialty and location
- Schedule and manage appointments
- Create medical records with diagnoses
- Issue prescriptions and order lab tests
- Access authorized patient records

### For Pharmacists
- Register pharmacy information
- Validate prescription purchases
- Track medication dispensing
- Access patient prescriptions (with authorization)

### For Lab Agents
- Manage laboratory test orders
- Upload and share test results
- Track test completion status

### For Insurance Employees
- Access patient records (with authorization)
- Approve prescription reimbursements
- Request patient data access

## Technology Stack

### Blockchain & Smart Contracts
- **Solidity** ^0.8.0 - Smart contract development
- **Truffle** - Development framework and testing
- **Web3.js** v1.2.2 - Ethereum JavaScript API
- **Ganache** - Local blockchain for development

### Frontend
- **React** ^18.2.0 - UI framework
- **React Router** ^5.2.0 - Navigation
- **Bootstrap** ^5.3.3 - Styling
- **Semantic UI React** ^2.0.3 - Additional UI components
- **AG Grid** ~31.2.1 - Data tables
- **React Toastify** ^10.0.5 - Notifications

### Storage
- **IPFS** (ipfs-mini) - Decentralized file storage for medical documents

## Project Structure

```
pcdHHK/
├── contracts/              # Solidity smart contracts
│   ├── Authentication.sol  # User authentication and role management
│   ├── patientcontract.sol # Patient data management
│   ├── docteur.sol        # Doctor functionality
│   ├── pharmacien.sol     # Pharmacist operations
│   ├── assuranceagent.sol # Insurance employee features
│   └── Migrations.sol     # Truffle migrations
├── client/                # React frontend application
│   ├── src/
│   ├── public/
│   └── package.json
├── migrations/            # Smart contract deployment scripts
├── test/                  # Contract tests
├── truffle-config.js      # Truffle configuration
└── README.md
```

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn
- Truffle: `npm install -g truffle`
- Ganache (for local development)
- MetaMask browser extension

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/houssemwld1/pcdHHK.git
   cd pcdHHK
   ```

2. **Install dependencies**
   ```bash
   # Install Truffle dependencies
   npm install

   # Install client dependencies
   cd client
   npm install
   ```

3. **Start Ganache**
   - Launch Ganache and create a new workspace
   - Note the RPC server address (default: HTTP://127.0.0.1:7545)

4. **Deploy Smart Contracts**
   ```bash
   # From root directory
   truffle migrate --reset
   ```

5. **Configure MetaMask**
   - Connect MetaMask to your local Ganache network
   - Import accounts using private keys from Ganache

6. **Start the React application**
   ```bash
   cd client
   npm start
   ```

The application will open at [http://localhost:3000](http://localhost:3000)

## Smart Contract Architecture

### Authentication Contract
- Manages user registration and role-based access control
- Defines user roles: Patient, Doctor, Researcher, Pharmacist, Lab Agent, Insurance Employee
- Stores user signatures and public keys for encryption

### Patient Contract
- Stores patient personal information
- Manages authorized healthcare providers
- Maintains medical records and appointment lists
- Stores encrypted IPFS hash of medical documents

### Doctor Contract
- Registers doctor profiles with specialties
- Manages patient lists per doctor
- Schedules and tracks appointments
- Creates prescriptions and medical records

### Pharmacist Contract
- Registers pharmacy information
- Validates prescription purchases
- Tracks medication dispensing

### Insurance Agent Contract
- Manages insurance employee profiles
- Approves prescription reimbursements
- Requests access to patient data

## Security Features

- **Role-Based Access Control**: Only authorized users can access specific functions
- **Encryption**: Medical data encrypted before storage
- **IPFS Storage**: Decentralized storage for sensitive documents
- **Blockchain Immutability**: Tamper-proof medical records
- **Patient Authorization**: Patients control who can access their data

## Testing

Run the test suite:
```bash
truffle test
```

## Available Scripts

### Root Directory
```bash
truffle compile    # Compile smart contracts
truffle migrate    # Deploy contracts
truffle test       # Run tests
truffle console    # Interactive console
```

### Client Directory
```bash
npm start          # Start development server
npm build          # Build for production
npm test           # Run tests
npm eject          # Eject from Create React App
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

**Important**: Remember the project motto - "dont push unless it works"!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## User Roles

| Role | Capabilities |
|------|-------------|
| **Patient** | Register, manage records, authorize providers, view appointments |
| **Doctor** | Register, schedule appointments, create prescriptions, access authorized records |
| **Pharmacist** | Register pharmacy, validate prescriptions, dispense medications |
| **Lab Agent** | Manage tests, upload results |
| **Insurance Employee** | Access records (authorized), approve reimbursements |
| **Researcher** | (Future implementation) |

## Future Enhancements

- Researcher role implementation
- Advanced encryption mechanisms
- Mobile application
- Integration with existing EHR systems
- AI-powered diagnosis assistance
- Multi-language support
- Telemedicine features

## Contact

Project Maintainer: [@houssemwld1](https://github.com/houssemwld1)

Repository: [https://github.com/houssemwld1/pcdHHK](https://github.com/houssemwld1/pcdHHK)

---

**Note**: This is a proof-of-concept implementation. For production use, additional security audits and compliance reviews are required.
