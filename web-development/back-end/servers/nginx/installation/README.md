# nginx Installation

## Step 1: Install Nginx

**sudo apt-get update**

**sudo apt-get install nginx**

## Step 2: Adjust the Firewall

**sudo ufw app list**

**sudo ufw allow 'Nginx HTTP'**

**sudo ufw status**

## Step 3: Check your Web Server

**systemctl status nginx**

## Step 4: Manage the Nginx Process

- To stop your web server, you can type:
    - **sudo systemctl stop nginx**
- To start the web server when it is stopped, type:
    - **sudo systemctl start nginx**
- To stop and then start the service again, type:
    - **sudo systemctl restart nginx**
- If you are simply making configuration changes, Nginx can often reload without dropping connections. To do this, this command can be used:
    - **sudo systemctl reload nginx**
- By default, Nginx is configured to start automatically when the server boots. If this is not what you want, you can disable this behavior by typing:
    - **sudo systemctl disable nginx**
- To re-enable the service to start up at boot, you can type:
    - **sudo systemctl enable nginx**

## Step 5: Get Familiar with Important Nginx Files and Directories

### Content

- `/var/www/html`: The actual web content, which by default only consists of the default Nginx page you saw earlier, is served out of the `/var/www/html` directory. This can be changed by altering Nginx configuration files.

### Server Configuration

- `/etc/nginx`: The Nginx configuration directory. All of the Nginx configuration files reside here.
- `/etc/nginx/nginx.conf`: The main Nginx configuration file. This can be modified to make changes to the Nginx global configuration.
- `/etc/nginx/sites-available/`: The directory where per-site "server blocks" can be stored. Nginx will not use the configuration files found in this directory unless they are linked to the `sites-enabled` directory (see below). Typically, all server block configuration is done in this directory, and then enabled by linking to the other directory.
- `/etc/nginx/sites-enabled/`: The directory where enabled per-site "server blocks" are stored. Typically, these are created by linking to configuration files found in the `sites-available` directory.
- `/etc/nginx/snippets`: This directory contains configuration fragments that can be included elsewhere in the Nginx configuration. Potentially repeatable configuration segments are good candidates for refactoring into snippets.

### Server Logs

- `/var/log/nginx/access.log`: Every request to your web server is recorded in this log file unless Nginx is configured to do otherwise.
- `/var/log/nginx/error.log`: Any Nginx errors will be recorded in this log.