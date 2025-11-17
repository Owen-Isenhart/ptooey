# TUI Deployment Platform — MVP & Stretch Goals

## MVP

### 1. Terminal-Only Frontend Client (Primary UI)
- Users interact with the platform through a native TUI client (`tui` command).
- Built with Rust (`ratatui` + `crossterm`).
- Features:
  - Login screen
  - Dashboard of deployments
  - Build logs viewer
  - Runtime logs viewer
  - Launcher for remote TUIs
  - File-tree project browser (optional)

### 2. Project Upload & Management
- Upload a TUI project via:
  - CLI (`tui deploy .`)
  - ZIP/TAR upload through the TUI client
  - GitHub repo link
- Users can view their deployed TUIs inside the TUI dashboard.

### 3. Build & Packaging Pipeline
- Backend build service compiles or prepares uploaded projects.
- Supported runtime stacks (initial):
  - Python (Textual, Rich)
  - Node.js (ink, blessed)
  - Go (Bubbletea)
- Automatic dependency installation.
- Build output stored & queryable.

### 4. Remote Execution Environment
- Each deployment runs in a secure sandbox (container / isolated namespace).
- Per-user resource quotas (CPU, RAM, timeout).
- PTY allocation per process for true TUI behavior.

### 5. Remote TUI Streaming Protocol
- Native PTY multiplexed protocol over:
  - WebSockets **or**
  - QUIC (preferred for performance)
- Handles:
  - byte-level input
  - ANSI output
  - resize events
  - session lifecycle

### 6. Remote Terminal Rendering in Local TUI
- The user’s local TUI client connects to remote TUIs and renders them *directly*.
- No web browser required.
- Behaves exactly like SSH, but application-specific.

### 7. Basic Deployment URLs
- Every TUI gets a unique deployment ID shown in the client.
- Public or private deploys.

### 8. Persistent Logs
- Build logs recorded and viewable.
- Runtime logs stored for each launch.

### 9. Authentication
- Email/password login.
- API token stored locally for CLI.
- Token refresh + session caching.

### 10. Basic Analytics
- Launch count per deployment.
- Last launched timestamp.
- Basic resource usage summary.

---

## Stretch Goals

### 1. Additional Runtime Profiles
- Rust apps (crossterm, ratatui)
- C / C++ ncurses apps
- Java / Kotlin TUIs
- WASM TUIs via WASI runtime
- Custom user-provided build scripts

### 2. Persistent Storage for TUIs
- Key-value store (Redis or SQLite-like)
- Per-deployment file storage
- “Stateful TUIs” for databases, config storage, small persistent data

### 3. Team Collaboration
- Project sharing with roles:
  - Viewer
  - Editor
  - Admin
- Team activity logs

### 4. Custom Domains
- Map a domain to a TUI:
  - `yourapp.tui.run`
  - `customdomain.com`

### 5. Scaling & Load Balancing
- Auto-scaling execution nodes
- Hot standby instances
- Parallel launches of the same TUI

### 6. WebAssembly Support
- Run TUIs in WASI for instant startup.
- WebAssembly “light containers.”

### 7. Payments / Pro Plans
- Usage-based billing:
  - CPU seconds
  - RAM hours
  - Persistent storage usage
- Multiple pricing tiers:
  - Free
  - Pro
  - Enterprise

### 8. Advanced CLI Tool Enhancements
- `tui deploy .`
- `tui logs <id>`
- `tui run <id>`
- `tui build`
- `tui ps` for active processes
- `tui kill <session>`

### 9. Optional: Web Dashboard (Later)
- For non-terminal users.
- Minimal UI for browsing deployments.
- Still secondary to the TUI-first design.

