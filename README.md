
# Support-Control-Panel (SCP)

Welcome to the SCP repository! This is a support control panel for managing support requests. Here, we provide instructions on how to set up and run the SCP on Linux, MacOS, and Windows.

## :gear: Requirements

Before you can set up and run the SCP, you will need to ensure that the following software is installed on your machine:

:desktop_computer: **Node.js**: This is required to build the Vue.js client. You can download it from the [official Node.js website](https://nodejs.org/en/).
    
:whale: **Docker**: This is required to run the necessary services for the SCP, such as MySQL and phpMyAdmin. You can download it from the [official Docker website](https://www.docker.com/).
    
:whale: **Docker Compose**: This is required to manage the Docker containers used by the SCP. You can install it by following the instructions in the [official Docker Compose documentation](https://docs.docker.com/compose/install/).
    

Once you have all of these requirements installed, you can follow the instructions in the previous section to set up and run the SCP.

## :computer: Installation

To get started, clone this repository onto your local machine:

`git clone https://github.com/cweyy/scp.git`

Then navigate into the `client` directory:

```bash
cd  client
```

Install all the dependencies using npm:

```bash
npm i
```

Finally, build the project using Vue:

```bash
vue build
```

After the build is complete, an automatically generated `dist` folder will be created at `/client/dist`.

## :wrench: Configuration

:information_source: To properly configure the SCP, you will need to create an `.htaccess` file in the `dist` folder with the following content:

```xml
<IfModule mod_negotiation.c>
	Options -MultiViews
</IfModule>
<IfModule mod_rewrite.c>
	RewriteEngine On
	RewriteBase /
	RewriteRule ^index\.html$ - [L]
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule . /index.html [L]
</IfModule>
```

## :rocket: Running the SCP

To run the SCP, you will need to use Docker Compose to start the necessary services:

```bash
docker-compose up --build
```

This will start MySQL, phpMyAdmin, and the Apache web server for the PHP backend. The configuration for these services can be found in the `docker-compose.yml` and `Dockerfile` files.

After everything is up and running, you can access the SCP at `http://127.0.0.1:3400`.

## :floppy_disk: Admin Configuration

After you have successfully set up and run the SCP, you can access the configuration panel as a high-level user (admin) at `http://127.0.0.1:3400/admin/config`.

From here, you can configure and customize various aspects of the SCP to suit your needs. This includes setting up email notifications, defining custom ticket categories, and managing user roles and permissions.

:check: That's it! With the SCP up and running, and fully configured to meet your needs, you can start managing support requests with ease.

## :warning:
> Please note that only high-level users (admins) have access to the configuration panel. If you need to grant or revoke admin privileges, you can do so by logging in as an existing admin and navigating to the "User Management" section.

## 📷 Images

Here are some demo images for the Support-Control-Panel:


> :closed_lock_with_key: Login Page
![Login](https://i.ibb.co/zRCqDqb/image.png)

> :bar_chart: Dashboard
![Dashboard](https://i.ibb.co/5vnMgXz/image.png)

> :link: Useful
![Useful](https://i.ibb.co/4V7r7q6/image.png)
