# Postman API Automation Tests

![Postman Tests](https://github.com/JBxrajas/postman-api-auto-tests/actions/workflows/postman-tests.yml/badge.svg)

Automated API testing using Postman collections with Newman, integrated with GitHub Actions for continuous testing and reporting.

##  Overview

This repository contains automated API tests for the Swagger PetStore API, demonstrating best practices for API automation testing with Postman collections.

##  Test Collection

- **PetStore Practice** - Comprehensive test suite covering:
  - Pet management endpoints (Create, Read, Update, Delete)
  - Store order operations
  - User management

##  Features

- ✅ Automated API testing with Postman/Newman
- ✅ GitHub Actions CI/CD integration
- ✅ HTML test reports with detailed metrics
- ✅ GitHub Pages deployment for report viewing
- ✅ Environment and global variable management
- ✅ Automatic test execution on push/PR

##  View Test Reports

Latest test results are automatically published to GitHub Pages:

 **[View Live Test Reports](https://jbxrajas.github.io/postman-api-auto-tests/)**

##  Project Structure

```
postman-api-auto-tests/
├── .github/
│   └── workflows/
│       └── postman-tests.yml      # GitHub Actions workflow
├── postman/
│   ├── collections/
│   │   └── PetStore Practice.postman_collection.json
│   ├── environments/
│   │   └── PetStorePROD.postman_environment.json
│   ├── globals/
│   │   └── workspace.postman_globals.json
│   └── specs/
│       └── Activation Service APIs.json
├── index.html                      # GitHub Pages landing page
└── README.md
```

##  Running Tests Locally

### Prerequisites

- Node.js (v14 or higher)
- npm

### Installation

```bash
# Install Newman globally
npm install -g newman newman-reporter-htmlextra
```

### Run Tests

```bash
# Run the PetStore collection
newman run "postman/collections/PetStore Practice.postman_collection.json" \
  -e postman/environments/PetStorePROD.postman_environment.json \
  -g postman/globals/workspace.postman_globals.json \
  --reporters cli,htmlextra \
  --reporter-htmlextra-export newman-report.html
```

The HTML report will be generated as `newman-report.html` in your current directory.

##  GitHub Actions Workflow

The workflow automatically:

1. **Runs on**: Push to `main`/`develop`, Pull Requests, or manual trigger
2. **Executes**: Newman tests with the PetStore collection
3. **Generates**: HTML test report with detailed metrics
4. **Uploads**: Report as workflow artifact
5. **Deploys**: Results to GitHub Pages for easy viewing

##  Environment Variables

### PetStorePROD Environment

- `BASEURL`: `https://petstore.swagger.io/v2`

Additional environment variables can be added in the environment file as needed.

##  Test Scenarios

Current test coverage includes:

- ✅ Create new pet with validation
- ✅ Retrieve pet by ID
- ✅ Create store order
- ✅ User creation with list
- ✅ User deletion

##  Contributing

1. Fork the repository
2. Create a feature branch
3. Add/modify test collections
4. Commit your changes
5. Push to your branch
6. Open a Pull Request

##  License

This project is open source and available for educational purposes.

##  Links

- [Postman Documentation](https://learning.postman.com/)
- [Newman Documentation](https://github.com/postmanlabs/newman)
- [Swagger PetStore API](https://petstore.swagger.io/) 
