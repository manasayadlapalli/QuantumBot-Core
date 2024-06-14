# QuantumBot-Core

## Firebase Functions and Chatbot Rex Setup

- **Introduction**
  - This project involves setting up a development environment for Firebase functions and building services like a chatbot. The following points guide you through the setup process, folder structure, API creation, testing, and final submission.

- **Setting Up Development Environment**
  - Install Node.js
    - Visit [Node.js](https://nodejs.org) and download the Node.js installer.
    - Ensure to select npm during the installation process.
  - Verify Node.js Installation
    - Open VS Code terminal.
    - Run `node --version` to verify the installation.
  - Install Firebase Tools
    - Run `npm install -g firebase-tools` to install Firebase CLI tools.
  - Login to Firebase
    - Run `firebase login` to authenticate your Firebase account.
  - Create Firebase Project
    - Visit [Firebase Console](https://console.firebase.google.com/).
    - Create a new project or use an existing one.
    - Copy the Project ID from the Firebase console.
  - Configure Firebase Project
    - Update the `.firebaserc` file with your Project ID.
    - Modify `firebase.json` to include necessary Firebase features like functions and Firestore.
  - Initialize Firebase
    - Run `firebase init`.
    - Select Firestore and Functions.
    - Follow the prompts to complete the initialization.
  - Create Firestore Database
    - In Firebase Console, go to Build > Firestore Database.
    - Create a database in test mode.

- **Basic Folder Structure**
  - Project Structure Overview
    - **functions/**: Contains all Firebase functions.
      - **api/**: API endpoints.
      - **helpers/**: Utility functions.
      - **models/**: Data models.
      - **services/**: Business logic.
      - **index.js**: Main entry point for Firebase functions.
    - **public/**: Static files for the frontend.
    - **firebase.json**: Main configuration file.
    - **.firebaserc**: Firebase project settings.

- **Setting Up Firestore Collection and API Endpoint**
  - Create Firestore Collections
    - In Firebase Console, create a collection named `chads`.
    - Add a sub-collection named `messages`.
  - Create API Endpoint
    - Define an HTTPS function in `functions/api/addMessage.js`.
    - Validate the request fields: `text` and `userID`.
    - Construct message data with `text`, `userID`, and timestamp.
    - Add the message to the Firestore `messages` sub-collection.
    - Return a success or error response.
  - Deploy API Endpoint
    - Change Firebase plan to Blaze (pay-as-you-go).
    - Run `firebase deploy --only functions` to deploy the function.

![image](https://github.com/manasayadlapalli/QuantumBot-Core/assets/87613567/d17f85a1-0cb5-4041-8b42-5b8a0f379bdf)


- **Testing API Endpoint with Postman**
  - Install Postman
    - Download and install Postman from [Postman](https://www.postman.com/).
  - Create Workspace
    - Create a new workspace in Postman named `Chatbot`.
  - Test API Endpoint
    - Create a new HTTP POST request.
    - Set the endpoint URL from Firebase function.
    - Add headers: `Content-Type: application/json`.
    - Set request body to JSON format with appropriate data.
    - Send the request and verify the response.
    - Check Firestore database for the new message entry.
