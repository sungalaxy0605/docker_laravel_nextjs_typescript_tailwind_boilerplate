# Project Name - Laravel, Next.js, TypeScript, Tailwind boilerplate

## Documentation
- [English](/README.md)
- [中文](/docs/ZH.md)
- [日本語](/docs/JA.md)

## Introduction
This project is a Dockerized template aimed at helping you quickly get started with building web applications using Laravel, Next.js, TypeScript, and Tailwind CSS.

## System Requirements
- Docker: Ensure that you have Docker installed. You can find installation instructions on the [Docker official website](https://www.docker.com/get-started).

## Quick Start
1. Clone this repository to your local environment:
   ```bash
   git clone https://github.com/cfwin/docker_laravel_nextjs_typescript_tailwind_template.git
   ```
2. Navigate to the project directory:
   ```bash
   cd docker_laravel_nextjs_typescript_tailwind_template
   ```
3. Edit your hosts file to map host.docker.internal to 127.0.0.1. You can open the C:\Windows\System32\drivers\etc\hosts file with a text editor and add the following line:
   ```plaintext
   127.0.0.1 host.docker.internal
   ```
4. Build and start the Docker containers:
   ```bash
   docker-compose up -d
   ```
5. Build and start the Docker containers:
   ```bash
   docker-compose exec app-api bash
   ```
6. Update Dependencies with Composer: Inside the container, use Composer to update the Laravel project's dependencies. Run the following command:
   ```bash
   cd /src/backend/api
   composer update
   cp .env.example .env
   php artisan key:generate
   ```
   Update the configuration of the .env file:
   ```plaintext
   # Update
   DB_CONNECTION=mysql
   DB_HOST=app-mysql
   DB_PORT=3306
   DB_DATABASE=app
   DB_USERNAME=app
   DB_PASSWORD=password
   
   REDIS_HOST=app-redis
   REDIS_PASSWORD=null
   REDIS_PORT=6379
   
   # Add
   FRONTEND_URL=http://host.docker.internal:8080
   SANCTUM_STATEFUL_DOMAINS=host.docker.internal
   ```
   This will set these environment variables to the specified values.
7. Install and Run Next.js:

	Now, let's set up and run the Next.js application.
	
	```bash
	docker-compose exec app-front bash
	```
	- Navigate to the Next.js project directory:
	```bash
	cd /usr/src/app
	```
	- Install the required dependencies:
	
	```bash
	npm install
	```
	
	- Start the Next.js development server:
	```bash
	npm run dev
	```

8. Enter the Laravel Project Directory: First, access the container for the app-api service. You can do this by running the following command:
   - Laravel Application: Visit [http://localhost:8080/](http://localhost:8080/) in your browser.
   - Next.js Application: Visit [http://localhost:8300/](http://localhost:8300/) in your browser.
   - Hello Page: Visit [http://localhost:8300/hello](http://localhost:8300/hello) in your browser.
   - Mailpit Application: Visit [http://localhost:8025/](http://localhost:8025/) in your browser.
   - phpMyAdmin Application: Visit [http://localhost:8081/](http://localhost:8081/) in your browser.

## Development

You can now start development within the project. Relevant code files for Laravel, Next.js, TypeScript, and Tailwind CSS are located in their respective directories.

## Stopping and Cleanup

To stop the Docker containers and clean up resources, run the following command:
   ```bash
   docker-compose down
   ```
## Contributing

Contributions to the project are welcome. Please check the contribution guidelines and submit a pull request.

## Issues and Feedback

If you encounter any issues or have feedback, please create an issue on GitHub.

