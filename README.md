# Mobile Email Client

A native mobile email client built with **Flutter**.

I built this project to tackle the engineering challenges of implementing standard email protocols (IMAP/SMTP) from scratch on mobile. Unlike REST APIs, email protocols require maintaining persistent socket connections, handling complex MIME parsing, and managing state synchronization between a local database and a remote server.

## 🛠 Tech Stack

| Component       | Technology         | Reason                                                                   |
| --------------- | ------------------ | ------------------------------------------------------------------------ |
| **Framework**   | Flutter (Dart)     | Cross-platform performance, strong typing.                               |
| **Protocols**   | `enough_mail`      | Low-level handling of IMAP/SMTP commands and MIME parsing.               |
| **Persistence** | `sqflite` (SQLite) | Offline-first architecture; caching headers and bodies for instant load. |
| **State**       | `provider`         | Dependency injection and state management.                               |
| **Security**    | `encrypt`          | AES encryption for storing sensitive credentials locally.                |

## 🏗 Architecture & Key Decisions

The application follows a **Service-Oriented Architecture** to decouple the UI from the complex protocol logic.

### 1. Offline-First Strategy

The app does not rely on a constant network connection to display data.

- **Write-through caching**: Incoming emails are parsed and immediately stored in SQLite.
- **Optimistic UI**: The interface loads data from the local database first, then updates in the background when the network sync completes.

### 2. Auto-Discovery Mechanism

Configuring IMAP/SMTP ports manually is bad UX.

- I implemented an auto-discovery service that attempts to guess server settings based on the email domain (e.g., `gmail.com` -> `imap.gmail.com`).

### 3. Security

- Credentials are never stored in plain text.
- Used `encrypt` package to secure the refresh tokens/passwords before writing them to `SharedPreferences`.

## 🚀 How to Run

1.  **Clone & Install**

    ```bash
    git clone https://github.com/jarzeckil/mobile_email_client.git
    cd mobile_email_client
    flutter pub get
    ```

2.  **Run**
    ```bash
    flutter run
    ```
