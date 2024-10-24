[![tests](https://github.com/MelaineGerard/ddev-directus/actions/workflows/tests.yml/badge.svg)](https://github.com/ddev/ddev-memcached/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2024.svg)

## What is this?

This repository allows you to quickly install Directus into a [DDEV](https://ddev.readthedocs.io) project using `ddev get MelaineGerard/ddev-directus`.

## What is Directus

[Directus](https://directus.io/) is an Open Source Headless CMS for managing SQL database content. It's a nice tool to use as a backend for all your frontend applications.

## Installation

For DDEV v1.23.5 or above run

```sh
ddev add-on get MelaineGerard/ddev-directus && ddev restart
```

For earlier versions of DDEV run

```sh
ddev get MelaineGerard/ddev-directus && ddev restart
```

## Explanation

This Directus recipe for [DDEV](https://ddev.readthedocs.io) installs a [`.ddev/docker-compose.directus.yaml`](docker-compose.directus.yaml) using the `directus` Docker image.

## Interacting with Directus

* The Directus instance will listen on HTTP port 8055 (the Directus default).
* Configure your application to connect to Directus on the host:port `directus:8055`.
* To reach the Directus admin interface, open [https://your-project.ddev.site:8055/admin](https://your-project.ddev.site:8055/admin) in your browser. (You need to replace `your-project` with your actual project name.)
* Credentials are `admin@ddev.site` and `localadmin`.

  Your can customize the default credentials in the [docker-compose.directus.yaml](docker-compose.directus.yaml) by editing the `ADMIN_EMAIL` and `ADMIN_PASSWORD` variables.

## How to use this project in a fresh project

```bash
# 1. Create an empty project
mkdir simple-php-project
cd simple-php-project
# 2. Create a simple Hello, World in this folder
echo "<?php echo 'Hello, World!'; ?>" > index.php
# 3. Init ddev in the project
ddev config
# 4. Add Directus in the project
ddev add-on get MelaineGerard/ddev-directus #or ddev get MelaineGerard/ddev-directus for older versions of DDEV
# 5. Start the project
ddev start
# Directus should now be started on port 8055 of your project
```

Example url : [https://simple-php-project.ddev.site:8055](https://simple-php-project.ddev.site:8055)


## Maintained By

- [Melaine gérard](https://github.com/MelaineGerard)
