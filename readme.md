# HAProxy Health Check with Docker Compose and Nginx 🚀💻

This project sets up a robust health check system for backend services using HAProxy, Docker Compose, and Nginx. It supports dynamic configuration through environment variables and integrates HTTPS support. 🚀🌟💻

## Features

- **HAProxy Health Checks**: Ensures backend services are functional and routes traffic only to healthy instances. ✅🛠️🔍
- **Dynamic Configuration**: Easily configure DNS and health endpoints using environment variables. 🔄⚙️🌐
- **Nginx Reverse Proxy**: Manages a subdomain and proxies requests to HAProxy. 🌐🔗📡
- **Docker Compose Setup**: Simplifies deployment and management. 📦🚀💼
- **HTTPS Support**: Secure communication with configurable SSL certificates. 🔒🌐🛡️

## Prerequisites

- Docker and Docker Compose installed. 🐋📂💾
- Valid domain name for the subdomain (e.g., `domain.subdomain.com.br`). 🌍🖥️📧
- SSL certificate and private key (or use Let's Encrypt for automatic certificates). 🔒📜🔑

## Setup Instructions

1. Clone the repository: 🖥️📂📥

   ```bash
   git clone https://github.com/your-username/haproxy-health-check.git
   cd haproxy-health-check
   ```

2. Set environment variables in your `.env` file: 📄⚙️🔑

   ```env
   DNS_SERVER1=192.168.1.10
   DNS_SERVER2=192.168.1.11
   HEALTH_ENDPOINT=/health
   ```

3. Update SSL configuration in `nginx.conf` if using custom certificates: 🔒🛠️📜

   ```nginx
   ssl_certificate /etc/nginx/ssl/certificate.crt;
   ssl_certificate_key /etc/nginx/ssl/private.key;
   ```

4. Start the services: 🚀📦🔄

   ```bash
   docker-compose up -d
   ```

5. Verify the setup: 🕵️‍♂️🔗✅
   - Access the health check via the subdomain, e.g., `https://dev-cooptracer.coopersystem.com/health-check`.
   - View HAProxy stats at `http://<your-ip>:8080/stats` (default login: `admin`, password: `password`).

## Project Structure

```
.
├── docker-compose.yml   # Docker Compose configuration
├── haproxy.cfg          # HAProxy configuration file
├── nginx.conf           # Nginx configuration file
└── .env.example         # Example environment variables
```

## Environment Variables

| Variable       | Description                            |
|----------------|----------------------------------------|
| `DNS_SERVER1`  | DNS or IP of the first backend service |
| `DNS_SERVER2`  | DNS or IP of the second backend service|
| `HEALTH_ENDPOINT` | Endpoint path for health checks      |

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request. 🙌🤝🌟

## License

This project is licensed under the MIT License. See the LICENSE file for details. 📜⚖️✅

