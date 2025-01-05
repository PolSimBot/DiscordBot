# Political Simulation Discord Bot Design Document

## Introduction

Project Name: Political Simulation Discord Bot
Project Description: A Discord bot that simulates the political process of a government.
Target Audience: PolSim Servers on Discord

## Features

Core Features:

- Voting
- Modification of Server
- Modification of Bot

## Technical Details

### Architecture

Language(s): Python (3.10.15)
Database: SQLite3

### Libraries

Libraries Used:

- discord.py
- sqlite3

## Development

### Testing

Testing Strategy:

- Unit Testing
Non-Discord API testing (internal functions, database wrappers, etc.)
- Integration Testing
Discord API testing (bot commands, bot responses, etc.)

Testing Tools:

- pytest
- pytest-cov
- pytest-mock

### Deployment

Deployment Strategy:

1. Create a PR to the main branch
2. Log into VPS/Server
3. Pull the latest code from the main branch on the server
4. Restart the bot
