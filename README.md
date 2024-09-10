ETH Deposit Tracker
The ETH Deposit Tracker is a TypeScript-based application designed to monitor Ethereum deposits on the blockchain. It efficiently tracks deposit transactions, stores them in a MongoDB database, and sends notifications via Telegram whenever new deposits are detected.

Prerequisites
Before starting with the ETH Deposit Tracker, ensure you have the following installed and properly configured:

Node.js: Version 14 or later.
npm: Version 6 or later (comes bundled with Node.js).
MongoDB: Ensure MongoDB is installed and running on port 27017.
MongoDB Installation
If MongoDB is not already installed on your system, follow the instructions below based on your operating system:

macOS (using Homebrew):

Tap the MongoDB Homebrew Tap:

bash
Copy code
brew tap mongodb/brew
Install MongoDB Community Edition:

bash
Copy code
brew install mongodb-community@6.0
Start MongoDB as a Service:

bash
Copy code
brew services start mongodb/brew/mongodb-community
MongoDB should now be running, and you can connect to it using the default port 27017.

Windows:

Download MongoDB Installer:

Visit the MongoDB Download Center and download the installer for Windows.
Run the Installer:

Follow the installation instructions in the installer. Choose the "Complete" setup option.
Start MongoDB:

bash
Copy code
mongod
MongoDB will be available on port 27017 by default.

Linux:

Import the MongoDB Public GPG Key:

bash
Copy code
sudo apt-get install -y gnupg
wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | sudo apt-key add -
Add MongoDB Repository:

bash
Copy code
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu $(lsb_release -cs) mongodb-org 6.0" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
Install MongoDB:

bash
Copy code
sudo apt-get update
sudo apt-get install -y mongodb-org
Start MongoDB:

bash
Copy code
sudo systemctl start mongod
MongoDB should now be running on port 27017.

Available Scripts
In the project directory, you can run the following commands:

npm run build:

Compiles the TypeScript code into JavaScript. This step is essential before running the application to ensure that all TypeScript files are converted and ready for execution.
npm run dev:

Starts the application in development mode. This command typically includes features such as live-reloading, which automatically restarts the application when changes are made to the code.
Architecture
The ETH Deposit Tracker follows Clean Architecture principles along with SOLID design principles to ensure a well-structured, maintainable, and scalable system. Here’s an overview of the architecture:

Clean Architecture:

Entities:

These represent the core business logic and domain models of the application. They are the fundamental objects and concepts within the system.
Use Cases:

Application-specific business rules that define how the system should operate. Use cases interact with entities to perform tasks and operations.
Interface Adapters:

This layer includes presenters, controllers, and gateways that handle communication between the core application logic and external systems. It adapts data and processes it for use by other layers.
Frameworks and Drivers:

External frameworks and tools such as databases, web frameworks, and third-party APIs. These components are used by the application but are not tightly coupled to the core business logic.
SOLID Principles:

Single Responsibility Principle:

Each class or module in the system has a single responsibility or reason to change. This helps in maintaining a clean and modular codebase.
Open-Closed Principle:

The system is designed to be open for extension but closed for modification. New features or changes can be introduced with minimal alterations to existing code.
Liskov Substitution Principle:

Subtypes or subclasses should be replaceable for their base types without altering the correctness of the application. This ensures that objects can be substituted seamlessly.
Interface Segregation Principle:

Interfaces are designed to be client-specific, avoiding forcing clients to depend on interfaces they do not use. This promotes more focused and manageable interfaces.
Dependency Inversion Principle:

High-level modules depend on abstractions rather than concrete implementations. This helps in reducing coupling between different parts of the application.
Flexibility
The ETH Deposit Tracker is designed with flexibility in mind. It can be easily configured to monitor deposits for various tokens from different blockchains. This is achieved through a modular approach where different contexts can be configured for each cryptocurrency or blockchain. This design allows for straightforward expansion and support for additional cryptocurrencies and blockchains without requiring significant changes to the core architecture.

Changes in .env File
The .env file is used to store environment-specific configuration variables. To configure your project, you will need to add the following entries to the .env file:

ETH_RPC_URL: The URL of the Ethereum RPC provider (e.g., Infura or Alchemy).

Example:
ETH_RPC_URL=https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID
MONGO_URI: The connection string for MongoDB.

Example:
MONGO_URI=mongodb://localhost:27017/eth-deposit-tracker
TELEGRAM_BOT_TOKEN: The token for the Telegram bot used for notifications.

Example:
TELEGRAM_BOT_TOKEN=your-telegram-bot-token
TELEGRAM_CHAT_ID: The chat ID for receiving notifications on Telegram.

Example:
TELEGRAM_CHAT_ID=your-chat-id
Make sure to replace placeholder values with your actual credentials and connection details.
