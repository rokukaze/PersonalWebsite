# Personal Website

A full-stack personal website project with a Rails backend and React frontend, featuring Docker containerization and PostgreSQL database.

## Project Structure

- `backend/` - Rails 8.1 API backend with PostgreSQL
- `frontend/` - React + TypeScript + Vite frontend
- `compose.yml` - Docker Compose configuration for full-stack deployment
- `Taskfile.yml` - Task automation configuration

## Prerequisites

### Docker Setup (Recommended)
- Docker
- Docker Compose

### Manual Setup
- Ruby 3.2.6 (managed via [mise](https://mise.jdx.dev/))
- Node.js and npm
- PostgreSQL 18

## Getting Started

### Quick Start with Docker (Recommended)

1. Clone the repository and navigate to the project directory

2. Start all services with Docker Compose:
   ```bash
   docker compose up
   ```

This will start:
- **Frontend** at `http://localhost:5173`
- **Backend** at `http://localhost:5174`
- **PostgreSQL database** on port 5432 (internal)

The services are configured with:
- Automatic health checks for the database
- Volume persistence for PostgreSQL data
- Proper service dependencies and networking
- Hot reload for development

### Manual Setup

#### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Copy the environment example file:
   ```bash
   cp .env.example .env
   ```

3. Install dependencies:
   ```bash
   bundle install
   ```

4. Set up the database:
   ```bash
   rails db:create
   rails db:migrate
   rails db:seed
   ```

5. Start the Rails server:
   ```bash
   bin/dev
   ```

The backend will be available at `http://localhost:5174`

#### Frontend Setup

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

The frontend will be available at `http://localhost:5173`

## Development

### Backend

- **Ruby version**: 3.2.6 (specified in `.mise.toml`)
- **Framework**: Rails 8.1.1
- **Database**: PostgreSQL 18
- **Server**: Puma
- **Port**: 5174 (configured to prevent port collisions)

#### Running Tests

```bash
cd backend
rails test
```

#### Code Quality

```bash
cd backend
bin/rubocop
bin/brakeman
bin/bundler-audit
```

#### Database Configuration

The project is configured with PostgreSQL for all environments:
- Development: PostgreSQL 18 (via Docker or local installation)
- Database configuration available in `backend/config/database.yml`
- Environment variables can be set in `.env` (see `.env.example`)

### Frontend

- **Framework**: React 19.2.0
- **Language**: TypeScript
- **Build Tool**: Vite (standard build, non-experimental)
- **Linting**: ESLint
- **Port**: 5173
- **Docker**: Dockerized with hot reload support

#### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

### Docker Services

The `compose.yml` configuration includes:

- **frontend**: React app with Vite, exposed on port 5173
- **backend**: Rails API server, exposed on port 5174
- **db**: PostgreSQL 18 Alpine with health checks and data persistence

All services are connected via a dedicated `app-network` bridge network.

## Deployment

The backend includes:
- Kamal configuration for Docker-based deployment
- Complete Dockerfile for production builds
- Environment variable management via `.env` files

See `backend/config/deploy.yml` for deployment settings.

## Technology Stack

### Backend
- Rails 8.1.1
- PostgreSQL 18 (Alpine)
- Puma web server
- Solid Cache, Solid Queue, Solid Cable
- Kamal for deployment
- Turbo Rails & Stimulus
- Docker containerization

### Frontend
- React 19.2.0
- TypeScript
- Vite (standard build)
- ESLint
- Docker containerization

### Infrastructure
- Docker & Docker Compose
- PostgreSQL 18
- Task automation with Taskfile

## License

[Add your license here]

