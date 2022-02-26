# Tutorial for social login with Symfony

*Inspired from **Grafikart video**: [Tutoriel Symfony : Authentification social sur Symfony]](https://youtu.be/IobeCRI6NOw)

## Sources

- [OAuth / Social Integration for Symfony](https://github.com/knpuniversity/oauth2-client-bundle): `composer require knpuniversity/oauth2-client-bundle`

## Requirements

- Inscription on the App you want to connect with:
    - [Github.com > Settings > Developer settings > OAuth Apps](https://github.com/organizations/Mushu-Tutorials/settings/applications/new) > New OAuth App
        - Get the **Client ID** and add it to the env  the `.env.local` file

## Installation

```shell
# Libraries & PHP extensions
sudo apt install sqlite3
sudo apt install php-sqlite3

# Project
composer create-project symfony/website-skeleton tuto-symfony-oauth-github
cd tuto-symfony-oauth-github

cp .env.example .env.local
nano .env.local # GITHUB_ID= # GITHUB_SECRET=

# Symfony commands
sc m:user
sc m:auth
sc m:e User # add githubId to User to store the social login ID

# Composer
composer require knpuniversity/oauth2-client-bundle
composer require league/oauth2-github

nano config/packages/knpu_oauth2_client.yaml
```

## Run the server

```shell
php -S localhost:8000 -t public
```