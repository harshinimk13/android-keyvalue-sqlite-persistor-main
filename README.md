# Credential Vault – Android Key-Value Persistence App

An Android application developed using Kotlin and XML to demonstrate key-value data persistence using SQLite. The application saves user credentials, restores saved values when the app is reopened, and provides login, home dashboard, and logout functionality.

## Aim

To develop an Android application that demonstrates data persistence using key-value storage and SQLite database management.

## Overview

Credential Vault demonstrates how an Android application can store and retrieve data locally using SQLite.

The application allows users to enter a username and password, saves the entered values to a local database, and restores previously saved values when the application is reopened.

After a successful login, the user is redirected to a home screen. The logout functionality clears the saved credentials and returns the user to the login screen.

## Objectives

1. Understand key-value data persistence in Android.
2. Implement SQLite database creation and management.
3. Store and retrieve username and password values.
4. Understand the role of `SQLiteOpenHelper`.
5. Implement automatic restoration of saved data.
6. Navigate between login and home screens.
7. Implement logout functionality to clear stored credentials.

## Technologies Used

- **Programming Language:** Kotlin
- **Development Environment:** Android Studio
- **User Interface:** XML
- **Database:** SQLite
- **Database Management:** SQLiteOpenHelper
- **UI Components:** Android Activities and Material Design components
- **Build System:** Gradle

## Features

### 1. Login Screen

Provides input fields for entering a username and password.

### 2. Real-Time Data Persistence

Saves the entered username and password to the SQLite database as the user types.

### 3. Automatic Data Restoration

Retrieves previously saved values from SQLite and populates the login fields when the application is reopened.

### 4. Key-Value Storage

Stores each value using a unique key, allowing individual values to be retrieved and updated.

### 5. Home Dashboard

Redirects the user to the home screen after successful login and displays a welcome message.

### 6. Logout Functionality

Clears the saved credentials and returns the user to the login screen.

### 7. User-Friendly Interface

Provides a clean interface with input fields, buttons, and Material Design components.

## Application Workflow

1. Launch the application.
2. The login screen appears.
3. Previously saved credentials are retrieved from SQLite, if available.
4. Enter or modify the username and password.
5. The application saves the entered values to the database.
6. Click the Login button.
7. After successful login, the home dashboard appears.
8. Click Logout to clear the saved credentials and return to the login screen.

## Database Architecture

The application uses an SQLite database named `UserCredentials.db`.

### Database Table: `credentials`

| Column Name | Data Type | Constraint | Description |
|---|---|---|---|
| `key_name` | TEXT | PRIMARY KEY | Unique identifier for each stored value |
| `value_text` | TEXT | As defined in the database schema | Value associated with the key |

### Example Key-Value Records

| key_name | value_text |
|---|---|
| saved_username | Example username |
| saved_password | Example password |

The values above are examples to explain the database structure, not actual credentials.

### Database Operations

The application demonstrates the following database operations:

- **Create:** Creates the database and table when required.
- **Insert or Update:** Stores new values or updates existing values.
- **Read:** Retrieves saved values when the application starts.
- **Delete:** Removes saved credential records during logout.

The database is managed through `SQLiteOpenHelper`.

## Key-Value Persistence Concepts

Android supports different approaches to local key-value persistence.

### SQLite

SQLite stores data in database tables and supports structured queries, inserts, updates, and deletions.

In this project, SQLite is used to persist the username and password.

### SharedPreferences

`SharedPreferences` is another Android mechanism for storing small amounts of data as key-value pairs, such as application settings and simple preferences.

It is a useful concept to understand when comparing Android persistence mechanisms. The application's implemented credential-storage functionality should be described according to the actual source code.

## Project Structure

```text
android-keyvalue-sqlite-persistor-main/
├── app/
│   └── src/
│       └── main/
│           ├── java/com/example/exp9/
│           │   ├── MainActivity.kt
│           │   ├── HomeActivity.kt
│           │   └── CredentialDatabaseHelper.kt
│           ├── res/
│           │   ├── layout/
│           │   │   ├── activity_main.xml
│           │   │   └── activity_home.xml
│           │   └── values/
│           │       ├── colors.xml
│           │       └── strings.xml
│           └── AndroidManifest.xml
├── gradle/
├── build.gradle.kts
├── settings.gradle.kts
├── gradle.properties
├── gradlew
├── gradlew.bat
└── README.md
```

*Note: This is the expected structure based on the project's current documentation. Additional files may exist in your actual project.*

## Implementation Details

### SQLiteOpenHelper

`CredentialDatabaseHelper.kt` manages the SQLite database, including database creation and database operations.

### MainActivity

`MainActivity.kt` manages the login interface, retrieves saved values, saves user input, and handles login interactions.

### HomeActivity

`HomeActivity.kt` displays the home dashboard and handles logout functionality.

### XML Layouts

- `activity_main.xml` defines the login screen.
- `activity_home.xml` defines the home dashboard.

## Testing and Test Cases

| Test Case | Scenario | Expected Result |
|---|---|---|
| TC01 | Launch the application | Login screen appears |
| TC02 | Enter a username | Username is saved according to the implemented persistence logic |
| TC03 | Enter a password | Password is saved according to the implemented persistence logic |
| TC04 | Restart the application | Previously saved values are restored |
| TC05 | Log in with valid input | Home dashboard appears |
| TC06 | Click Logout | Saved credentials are cleared and the login screen appears |
| TC07 | Reopen the application after logout | Previously cleared credentials are not restored |

**Note:** Verify each test case on your device or emulator before marking it as passed.

## How to Build and Run

1. Clone or download this repository.
2. Open the project in Android Studio.
3. Allow Gradle synchronization to complete.
4. Select an Android emulator or connect an Android device.
5. Run the application using the Run button or `Shift + F10`.
6. Test the login, persistence, restoration, and logout functionality.

## Concepts Learned

Through this project, the following concepts are demonstrated:

1. Android application development using Kotlin.
2. Designing interfaces using XML.
3. SQLite database creation and management.
4. Key-value data persistence.
5. Using `SQLiteOpenHelper`.
6. Inserting, retrieving, updating, and deleting database records.
7. Maintaining data across application restarts.
8. Navigating between Android Activities.
9. Comparing SQLite with SharedPreferences.

## Result

Thus, the Credential Vault Android application demonstrates local key-value data persistence using SQLite, automatic restoration of saved values, navigation between login and home screens, and credential clearing during logout.
