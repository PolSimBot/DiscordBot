# Political Simulation Discord Bot Design Document

## 1. Introduction

**Project Name:** Political Simulation Discord Bot  
**Project Description:** A Discord bot that simulates the political process of a government.  
**Target Audience:** PolSim Servers on Discord

## 2. Features

- **Voting**
- **Modification of Server**
- **Modification of Bot**
- **Google OAuth 2.0 Integration**: Required for voting authentication.

## 3. Technical Details

### 3.1. Architecture

- **Language(s):** Python (3.10.15)
- **Database:** SQLite3

### 3.2. Authentication

- **Google OAuth 2.0:** Used to authenticate users for voting, ensuring votes are from verified users.

### 3.3. Libraries

- **Core Libraries:**
  - discord.py
  - sqlite3
- **Authentication Libraries:**
  - oauthlib
  - requests_oauthlib

## 4. Development Strategy

### 4.1. Command Structure

- **Tree Commands with Interactions:** Utilizing `discord.ext.commands.app_commands` for hierarchical command handling.
- **Cogs and Extensions:** Modular structure to maintain and scale bot functionality.

### 4.2. Testing

- **Testing Strategy:**
  - **Unit Testing:** Test internal functions, database wrappers, OAuth logic, etc.
  - **Integration Testing:** Validate Discord API interactions, bot commands, OAuth flow.

- **Testing Protocols:**
  - Command execution and error handling.
  - Functionality of individual cogs.
  - Validation of database operations.
  - User authentication flow.
  - Performance under load.

- **Testing Tools:**
  - pytest
  - pytest-cov
  - pytest-mock

### 4.3. Deployment

1. Create a PR to the main branch.
2. Log into VPS/Server.
3. Pull the latest code from the main branch on the server.
4. Add environment variables for Google OAuth credentials.
5. Restart the bot.

## 5. Logging and Monitoring

### 5.1. Logging Strategy

- **Tools Used:**
  - **Python's Logging Module**: The base logging framework to handle log message generation and formatting.
  - **Rich**: An extension on top of the logging module for more visually appealing logs with features like colored logs, progress bars, and tracebacks.

- **Logging Levels:**
  - Extensive use of detailed logging at the `INFO` level to track the operation of each subroutine and all critical steps within the application.
  - Additional logging at `WARNING`, `ERROR`, and `DEBUG` levels as needed for capturing potential issues and detailed debugging information.

### 5.2. Implementation

- **Every Subroutine and Module**: Ensure that each subroutine and module has at least one log message indicating its execution. This will help trace the entire flow of the bot's operation.
- **Logging Structure**:
  - Start and exit points of functions.
  - Key actions or decisions made by the bot.
  - Important API interactions and responses, such as OAuth authentication success or failures.
  - Database operations, including queries and transactions.

### 5.3. Monitoring

- **Objectives**: Monitor performance and usage, detect anomalies or errors, and troubleshoot issues quickly.
- **Considerations**:
  - Implement log rotation to manage log file sizes if written to disk.
  - Possible integration with logging aggregation tools for real-time monitoring and alerting.
