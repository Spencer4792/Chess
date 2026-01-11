# ♔ Java Chess Game ♚

A full-featured chess game with multiple themed boards, and complete chess rules implementation.

![Chess Game](https://img.shields.io/badge/Game-Chess-brown)
![Java](https://img.shields.io/badge/Java-21+-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## Play Now

**[Play Chess Online](https://spencer4792.github.io/Chess/)** - No installation required

---

## Files
- `chess-server.jar` - The chess server (in-memory storage by default)
- `index.html` - Static web version for GitHub Pages

## Running the Server Version

### Start the Server
```bash
java -jar chess-server.jar
```
If you are in the chess directory:
```bash
java -jar server/target/chess-server.jar
```

The server will start on port 8080 by default. You'll see:
```
Chess server started on port 8080
Using in-memory storage
Press Ctrl+C to stop the server
```

**Server Options:**
- `--port <number>` - Use a different port
- `--db` - Use MySQL database instead of in-memory storage (requires MySQL setup)

### Access the Web Interface
Once the server is running, open your browser to:
```
http://localhost:8080/chess.html
```

### Playing the Game

**Authentication:**
1. **Register** - Create a new account (username, password, email)
2. **Login** - Sign in with existing account

**Lobby:**
1. **Create Game** - Create a new chess game
2. **Solo** - Create a game where you play both sides
3. **Join Game** - Join an existing game as WHITE or BLACK
4. **Watch** - Observe a game without playing
5. **Refresh** - Update the game list

**Gameplay:**
- Click a piece to select it
- Green dots show valid moves
- Red borders indicate captures
- Click a highlighted square to move
- Pawn promotion modal appears when a pawn reaches the end

## Two-Player Setup
1. Start the server
2. Player 1 opens `http://localhost:8080/chess.html`, registers/logs in
3. Player 1 creates a game and joins as WHITE
4. Player 2 opens the same URL in another browser/tab
5. Player 2 registers/logs in, finds the game, joins as BLACK
6. Play alternates between players via WebSocket (real-time updates)

---

## Board Themes

Switch themes anytime using the buttons above the board:

| Theme | Light Squares | Dark Squares | Frame Style |
|-------|--------------|--------------|-------------|
| **Classic** | Tan | Brown | Mahogany + Gold |
| **Marble** | White | Gray | Charcoal + Gold |
| **Egyptian** | Sand | Gold | Black + Gold |
| **Roman** | Cream | Terra Cotta | Sienna + Bronze |
| **Greek** | White | Blue | Navy + Gold |
| **Indian** | Cream | Crimson | Maroon + Pink |
| **Persian** | Ivory | Forest Green | Dark Green + Brass |

---

## Features

### Game Features
- Full chess rules including castling, en passant, and pawn promotion
- Check and checkmate detection
- Stalemate detection
- Turn-based play enforced by server
- Valid move highlighting
- Captured pieces display
- Last move indication

### Technical Features
- Real-time updates via WebSocket
- Game state persistence (in-memory or MySQL)
- RESTful API for game management
- Responsive web design
- 7 board themes

---

## Requirements

### Server Version
- Java 21 or higher
- Network connectivity between server and clients

### Static Version
- Any modern web browser
- No installation required

---

## Architecture

```
Chess/
├── server/
│   └── target/
│       └── chess-server.jar    # Compiled server
├── shared/                      # Chess game logic, piece movement rules
├── client/                      # Legacy terminal client
├── index.html                   # Static web version
└── README.md
```

- **Shared**: Chess game logic, piece movement rules
- **Server**: REST API + WebSocket for real-time updates, Spark framework
- **Web Client**: Interface with real-time WebSocket updates

---

## License

MIT License
