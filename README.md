# Roller Assignment - Smart B-Roll Video Editor

An OpenAI-powered video editing application that automatically inserts B-roll footage into talking-head videos using intelligent content analysis.

## Project Overview

This project consists of two main components:
- **Backend (roller_backend)**: Node.js/Express API server with AI integration for video processing
- **Frontend (roller_ui)**: React/Vite application with modern UI for video upload and management

## Features

- 🎬 **Smart B-Roll Insertion**: AI-powered analysis to determine optimal B-roll placement
- 📁 **Multi-file Upload**: Support for A-roll (main video) and multiple B-roll videos
- 🎯 **Real-time Processing**: Live upload progress and processing status
- 📊 **Timeline Generation**: JSON-based timeline plan for video editing
- 🎨 **Modern UI**: Clean, responsive interface built with React and Tailwind CSS
- 📝 **Comprehensive Logging**: Winston-based logging with daily rotation

## Tech Stack

### Backend
- Node.js with Express
- MongoDB with Mongoose
- OpenAI API integration
- Multer for file uploads
- Winston for logging
- CORS enabled for cross-origin requests

### Frontend
- React 19 with Vite
- Tailwind CSS for styling
- Axios for API communication
- Lucide React for icons
- Drag & drop file upload

## Prerequisites

- Node.js (v16 or higher)
- MongoDB (local or cloud instance)
- OpenAI API key

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd roller_assignment
```

### 2. Backend Setup

```bash
cd roller_backend

# Install dependencies
npm install

# Create environment file
cp env.example .env

# Edit .env file with your configuration (see Environment Variables section)
```

### 3. Frontend Setup

```bash
cd roller_ui

# Install dependencies
npm install
```

## Environment Variables

Create a `.env` file in the `roller_backend` directory with the following variables:

```env
# OpenAI API Configuration
OPENAI_API_KEY=your_openai_api_key_here

# Server Configuration
PORT=3000
NODE_ENV=development

# File Upload Configuration
MAX_FILE_SIZE=100000000
UPLOAD_DIR=./uploads

# MongoDB Configuration (add if using MongoDB)
MONGO_URL=mongodb://localhost:27017/roller_db
```

## Running the Application

### Start Backend Server

```bash
cd roller_backend

# Development mode with auto-reload
npm run dev

# Production mode
npm start
```

The backend server will start on `http://localhost:3000`

### Start Frontend Development Server

```bash
cd roller_ui

# Start development server
npm run dev
```

The frontend will be available at `http://localhost:5173`

## API Endpoints

### Health Check
- `GET /health` - Server health status

### B-Roll Processing
- `POST /api/broll/process` - Upload and process videos for B-roll insertion

## Project Structure

```
roller_assignment/
├── roller_backend/
│   ├── src/
│   │   ├── config/          # Configuration files
│   │   ├── constants/       # Application constants
│   │   ├── controller/      # Route controllers
│   │   ├── middlewares/     # Express middlewares
│   │   ├── routes/          # API routes
│   │   ├── services/        # Business logic
│   │   └── utils/           # Utility functions
│   ├── uploads/             # Uploaded video files
│   ├── logs/                # Application logs
│   └── index.js             # Server entry point
└── roller_ui/
    ├── src/
    │   ├── components/      # React components
    │   ├── constants/       # Frontend constants
    │   └── assets/          # Static assets
    └── public/              # Public files
```

## Output Artifacts

The application generates the following outputs:

1. **Timeline Plan JSON**: Detailed plan for B-roll insertion with timestamps and video segments
2. **Processing Logs**: Comprehensive logs of video analysis and processing
3. **Optional Rendered Video**: Final video output with B-roll insertions (future enhancement)

## Development

### Backend Development

```bash
cd roller_backend
npm run dev  # Starts with nodemon for auto-reload
```

### Frontend Development

```bash
cd roller_ui
npm run dev     # Start development server
npm run build   # Build for production
npm run preview # Preview production build
```

## File Upload Limits

- Maximum file size: 100MB per file
- Supported formats: MP4, MOV, AVI
- Multiple B-roll files supported

## Logging

The application uses Winston for comprehensive logging:
- Daily rotating log files in `roller_backend/logs/`
- Different log levels (info, error, debug)
- Request/response logging for API calls




<img width="916" height="459" alt="live image" src="https://github.com/user-attachments/assets/30158735-e82a-40e2-81cb-0deee0abeb58" />
