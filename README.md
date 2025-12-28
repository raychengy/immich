# Immich - Self-hosted photo and video backup solution directly from your mobile phone.

![Immich](https://immich.app/img/immich-logo-stacked-dark.svg)

Immich is a self-hosted photo and video backup solution. It's a great alternative to Google Photos or iCloud Photos.

## Features

*   **Automatic Backup:** Backs up photos and videos from your mobile phone (iOS and Android).
*   **Web Interface:** A full-featured web interface to view your photos and videos.
*   **Multi-user support:** Share your instance with your family and friends.
*   **Albums:** Create albums to organize your photos.
*   **Sharing:** Share your photos and albums with others.
*   **Machine Learning:** Immich uses machine learning to automatically tag your photos and recognize faces.

## Getting Started

This repository contains the `docker-compose.yml` file to run Immich.

### Prerequisites

*   [Docker](https://docs.docker.com/get-docker/)
*   [Docker Compose](https://docs.docker.com/compose/install/)

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

4.  Start the services:
    ```sh
    docker-compose up -d
    ```

5.  Open your browser and go to `http://localhost:2283`.

## Contributing

This is a mirror of the official Immich repository. If you want to contribute, please go to the [official repository](https://github.com/immich-app/immich).

## License

Immich is licensed under the MIT License. See the [LICENSE](https://github.com/immich-app/immich/blob/main/LICENSE) file for details.
