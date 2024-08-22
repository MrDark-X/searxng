# Searx Meta Search Engine with Docker Compose

This repository contains the configuration files needed to deploy the Searx meta-search engine using Docker Compose. Searx is a privacy-respecting, customizable metasearch engine that aggregates results from various search engines without tracking users.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/searx-docker.git
cd searx-docker
```

### 2. Customize Configuration (Optional)

The docker-compose.yaml file is pre-configured to run Searx with sensible defaults. However, you can customize the settings according to your needs. For example, you can modify the SEARXNG_BASE_URL environment variable to reflect your domain.

### 3. Start the Searx Service
Run the following command to start the Searx service:
```
docker-compose up -d
```

### 4. Access Searx

Once the service is running, you can access Searx in your web browser at:
```
http://localhost:8080
```

If you've configured a custom domain, replace localhost with your domain name.

### 5. Stop the Searx Service

To stop the Searx service, use the following command:

```
docker-compose down
```

This will stop and remove the containers, but the data will persist.

### Directory Structure

   . docker-compose.yaml: The Docker Compose configuration file.
   . searxng/: A directory where SearxNG configuration files are stored.

### Logging

The service is configured to use the json-file logging driver with a maximum log file size of 1MB and a maximum of 1 log file. You can adjust these settings in the docker-compose.yaml file under the logging section.

### Security Considerations

The Docker container is configured with minimal capabilities (cap_drop: ALL) and only adds the necessary ones (CHOWN, SETGID, SETUID). This is done to enhance security by reducing the container's potential attack surface.

### Troubleshooting

Ensure Docker and Docker Compose are properly installed and running.

Check the logs for any errors:

```
docker-compose logs searxng
```

Make sure the port 8080 is not being used by another service on your machine.

### License

This project is licensed under the MIT License. See the LICENSE file for details.

## SearxNG for the amazing project.
