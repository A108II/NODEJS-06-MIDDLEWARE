# README

## Overview
This README provides an overview of a Node.js application that serves static files, handles different file types, and implements route handling and redirection. The application uses the Express framework to create a server and manage routes.

## Dependencies
The application requires the following npm packages:
- `express`: For creating and managing the HTTP server and routes.
- `path`: For handling and transforming file paths.
- `cors`: For enabling Cross-Origin Resource Sharing.

## Installation
Install the necessary npm packages using the following command:
```bash
npm install express path cors
```

## Usage

### Running the Application
1. Navigate to the project directory in your terminal.
2. Run the following command to start the server:
   ```bash
   npm run dev
   ```
   The server will start listening on the specified port (default is 3500).

### Serving Static Files
The application serves static files from the `public` directory, allowing CSS, images, and other assets to be properly rendered when requested.

### Route Handling

#### Home and Index Page
- **Path**: `/`, `/index`, or `/index.html`
- **Description**: Matches the root URL and serves the `index.html` file from the `html_files` directory.

#### New Page
- **Path**: `/new` or `/new.html`
- **Description**: Serves the `new.html` file from the `html_files` directory.

#### Old Page Redirect
- **Path**: `/old` or `/old.html`
- **Description**: Redirects to `/new.html` with a 301 status code.

### Middleware

#### Hello Route
- **Path**: `/hello` or `/hello.html`
- **Description**: Logs a message and serves "Hi there!".

#### Chain Route
- **Path**: `/chain` or `/chain.html`
- **Description**: Logs messages in sequence and serves "Done!" using chained middleware functions.

### Error Handling
The application serves a custom 404 page for any unmatched routes.

#### 404 Page
- **Path**: Any unmatched path
- **Description**: Serves the `404.html` file from the `html_files` directory or returns a JSON/plain text error message based on the client's `Accept` header.

### Logging
Custom middleware is used for logging events and errors.

#### Logger
Logs requests to `reqLog.txt`.

#### Error Handler
Logs errors to `errLog.txt` and sends a 500 status with the error message.

## Conclusion
This README provides an overview of a Node.js application using Express to serve static files, handle different file types, implement routing and redirections, and manage custom route handlers. It covers the dependencies, installation, usage instructions, and the core functionality of the application.