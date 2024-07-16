# SMTP Server Setup with Postfix in Docker

This repository provides a Dockerized SMTP server setup using Postfix, configured to send emails via Gmail. This setup is ideal for local development environments where you need to test email functionality without relying on external SMTP servers.

## Table of Contents

- [What is SMTP and SMTP Server?](#what-is-smtp-and-smtp-server)
- [What is Postfix?](#what-is-postfix)
- [What is a Gmail Application Password and How to Obtain It?](#what-is-a-gmail-application-password-and-how-to-obtain-it)
- [Setup Instructions](#setup-instructions)
  - [Prerequisites](#prerequisites)
  - [Configuration](#configuration)
  - [Building and Running the Docker Container](#building-and-running-the-docker-container)
- [Usage](#usage)
- [Example](#example)
- [Contributing](#contributing)
- [License](#license)

## What is SMTP and SMTP Server?

SMTP (Simple Mail Transfer Protocol) is a communication protocol used for sending emails. An SMTP server is responsible for receiving and forwarding emails using this protocol.

## What is Postfix?

Postfix is a popular open-source Mail Transfer Agent (MTA) used on Unix-based systems. It handles sending, receiving, and forwarding emails efficiently.

## What is a Gmail Application Password and How to Obtain It?

A Gmail Application Password is a secure way to access Gmail when using third-party applications or devices. It allows you to authenticate without using your regular Gmail password, ideal for SMTP configurations.

## Setup Instructions

### Prerequisites

Before starting, ensure you have the following:
- Docker installed on your system.

### Configuration

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/smtp-server.git
   cd smtp-server
   ```

2. **Create a `.env` File:**
   Create a `.env` file in the root directory with your Gmail credentials and SMTP settings:
   ```dotenv
   EMAIL=your-gmail-address
   EMAIL_PASSWORD=your-gmail-application-password
   PORT=25
   MAIL_NAME=your-mailname
   SMTP_DOMAIN=smtp.gmail.com
   SMTP_PORT=587
   ```

3. **Update `main.cf`:**
   Modify the `main.cf` file located in the root directory if necessary. This file contains Postfix configuration settings.

### Building and Running the Docker Container

Build and run the Docker container using Docker Compose:
```bash
docker-compose up -d --build
```

## Usage

Once the Docker container is running, you can send test emails from your local environment using the configured SMTP server.

## Example

Send a test email from the Docker container shell:
```bash
docker exec -it smtp-server sh
echo "This is a test email." | mail -s "Test Subject" recipient@example.com
```

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

