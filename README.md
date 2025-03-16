# Project Setup and Deployment Guide

## Setting up VSCode Devcontainer

1. Open your project in VSCode.
2. Make sure you have the `Dev Containers` extension installed.
3. Open the command palette (Ctrl+Shift+P) and select `Dev Containers: Reopen in Container...`.
4. VSCode will now build and start the devcontainer.

## Running the Project

Once the devcontainer is up and running, you can run the project using Cargo:

1. Open a terminal in VSCode.
2. Run the following command:
   ```sh
   cargo run
   ```
3. You should see the output:
   ```
   Hello, World!
   ```

## Deploying with Docker Compose (example)

To deploy the project using Docker Compose, follow these steps:

1. Make sure you have Docker and Docker Compose installed.
2. Open a terminal and navigate to your project directory.
3. Run the following command:
   ```sh
   docker-compose up
   ```
4. Docker Compose will build and start the services defined in your `docker-compose.yml` file.
5. You should see the output:
   ```sh
   api-1  | Hello, World!
   api-1 exited with code 0
   ```

That's it! Your project should now be up and running.
