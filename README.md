# RECOOO

A web application security testing tool that allows you to scan web applications for common vulnerabilities like SQL Injection, XSS, and CSRF.

## Features

- SQL Injection scanning
- Cross-Site Scripting (XSS) detection
- Cross-Site Request Forgery (CSRF) scanning
- Real-time logging via WebSockets
- Modern dark-themed UI

## Running with Docker

The easiest way to run the application is with Docker and Docker Compose.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Starting the application

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/pentest-tool.git
   cd pentest-tool
   ```

2. Start the application using Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Access the application:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000

### Testing the Connection

We've provided a special test page to verify the connection between the frontend and backend:

1. Make sure Docker is running and both services are started
2. Access the test page at: http://localhost:3000/test-connection
3. The page will show connection status, API URLs, and test the health endpoint
4. You can also use the batch script (Windows) or shell script (Linux/macOS):

   **Windows:**
   ```
   .\test-connection.bat
   ```

   **Linux/macOS:**
   ```
   ./test-connection.sh
   ```

### Stopping the application

To stop all services:

**Using Docker Compose directly:**
```bash
docker-compose down
```

**Using the helper script:**

Windows:
```
.\run.bat stop
```

Linux/macOS:
```
./run.sh stop
```

## Development Setup

### Backend (Python/FastAPI)

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the development server:
   ```bash
   uvicorn main:app --reload
   ```

### Frontend (Next.js)

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

## API Endpoints

- `GET /` - Welcome message
- `GET /health` - Health check
- `POST /scan/sql` - Run SQL injection scan
- `POST /scan/xss` - Run XSS scan
- `POST /scan/csrf` - Run CSRF scan
- `WebSocket /ws/logs` - Real-time log stream

## License

MIT 