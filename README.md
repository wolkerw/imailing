## Running This Project with Docker

This project is set up to run as a Node.js application inside Docker, using Node.js version **22.13.1-slim**. All dependencies are installed via `npm ci --production` for deterministic builds. The application exposes port **5000**.

### Requirements
- Docker and Docker Compose installed on your system.
- No external services or persistent volumes are required.
- No required environment variables by default, but you may uncomment the `env_file` line in `docker-compose.yml` if you add a `.env` file.

### Build and Run Instructions
1. **Build and start the service:**
   ```sh
   docker compose up --build
   ```
   This will build the image using the specified Node.js version and start the app in a container named `javascript-app`.

2. **Access the application:**
   - The app will be available on [http://localhost:5000](http://localhost:5000)

### Configuration Notes
- The container runs as a non-root user for security.
- The `NODE_ENV` is set to `production` and `NODE_OPTIONS` is set to `--max-old-space-size=4096` by default.
- If you need to add environment variables, create a `.env` file and uncomment the `env_file` line in `docker-compose.yml`.

### Ports
- **5000**: Exposed by the application and mapped to the host.

_No additional configuration or external services are required for this project._
