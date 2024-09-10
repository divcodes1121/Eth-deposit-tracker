# **Ethereum (ETH) Deposit Tracker**

## **Objective**

The goal of this project is to create a robust Ethereum Deposit Tracker that monitors and records Ethereum (ETH) deposits on the Beacon Deposit Contract. The system will efficiently track deposits, handle notifications, and provide a clear overview of deposit activities.

## **Table of Contents**

- [Objective](#objective)
- [Examples of Deposits](#examples-of-deposits)
- [Project Components](#project-components)
  - [Language](#language)
  - [RPC Integration](#rpc-integration)
  - [Deposit Tracking Logic](#deposit-tracking-logic)
  - [Alerting and Notifications](#alerting-and-notifications)
  - [Error Handling and Logging](#error-handling-and-logging)
  - [Documentation](#documentation)
- [Schema of Deposit](#schema-of-deposit)
- [Deliverables](#deliverables)
- [Setup Development Environment](#setup-development-environment)
- [Usage Instructions](#usage-instructions)

## **Examples of Deposits**

Here are examples of Ethereum deposit transactions:

- **Normal Transaction**: `0x1391be19259f10e01336a383217cf35344dd7aa157e95030f46235448ef5e5d6`
- **Internal Transaction**: `0x53c98c3371014fd54275ebc90a6e42dffa2eee427915cab5f80f1e3e9c64eba4`

These examples showcase different types of transactions that the tracker will monitor.

## **Project Components**

### **Language**

- **TypeScript (TS)**: The project is built using TypeScript. TypeScript provides static typing, which helps in detecting errors early and improves code reliability and maintainability.

### **RPC Integration**

- **Establish an RPC Connection**:
  - Choose a provider to connect to an Ethereum node. This can be a service like Infura or Alchemy, or a local Ethereum node you set up yourself.
  - Set up the connection by providing the necessary API keys or endpoint URLs.

- **Develop Functions for Data Fetching**:
  - Create functions that use Ethereum RPC methods to fetch transaction data.
  - Ensure these functions can handle real-time data and efficiently process incoming transactions.

- **Parse and Filter Transactions**:
  - Extract relevant information from the fetched data to identify ETH deposits.
  - Filter out non-relevant transactions and focus on deposits.

### **Deposit Tracking Logic**

- **Monitor the Beacon Deposit Contract**:
  - Track the Beacon Deposit Contract address: `0x00000000219ab540356cBB839Cbe05303d7705Fa`.
  - Implement logic to continuously check for incoming ETH deposits.

- **Record and Store Deposit Details**:
  - Develop functionality to record key deposit details such as amount, sender address, and timestamp.
  - Store these details in a database for further analysis.

- **Handle Multiple Deposits**:
  - Ensure the system can manage multiple deposits within a single transaction, including internal transactions.

### **Alerting and Notifications**

- **Integrate Alerting Mechanisms**:
  - Set up notifications to alert you when new deposits are detected.
  - Use tools like Telegram for immediate alerts.

- **Grafana Dashboard**:
  - Create a Grafana dashboard to visualize deposit data and system metrics.
  - Configure the dashboard to provide real-time updates and insights.

- **Telegram Notifications**:
  - Implement Telegram notifications to send alerts directly to users.

### **Error Handling and Logging**

- **Comprehensive Error Handling**:
  - Implement error handling for API calls and RPC interactions to manage potential issues effectively.

- **Logging Mechanisms**:
  - Add logging to track errors and significant events within the application.
  - Ensure logs are easy to review and analyze for debugging purposes.

### **Documentation**

- **Setup Process Documentation**:
  - Provide clear instructions on setting up the project environment, including configuring dependencies and environment variables.

- **Usage Instructions**:
  - Create detailed usage instructions to help users understand how to run and operate the Ethereum Deposit Tracker.

- **Codebase Comments**:
  - Include comments within the code to explain functionality and improve readability.

## **Schema of Deposit**

Here is the schema for a deposit record:

```typescript
Deposit {
    blockNumber: number;       // The block number where the deposit occurred
    blockTimestamp: number;    // The timestamp of the block
    fee?: number;              // (Optional) The transaction fee, if applicable
    hash?: string;             // (Optional) The transaction hash
    pubkey: string;            // The public key associated with the deposit
}
