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

1. **Install Apache2, namp, php**:
   ```bash
   sudo apt-get install apache2
   sudo apt-get install php
   sudo apt-get install nmap
   
 Ensure Apache2 is running: After installing Apache, make sure it's running:

``` bash
    sudo systemctl start apache2
    sudo systemctl enable apache2

# Network Scan Directory Setup

## Setup Directory and Permissions

###  Create the Directory for Storing Network Scan Results

Run the following command to create the directory where `nmap` will save its output:


sudo mkdir -p /var/www/html/network_scan
2. Set the Appropriate Permissions
Change the ownership of the directory to the web server's user (e.g., www-data), so the web server can access the directory:


sudo chown www-data:www-data /var/www/html/network_scan
Set the permissions so that the web server has read and execute access to the directory:


sudo chmod 755 /var/www/html/network_scan

Ensure the Web Server User Can Write to the Directory
If you're using a non-default web server user or need the directory to be writable by the script, set the appropriate permissions as needed. For example, if you want to allow the web server user to write to the directory, you can adjust the permissions like this:


sudo chmod 775 /var/www/html/network_scan

This will grant write access to the web server's user and group.

Notes

Ensure that your web server is running as the user you set in the permissions (e.g., www-data).

If using a script that runs nmap, make sure it has the appropriate permissions to write to the directory.

Adjust directory permissions based on your security requirements.
Troubleshooting
If you encounter permission issues, verify the ownership and permissions of the directory using the following commands:

ls -ld /var/www/html/network_scan
This will show the current permissions and owner of the directory, allowing you to diagnose and fix any issues.
