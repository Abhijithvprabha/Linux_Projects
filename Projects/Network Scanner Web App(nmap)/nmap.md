# Simple Network Scanner Web App

This project allows you to create a simple network scanner that is accessible from a web browser on your network. The project uses `nmap` to scan the network at regular intervals and presents the results via a web interface.

## Project Overview

Every 10 minutes, a **Cron Job** triggers the `nmap` command to scan the network and outputs the results into a text file. A **PHP** script is then used to format and present the contents of the text file in a web browser for easy viewing.

## Prerequisites

To get started, make sure you have the following tools installed:

- **Linux** (Ubuntu or similar)
- **Cron Jobs** for scheduled tasks (`crontab`)
- **Apache2** for the web server
- **PHP** for handling the web interface
- **nmap** for network scanning

### Install Dependencies

1. **Install Apache2**:
   ```bash
   sudo apt-get install apache2
