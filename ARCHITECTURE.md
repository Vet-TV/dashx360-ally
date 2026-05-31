# DashX360 Ally - Architecture Plan

## Project Overview

DashX360 Ally is an enhanced fork of DashX360 optimized for the ASUS ROG Ally Z1 Extreme handheld gaming device. It serves as a comprehensive Windows shell replacement providing unified access to local games, cloud gaming services, music, videos, and system management—all designed around controller-first interaction.

## Core Architecture

The application is structured with a unified shell integrating:
- **Games Hub:** Local + Cloud gaming (equal-priority sources)
- **Media Hub:** Music and Video playback
- **File Browser:** Windows Explorer replacement
- **Settings & Control:** System management
- **Controller Input:** Universal input handling
- **Device Optimization:** ROG Ally Z1 Extreme-specific features

## Key Components

### 1. Unified Game Library System
- **Local Sources:** Steam, Epic Games, GOG, Game Pass, Raw Executables
- **Cloud Sources:** Xbox Cloud Gaming, Boosteroid, NVIDIA GeForce NOW
- **Smart Deduplication:** Same game from multiple sources shown once with launch options
- **Metadata Enrichment:** Combined artwork and data from all sources

### 2. Cloud Gaming Integration

#### Xbox Cloud Gaming (XCloud)
- Microsoft Account OAuth 2.0
- Xbox Game Pass for Cloud catalog
- Play token generation
- Server selection via latency testing
- Session management and monitoring

#### Boosteroid
- Boosteroid OAuth login
- Subscription and rental game models
- Game library sync
- Save game management
- Achievement tracking

#### NVIDIA GeForce NOW
- NVIDIA Account OAuth 2.0
- Multi-platform library linking (Steam, Epic, Uplay, etc.)
- RTX ray tracing support
- DLSS Super Resolution
- Cloud save management
- Multiple quality tiers (1080p/1440p/4K)

### 3. Media Playback System

#### Music Player
- Codec support: MP3, FLAC, WAV, OPUS
- Streaming integration: Spotify, iTunes
- Audio visualizer with spectrum analyzer
- Gapless playback
- Queue and playlist management

#### Video Player
- Video format support: MP4, MKV, AVI, MOV
- Hardware-accelerated decoding (H.264, H.265, VP9)
- Subtitle support (embedded and external SRT)
- Resume playback from last position
- Adaptive bitrate streaming

### 4. Windows Explorer Replacement
- File navigation with breadcrumbs
- Quick access sidebar
- Multiple view modes (grid, list, compact)
- File operations (copy, move, delete, rename)
- Full-text search and filtering
- File previews
- Drag & drop support
- Application launcher
- System control panel
- Status bar with battery/network indicators

### 5. Controller-First Input System
- XInput native support
- DirectInput fallback
- Custom button mapping
- Analog stick sensitivity settings
- Vibration feedback
- Gesture recognition

### 6. ROG Ally Z1 Extreme Optimization
- Hardware detection and profiling
- Performance tier modes (Aggressive/Balanced/Eco)
- Thermal management
- Battery optimization
- Dynamic refresh rate (30/60/120 Hz)
- Power management integration

## Technology Stack

### Frontend
- React 18+
- TypeScript
- Redux Toolkit
- TailwindCSS
- Framer Motion

### Backend
- Electron 22+
- Node.js 18+
- SQLite with Drizzle ORM

### APIs
- Steam Web API
- Epic Games API
- GOG API
- Xbox Cloud Gaming API
- Boosteroid API
- NVIDIA GeForce NOW API

### Build & Development
- Vite
- Jest + React Testing Library
- ESLint + Prettier

## Performance Targets

| Metric | Target |
|--------|--------|
| App Launch | <2s |
| Library Load | <3s |
| Game Launch (local) | <5s |
| Game Launch (cloud) | <10s |
| Menu Frame Rate | 60 FPS |
| Memory Usage | <300MB |
| Input Latency | <50ms |
| Thermal (sustained) | <80°C |
| Battery (gaming) | 2+ hours |
| Battery (media) | 6+ hours |

## Security & Privacy

- API keys stored in system keyring
- Tokens encrypted in database
- OAuth with PKCE
- TLS 1.3 for all APIs
- Opt-in telemetry only
- Local library storage (no cloud sync)
- Minimal privilege escalation
