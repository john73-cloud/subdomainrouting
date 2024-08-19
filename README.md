# Simple Proof of Concept Application for Subdomains

This is a basic Express.js application designed as a proof of concept for handling subdomains. The application listens on port 3000 and responds to requests with a JSON object containing the host information and a test message.

## How It Works

The application is built using the Express.js framework. When a GET request is made to the root route (`/`), the server responds with a JSON object that includes the `host` header from the request and a message.

### Example Response

When you access the root route (e.g., `http://localhost:3000/`), the server will respond with:

```json
{
    "host": "localhost:3000",
    "message": "testing api"
}
```

### Subdomain Handling

This application can be extended to handle different subdomains. When a request is made to a specific subdomain, the `host` value in the JSON response will reflect the subdomain.

For example, if the application is hosted on a domain with a subdomain (e.g., `api.example.com`), the response would look like:

```json
{
    "host": "api.example.com",
    "message": "testing api"
}
```

## Getting Started

### Prerequisites

- Node.js installed on your machine.

### Installation

1. Clone this repository or copy the code provided.
2. Navigate to the project directory.
3. Install the necessary dependencies by running:

    ```bash
    npm install express
    ```

4. Start the server by running:

    ```bash
    node index.js
    ```

5. The server will be running on `http://localhost:3000/`.

### Testing Subdomains

To test subdomains locally, you can modify your `/etc/hosts` file (on Linux/Mac) or `C:\Windows\System32\drivers\etc\hosts` file (on Windows) to map subdomains to `localhost`. For example, you can add the following line:

```
127.0.0.1   api.localhost
```

Now, you can access the application via `http://api.localhost:3000/`, and the response will show `"host": "api.localhost:3000"`.

