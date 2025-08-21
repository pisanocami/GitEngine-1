# GitEngine-1

## Windows Setup Guide

### 1. Environment Variables
Use `cross-env` for npm scripts:
```json
"dev": "cross-env NODE_ENV=development tsx server/index.ts"
"start": "cross-env NODE_ENV=production node dist/index.js"
```

### 2. Port Configuration
Server uses port 5001 by default to avoid conflicts:
```typescript
const PORT = process.env.PORT || 5001;
```

### 3. Socket Reuse
Disable `reusePort` on Windows:
```typescript
reusePort: process.platform !== 'win32'
```

### 4. Running the App
```bash
npm install
npm run dev
```
Access at: http://localhost:5001
