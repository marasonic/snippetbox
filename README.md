# Snippetbox

Snippetbox is a simple web application for managing code snippets. This project is built using Go and MySQL.

## Prerequisites

- Docker and Docker Compose installed
- Go installed (if running locally)

## Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd snippetbox
```

### 2. Start the MySQL Database

Use Docker Compose to start the MySQL server:

```bash
docker-compose up -d
```

### 3. Set Up the Database

#### Apply the Schema

Load the database schema:

```bash
docker exec -i snippetbox-mysql mysql -u root -p'rootpassword' snippetbox < db/schema.sql
```

#### Insert Dummy Data

Load the dummy data:

```bash
docker exec -i snippetbox-mysql mysql -u root -p'rootpassword' snippetbox < db/dummy_data.sql
```

### 4. Run the Application

Start the web server:

```bash
go run ./cmd/web
```

The application will be available at `http://localhost:4000`.

## Project Structure

- `cmd/web/`: Contains the main application code.
- `db/`: Contains the database schema and dummy data.
- `ui/`: Contains HTML templates, CSS, and JavaScript files.

## License

This project is licensed under the MIT License.
