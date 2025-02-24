# ECSAgent

ECSAgent is an AI agent framework designed by ECS accompany with plugin Architecture.

Our origin idea comes from https://github.com/project-89/argOS/blob/main/designDocsBackup/bitECS-readme.md.

Our ECS implementation uses [bitECS](https://github.com/NateTheGreatt/bitECS).

## Features

- [ ] ECS Architecture
- [ ] Plugin Architecture
- [x] Event Manager
    - [x] Event Bus
- [ ] Module System 
    - [ ] System Drawer
- [ ] Swarm
- [ ] Action Manager
- [ ] Embeeding Manager
    - [ ] Dynamic Tool 
    - [ ] Dynamic Content 
- [ ] Chat Client 
    - [ ] Telegram
    - [ ] Discord
    - [ ] WeChat
    - [ ] Web
    - [ ] CLI 
    - [ ] Twitter
- [ ] Social Media 
    - [ ] Twitter
    - [ ] xiaohongshu 
    - [ ] TikTok
    - [ ] YouTube
- [ ] Market client
    - [ ] Bireye
    - [ ] Pumpfun 
    - [ ] 
- [x] AI Model use Vercel AI SDK
- [x] Database Manager 
    - [x] MongoDB
    - [ ] Redis
    - [ ] MySQL
    - [ ] PostgreSQL
    - [ ] SQLite 
    - [ ] Cosmos
- [ ] System 
    - [x] Chat
    - [ ] Plan
    - [ ] Analyze
    - [ ] Decide
    - [ ] Reflection 
    - [ ] Experience



### example 
  - [ ] [The relationship between price and Twitter]
        analyze the relationship between why a CA price rises and the articles on Twitter, for example, why it suddenly rises during a certain historical event, and which posts are responsible, and finally have a complete report.
  - [ ] Deep Analyze the market 

## Prerequisites

- Node.js (version 16 or higher)
- pnpm (package manager)
- MongoDB (version 7.0 or higher)

## Environment Setup

### 1. Install MongoDB (macOS)
```bash
# Install MongoDB
brew tap mongodb/brew
brew install mongodb-community

# Start MongoDB service
brew services start mongodb-community

# Verify installation
mongod --version
mongosh
```

For other platforms, check [MongoDB Installation Guide](https://www.mongodb.com/docs/manual/installation/)

### 2. Project Setup

1. Install pnpm if you haven't:
```bash
npm install -g pnpm
```

2. Install dependencies:
```bash
pnpm install
```

3. Create `.env` file in project root:
```env
MONGODB_URI=mongodb://localhost:27017
TELEGRAM_TOKEN=your_telegram_bot_token
```

4. Create type declarations for bitECS:
Create a file at `src/types/bitecs.d.ts`:
```typescript
declare module 'bitecs' {
  export function createWorld(): any
  export function defineComponent(schema: any): any
  export const Types: {
    f32: symbol
    f64: symbol
    i8: symbol
    i16: symbol
    i32: symbol
    ui8: symbol
    ui16: symbol
    ui32: symbol
  }
}
```

## Development Commands

```bash
# Start development mode (watch mode)
pnpm dev

# Build project
pnpm build

# Run tests
pnpm test

# Run index.ts once
pnpm start

# Run index.ts in development mode (auto-reload)
pnpm start:dev
```

## Project Structure

```
.
├── src/
│   ├── types/        # Type declarations
│   ├── components/   # ECS components
│   ├── systems/      # ECS systems
│   └── index.ts      # Main entry point
├── dist/            # Compiled files
├── tests/           # Test files
└── package.json     # Project configuration
```

## Troubleshooting

### MongoDB Issues
- Check if MongoDB is running: `brew services list`
- Check MongoDB logs: `tail -f /usr/local/var/log/mongodb/mongo.log`
- Default MongoDB URI: `mongodb://localhost:27017`

For more help, check [MongoDB Documentation](https://www.mongodb.com/docs/)

## License

MIT