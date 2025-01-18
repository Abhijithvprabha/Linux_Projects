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

1. **Install Apache2, nmap, php**:
    ```bash
    sudo apt-get install apache2
    sudo apt-get install php
    sudo apt-get install nmap
    ```

2. **Ensure Apache2 is running**:
    After installing Apache, make sure it's running:
    ```bash
    sudo systemctl start apache2
    sudo systemctl enable apache2
    ```

# Network Scan Directory Setup

## Setup Directory and Permissions

### Create the Directory for Storing Network Scan Results

# Configure Ownership and Permissions (This is a Bad Idea)

sudo chown ubuntu /var/www/html

sudo chmod 777 /var/www/html

# Cron Job Configuration

sudo crontab -e

*/10 * * * * nmap 192.168.1.0/24 -oN /var/www/html/nmap.html

# PHP Script: `network.php`

This PHP script displays the server's current timestamp and includes the content of the `nmap.html` file, preserving its formatting.

### PHP Code:

```php
<?php

echo "Server Timestamp: ";
echo date("h:i:sa");

echo "<pre>";
include("nmap.html");
echo "</pre>";

?>

```


