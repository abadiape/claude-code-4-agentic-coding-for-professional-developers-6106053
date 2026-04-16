# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a React application showcasing the "Stargazers" - an intergalactic alliance of alien characters. It's part of the LinkedIn Learning course "Claude Code 4: Agentic Coding for Professional Developers" by Ray Villalobos. The application displays character profiles in an interactive gallery with modal popups and theme switching capabilities.

## Architecture

### Core Structure
- **React 19** with Vite as the build tool and development server
- **PicoCSS** for styling with built-in theme support (light/dark/auto)
- **Component-based architecture** with clear separation of concerns
- **Static data** served from `public/cast.json` containing character information

### Key Components
- `App.jsx`: Main application container, manages cast data and modal state
- `Nav.jsx`: Navigation bar with logo, dropdown menu, and theme toggle
- `ListCast.jsx`: Grid layout displaying character thumbnails
- `Modals.jsx`: Character detail modal system
- `ToggleTheme.jsx`: Theme switcher with localStorage persistence
- `InterfaceStyles.jsx`: Additional styling components

### Data Flow
The app fetches character data from `cast.json` on component mount and passes it down through props. Modal state is managed at the App level and can be triggered from both the navigation dropdown and the character grid.

## Development Commands

```bash
# Install dependencies
npm install

# Start development server (runs on http://localhost:5173)
npm run dev

# Build for production (outputs to docs/ directory)
npm run build

# Preview production build
npm run preview

# Run ESLint
npm run lint
```

## Build Configuration

- Vite configuration includes React Compiler plugin for optimization
- Build output goes to `docs/` directory (configured for GitHub Pages deployment)
- Base path is set to `./` for relative asset loading
- Images and static assets are served from `public/` directory

## Key Features

### Theme System
The application supports three themes (light, dark, auto) with:
- localStorage persistence across sessions  
- System preference detection for auto mode
- Dynamic data-theme attribute updates on document root

### Character Data Structure
Each character in `cast.json` includes:
- Basic info (id, name, slug, bio, origin)
- Physical attributes (eyes, ambulation method)
- Professional details (job_title, dream_job_title)
- Personal preferences (favorites object with food, music, books, footwear)
- Additional traits (hobby, singing_voice)

## Asset Organization
- Character images follow naming convention: `images/{slug}_tn.svg` for thumbnails
- Full character images: `images/{slug}.svg`
- Background images and UI assets stored in `images/` directory
- Card-based character representations for detailed views

## Branch Structure
This repository uses a course-specific branching strategy:
- `main`: Final course state
- `CHAPTER#_MOVIE#`: Corresponds to specific course videos
- Some branches have `b` (beginning) and `e` (end) variants