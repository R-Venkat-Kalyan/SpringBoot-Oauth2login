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

### 🔗 Key Points About Redirect URIs

**Authorized Redirect URIs** are the URLs that Google will redirect to after a user successfully authenticates. It is crucial to match the redirect URIs configured in your Spring Boot application with those authorized in the Google Developer Console. Here’s why:

- **Security**: Only authorized URIs will receive the authentication code from Google. This prevents malicious sites from intercepting sensitive data.
- **Default URI Handling**: Spring Security uses a default endpoint pattern like `/login/oauth2/code/google` for handling OAuth2 login responses. You must include this exact URI (e.g., `http://localhost:8080/login/oauth2/code/google`) in your authorized redirect URIs.
- **Flexibility**: You can list multiple URIs to support various environments (development, staging, production). However, each environment's redirect URI must be explicitly listed in Google’s settings to function correctly.

**Add the following "Authorized redirect URIs"**:

- `http://localhost:8080/login/oauth2/code/google`
- `https://localhost:8080/login/oauth2/code/google`

7. Click **"Create"** to generate your **Client ID** and **Client Secret**.

### 🔑 Configuring Your Spring Boot Application

1. Open the `src/main/resources/application.properties` file in your project.
2. Add the following properties and replace `<YOUR_CLIENT_ID>` and `<YOUR_CLIENT_SECRET>` with the credentials you obtained from the Google Developer Console:

   ```properties
   spring.security.oauth2.client.registration.google.client-id=<YOUR_CLIENT_ID>
   spring.security.oauth2.client.registration.google.client-secret=<YOUR_CLIENT_SECRET>
   spring.security.oauth2.client.registration.google.redirect-uri=http://localhost:8080/login/oauth2/code/google
   spring.security.oauth2.client.provider.google.user-info-uri=https://www.googleapis.com/oauth2/v3/userinfo

# 🏃‍♂️ Run the Application

Now, you are all set to run your Spring Boot application and test the Google OAuth2 Sign-In functionality.

## 📦 How to Clone and Run the App

Follow these steps to clone and run the application on your local machine:

### Clone the Repository

Open your terminal and run the following command to clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   mvn clean install
   mvn spring-boot:run

**Access the Application**
Open your web browser and go to http://localhost:8080. You should see the home page with the "Login with Google" button.

**Log in with Google**
Click the "Login with Google" button and follow the instructions to log in with your Google account. After successful authentication, you should be redirected to the welcome page displaying your user details.
