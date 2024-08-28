# 🌐 Spring Boot Google OAuth2 Sign-In App

This Spring Boot application demonstrates how to implement Google OAuth2 Sign-In functionality. It allows users to log in using their Google account and displays basic user details upon successful authentication.

## ✨ Features

- 🔒 **Google OAuth2 Authentication**: Secure login using Google accounts.
- 🖥️ **Simple User Interface**: An index page with a "Login with Google" button.
- 📄 **User Details Display**: Shows basic information of the signed-in user after successful authentication.

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### 📋 Prerequisites

1. **Java 8 or later** - [Download here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
2. **Maven** - [Download here](https://maven.apache.org/download.cgi)
3. **Google Developer Account** - [Sign up here](https://developers.google.com/identity/sign-in/web/sign-in)

### 🛠️ Setting Up Google OAuth2 Credentials

To enable Google Sign-In for your app, you need to create OAuth2 credentials in the Google Developer Console:

1. Go to the [Google Developer Console](https://console.developers.google.com/).
2. **Create a new project** by clicking the dropdown in the top menu and selecting "New Project."
3. **Navigate to the "OAuth consent screen"** tab and configure your app's consent screen. Fill in the required fields (app name, user support email, etc.).
4. **Go to the "Credentials" tab** and click on **"Create Credentials" > "OAuth 2.0 Client IDs"**.
5. **Configure the OAuth consent screen** (if not already configured). You may need to set up a test user list.
6. Set the **"Application type"** to **"Web application."**
7. Add the following **"Authorized redirect URIs"**: `http://localhost:8080/login/oauth2/code/google`.
8. Click **"Create"** to generate your **Client ID** and **Client Secret**.

### 🔑 Configuring Your Spring Boot Application

1. Open the `src/main/resources/application.properties` file in your project.
2. Add the following properties and replace `<YOUR_CLIENT_ID>` and `<YOUR_CLIENT_SECRET>` with the credentials you obtained from the Google Developer Console:

   ```properties
   spring.security.oauth2.client.registration.google.client-id=<YOUR_CLIENT_ID>
   spring.security.oauth2.client.registration.google.client-secret=<YOUR_CLIENT_SECRET>
   spring.security.oauth2.client.registration.google.redirect-uri=http://localhost:8080/login/oauth2/code/google
   spring.security.oauth2.client.provider.google.user-info-uri=https://www.googleapis.com/oauth2/v3/userinfo
# 🌐 Spring Boot Google OAuth2 Sign-In App

This Spring Boot application demonstrates how to implement Google OAuth2 Sign-In functionality. It allows users to log in using their Google account and displays basic user details upon successful authentication.

## ✨ Features

- 🔒 **Google OAuth2 Authentication**: Secure login using Google accounts.
- 🖥️ **Simple User Interface**: An index page with a "Login with Google" button.
- 📄 **User Details Display**: Shows basic information of the signed-in user after successful authentication.

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### 📋 Prerequisites

1. **Java 8 or later** - [Download here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
2. **Maven** - [Download here](https://maven.apache.org/download.cgi)
3. **Google Developer Account** - [Sign up here](https://developers.google.com/identity/sign-in/web/sign-in)

### 🛠️ Setting Up Google OAuth2 Credentials

To enable Google Sign-In for your app, you need to create OAuth2 credentials in the Google Developer Console:

1. Go to the [Google Developer Console](https://console.developers.google.com/).
2. **Create a new project** by clicking the dropdown in the top menu and selecting "New Project."
3. **Navigate to the "OAuth consent screen"** tab and configure your app's consent screen. Fill in the required fields (app name, user support email, etc.).
4. **Go to the "Credentials" tab** and click on **"Create Credentials" > "OAuth 2.0 Client IDs"**.
5. **Configure the OAuth consent screen** (if not already configured). You may need to set up a test user list.
6. Set the **"Application type"** to **"Web application."**
7. Add the following **"Authorized redirect URIs"**: `http://localhost:8080/login/oauth2/code/google`.
8. Click **"Create"** to generate your **Client ID** and **Client Secret**.

### 🔑 Configuring Your Spring Boot Application

1. Open the `src/main/resources/application.properties` file in your project.
2. Add the following properties and replace `<YOUR_CLIENT_ID>` and `<YOUR_CLIENT_SECRET>` with the credentials you obtained from the Google Developer Console:

   ```properties
   spring.security.oauth2.client.registration.google.client-id=<YOUR_CLIENT_ID>
   spring.security.oauth2.client.registration.google.client-secret=<YOUR_CLIENT_SECRET>
   spring.security.oauth2.client.registration.google.redirect-uri=http://localhost:8080/login/oauth2/code/google
   spring.security.oauth2.client.provider.google.user-info-uri=https://www.googleapis.com/oauth2/v3/userinfo


🏃‍♂️ Run the Application
