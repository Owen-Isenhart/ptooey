# TUI Deployment Platform — MVP & Stretch Goals

## MVP

### 1. Project Upload & Management
- Users can upload a TUI project (zip, tar, or GitHub link).
- Users can view a dashboard of their deployed TUIs.

### 2. Build & Packaging Pipeline
- Basic build runner supporting:
  - Python (textual, rich)
  - Node.js (blessed, ink)
  - Go (bubbletea)
- Automatic dependency installation and build output capture.

### 3. Remote Execution Environment
- Sandbox container for each deployment.
- Process isolation per user.
- Limited runtime resource quotas.

### 4. Web Terminal Interface
- In-browser terminal connected to the remote TUI.
- Keyboard input + ANSI output streaming over WebSockets.

### 5. Basic Deployment URLs
- Each TUI gets a unique, shareable URL.
- Public or private visibility toggle.

### 6. Persistent Logs
- Runtime logs viewable from the dashboard.
- Build logs viewable post-deployment.

### 7. Authentication
- Email/password signup or login.
- Basic session management.

### 8. Basic Analytics
- Simple deployment usage count (launches, runtime hours).

---

## Stretch Goals

### 1. Multiple Runtime Profiles
- Support for:
  - Rust (crossterm, ratatui)
  - C/C++ ncurses apps
  - Java/Kotlin TUIs
- Custom build scripts per project.

### 2. Persistent Storage for Deployments
- Key-value store integration.
- File-based persistence for TUI apps.

### 3. Team Collaboration
- Project sharing with team members.
- Roles: Viewer, Editor, Admin.

### 4. Custom Domains
- Map a custom domain to a TUI deployment.

### 5. Scaling & Load Balancing
- Auto-scaling execution pools.
- Multiple instances per deployment.

### 6. WebAssembly Support
- Run lightweight TUIs in WASI environments.

### 7. Payments / Pro Plans
- Usage-based billing.
- Additional compute time or storage for paid plans.

### 8. CLI Tool
- Deploy directly from terminal via:
  ```bash
  tui-deploy deploy .
