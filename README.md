# Integrating Immutable Passport into Your Application

Welcome to the guide on how to integrate Immutable Passport into your application. Immutable Passport simplifies user authentication and provides access to Immutable's blockchain-based ecosystem.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Getting Started](#getting-started)
   - [Creating a Simple Application](#creating-a-simple-application)
   - [Cloning a Sample Repository](#cloning-a-sample-repository)
3. [Registering Your Application on Immutable Developer Hub](#registering-your-application)
4. [Installing and Initializing the Passport Client](#installing-and-initializing-the-passport-client)
5. [Logging In a User with Passport](#logging-in-a-user)
6. [Displaying User Information](#displaying-user-information)
7. [Logging Out a User](#logging-out-a-user)
8. [Initiating a Transaction from Passport](#initiating-a-transaction)
9. [Sample Application](#sample-application)

## 1. Prerequisites

Before you begin, make sure you have the following prerequisites:

- A basic application (if not, you can clone the sample repository).
- An Immutable Developer Hub account.
- API keys and secrets obtained from Immutable Developer Hub.

## 2. Getting Started

### 2.1 Creating a Simple Application

If you don't have an existing application, create one using your preferred programming language and framework. Your application should have the following prerequisites:

- Dependencies for web development (e.g., Node.js, npm, or a web framework).
- A user interface to accommodate user interactions.

### 2.2 Cloning a Sample Repository

To expedite the process, you can clone our [Sample Passport Integration Repository](https://github.com/immutable/sample-passport-integration). This repository provides a basic application with Immutable Passport integration. You can use it as a starting point for your project.

## 3. Registering Your Application on Immutable Developer Hub

To integrate Immutable Passport, you need to register your application on the Immutable Developer Hub. Here's how:

1. Visit the [Immutable Developer Hub](https://developer.immutable.com/).
2. Create an account or log in if you already have one.
3. Navigate to the "Applications" section.
4. Click "Create Application" and follow the on-screen instructions to set up your application.
5. Once your application is registered, you'll receive API keys and secrets. Keep these credentials secure as you will need them for integration.

## 4. Installing and Initializing the Passport Client

The Passport client library enables your application to interact with Immutable Passport. Here's how to install and initialize it:

**Installation**

Install the Passport client library using npm:

```bash
npm install immutable-passport-client

**Initialization**

In your application code, initialize the Passport client with your API keys and secrets:

const { PassportClient } = require('immutable-passport-client');

const passport = new PassportClient({
  apiKey: 'YOUR_API_KEY',
  apiSecret: 'YOUR_API_SECRET',
});

This code configures the Passport client with your Immutable Passport credentials, allowing you to interact with the Immutable ecosystem.

## 5. Logging In a User with Passport

Immutable Passport enables users to log in using their Immutable accounts. Here's how to initiate the login process:

Login Function

## Define a function to handle user login with Immutable Passport


async function loginWithPassport() {
  try {
    const { user, tokens } = await passport.login(); // Initiating the login process
    console.log('User:', user);
    console.log('Tokens:', tokens);
  } catch (error) {
    console.error('Login failed:', error);
  }
}


## 6. Displaying User Information
Once a user is logged in, you can access and display user information such as the ID token, access token, and user's nickname. Update your user interface to show this information:

console.log('User ID:', user.id);
console.log('User Nickname:', user.nickname);
console.log('ID Token:', tokens.idToken);
console.log('Access Token:', tokens.accessToken);

This code snippet demonstrates how to access and display user details in your application. You can customize your UI to present this information as required.

### 7. Logging Out a User
To allow users to log out, you can use the logout method provided by the Passport client:

passport.logout();
console.log('User logged out.');

## 8. Initiating a Transaction from Passport
Immutable Passport can be used to initiate blockchain transactions. For example, you can send a placeholder string and obtain the transaction hash:

Transaction Function

Define a function to initiate a transaction using Immutable Passport:

async function initiateTransaction() {
  try {
    const transactionHash = await passport.sendTransaction('YOUR_PLACEHOLDER_STRING');
    console.log('Transaction Hash:', transactionHash);
  } catch (error) {
    console.error('Transaction failed:', error);
  }
}

## 9. Sample Application
You can explore a sample application with Immutable Passport integration in our Sample Passport Integration Repository. This repository contains a basic app that demonstrates the integration steps covered in this guide.

Feel free to modify and expand the sample application to meet your specific requirements.

That's it! You've successfully integrated Immutable Passport into your application, enabling users to authenticate, access their information, and interact with Immutable's blockchain ecosystem.

