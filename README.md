# Immich - Self-hosted photo and video backup solution directly from your mobile phone.

![Immich](https://immich.app/img/immich-logo-stacked-dark.svg)

Immich is a self-hosted photo and video backup solution. It's a great alternative to Google Photos or iCloud Photos.

## Features

- **Automatic Backup:** Automatically backs up photos and videos from your mobile phone (iOS and Android).
- **Self-Hosted:** Your photos and videos are stored on your own server, giving you full control over your data.
- **Multi-User Support:** Share your instance with your family and friends, with separate accounts.
- **Albums:** Create shared or private albums to organize your memories.
- **Advanced Search:** Search your library by tags, metadata, and even objects in the photos using machine learning.
- **Face Recognition:** Automatically detects and groups photos of the same people.
- **Geolocation:** View your photos on a world map.
- **Sharing:** Share your photos and albums with others via public links.
- **Cross-platform:** Access your photos from the web interface or the mobile apps (iOS and Android).
- **And much more!**

## Getting Started

This repository contains the `docker-compose.yml` file to run Immich.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Installation

1.  Clone this repository:

    ```sh
    git clone https://github.com/immich-app/immich.git
    cd immich
    ```

2.  Create a `.env` file by copying the example:

    ```sh
    cp .env.example .env
    ```

3.  Edit the `.env` file and change the default values. At a minimum, you should change `DB_PASSWORD`.

4.  Create the necessary directories for the database, library and backups.

    ```sh
    mkdir -p ./pgdata ./library ./backups
    ```

    Ensure these directories are writable by the user running the Docker command.

5.  Start the services:

    ```sh
    docker-compose up -d
    ```

6.  Open your browser and go to `http://localhost:2283`.

## Advanced Setup

### Reverse Proxy

It is recommended to run Immich behind a reverse proxy. This allows you to use a custom domain, SSL certificates, and adds a layer of security.

Here's an example of how to set it up with [Nginx Proxy Manager](https://nginxproxymanager.com/).

1.  **Add a new Proxy Host.**
2.  In the `Details` tab:
    - **Domain Names:** Enter your domain or subdomain (e.g., `immich.yourdomain.com`).
    - **Scheme:** `http`
    - **Forward Hostname / IP:** The hostname or IP of your Immich server (e.g., `immich-server` if on the same Docker network, or the server's IP address).
    - **Forward Port:** `2283`
    - Enable **Websockets Support**. This is crucial for real-time features.
3.  In the `SSL` tab:
    - Request a new SSL certificate and enable `Force SSL`.
4.  In the `Advanced` tab, add the following to support large video uploads:
    ```nginx
    client_max_body_size 0;
    ```

After saving, you should be able to access Immich at your specified domain.

## License

Immich is licensed under the MIT License. See the [LICENSE](https://github.com/immich-app/immich/blob/main/LICENSE) file for details.
