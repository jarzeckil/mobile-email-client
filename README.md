# Mobile Email Client

A robust and secure mobile email application built with **Flutter**, designed to handle complex mail operations efficiently. This project demonstrates a full-featured email client implementation supporting **IMAP** and **SMTP** protocols, local data persistence, and automatic server configuration discovery.

---

## 🚀 Overview

This application serves as a comprehensive email client allowing users to manage their electronic correspondence directly from their mobile devices. It was engineered to solve common challenges in mobile mail apps, such as handling asynchronous network streams, managing secure authentication, and ensuring offline accessibility through local caching.

**Key capabilities include:**
* **Universal Connectivity**: Connects to major email providers via standard IMAP/SMTP protocols.
* **Intelligent Setup**: Utilizes auto-discovery to automatically configure server settings based on the email domain.
* **Offline Access**: Persists emails locally using SQLite, allowing users to view messages without an active internet connection.
* **Real-time Updates**: Implements mail polling to fetch new messages as they arrive.

## 🛠️ Tech Stack & Libraries

The project leverages a modern ecosystem of Dart packages to ensure performance and maintainability:

* **Core Framework**: [Flutter](https://flutter.dev/) (SDK ^3.7.2)
* **Email Protocols**: [`enough_mail`](https://pub.dev/packages/enough_mail) - Handles low-level IMAP/SMTP commands and MIME parsing.
* **Local Database**: [`sqflite`](https://pub.dev/packages/sqflite) - SQL-based storage for caching emails and user data.
* **State Management**: [`provider`](https://pub.dev/packages/provider) - Efficient state management and dependency injection.
* **Security & Storage**:
    * [`encrypt`](https://pub.dev/packages/encrypt) - For encrypting sensitive user credentials.
    * [`shared_preferences`](https://pub.dev/packages/shared_preferences) - For managing simple persistent data like user settings.

## ✨ Features

### Implemented
- **Secure Authentication**: User login with automatic server configuration discovery (Auto-config).
- **Mail Composition**: Rich text email composition and sending via SMTP.
- **Inbox Management**: IMAP-based mail fetching with support for pagination and history loading.
- **Local Caching**: Incoming messages are saved to a local SQLite database for instant retrieval and offline viewing.
- **Background Polling**: Service-based architecture to listen for incoming emails.

## 🏗️ Architecture

The project follows a **Service-Oriented Architecture (SOA)** with a clean separation of concerns:

1.  **UI Layer**: Flutter widgets responsible for presentation.
2.  **Service Layer**: The `MailService` singleton manages all network communication, decoupling the UI from protocol implementations.
3.  **Data Layer**: `DatabaseHelper` and `SharedPreferences` handle local persistence, ensuring the app remains functional offline.

## 🏁 Getting Started

To run this project locally:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/mobile_email_client.git](https://github.com/yourusername/mobile_email_client.git)
    ```
2.  **Install dependencies:**
    ```bash
    flutter pub get
    ```
3.  **Run the app:**
    ```bash
    flutter run
    ```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
