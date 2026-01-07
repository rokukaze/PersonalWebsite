# Personal Website

A full-stack personal website project with a Rails backend and React frontend.

## Project Structure

- `backend/` - Rails 8.1 API backend
- `frontend/` - React + TypeScript + Vite frontend

## Prerequisites

- Ruby 3.2.6 (managed via [mise](https://mise.jdx.dev/))
- Node.js and npm
- SQLite3

## Getting Started

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Set up the database:
   ```bash
   rails db:create
   rails db:migrate
   rails db:seed
   ```

4. Start the Rails server:
   ```bash
   bin/dev
   ```

The backend will be available at `http://localhost:3000`

### Frontend Setup

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
- **Database**: SQLite3
- **Server**: Puma

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

### Frontend

- **Framework**: React 19.2.0
- **Language**: TypeScript
- **Build Tool**: Vite (rolldown-vite)
- **Linting**: ESLint

#### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

## Deployment

The backend includes Kamal configuration for Docker-based deployment. See `backend/config/deploy.yml` for deployment settings.

## Technology Stack

### Backend
- Rails 8.1.1
- SQLite3
- Puma web server
- Solid Cache, Solid Queue, Solid Cable
- Kamal for deployment
- Turbo Rails & Stimulus

### Frontend
- React 19.2.0
- TypeScript
- Vite (rolldown-vite)
- ESLint

## License

[Add your license here]

