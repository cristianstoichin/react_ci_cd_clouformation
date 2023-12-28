# React Hello World with AWS CloudFormation and GitHub Actions CI/CD

## Introduction
Welcome to our React Hello World example repository. This project is designed to provide a simple, yet effective, demonstration of integrating a basic React application with Infrastructure as Code (IaC) using AWS CloudFormation templates, alongside a Continuous Integration and Continuous Deployment (CI/CD) pipeline facilitated by GitHub Actions.

## Project Structure
- `src/`: Contains the source code for the React application.
- `infra/`: The AWS CloudFormation templates for infrastructure setup.
- `.github/workflows/`: Contains the GitHub Actions workflow definitions for CI/CD.

## Getting Started
### Prerequisites
- Node.js and npm installed
- AWS CLI configured with appropriate permissions
- GitHub account

## Setting Up the Project
Follow these [steps](/README-App.md) to run the project locally.

## Continuous Integration and Deployment
GitHub Actions are set up for continuous integration and deployment. Upon pushing code to the repository, the GitHub Actions workflows will:
1. Install dependencies.
2. Run tests (if any).
3. Deploy the application to AWS (if on the main branch).

Infrastructure details [here](/infra/readme.md).

CI-CD details [here](/.github/workflows/readme.md).

## Contributing
We welcome contributions! Please read our [Contributing Guidelines](CONTRIBUTING.md) for more information on how you can contribute to this project.

## License
This project is licensed under the [MIT License](LICENSE).

## Contact
For any queries or suggestions, feel free to open an issue or contact the repository maintainers.

## Acknowledgements
- React Community
- AWS CloudFormation
- GitHub Actions
