# Java Chess Game - Compiled JARs

## Files
- `chess-server.jar` - The chess server (in-memory storage by default)
- `chess-client.jar` - Terminal-based chess client

## Running the Game

### Start the Server
```bash
java -jar chess-server.jar
if you are in the chess directory, then use java -jar server/target/chess-server.jar
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

### Start the Client(s)
In separate terminal windows, run:
```bash
java -jar server/target/chess-server.jar
Amd then in your browser run: http://localhost:8080/chess.html
```

### Playing the Game

**Prelogin Menu:**
1. **Register** - Create a new account (username, password, email)
2. **Login** - Sign in with existing account
3. **Quit** - Exit the client

**Postlogin Menu:**
1. **Create Game** - Create a new chess game
2. **List Games** - View all available games
3. **Join Game** - Join an existing game as WHITE or BLACK
4. **Observe Game** - Watch a game without playing
5. **Logout** - Return to prelogin menu

**Gameplay:**
- Moves use standard chess notation
- Example: `e2 e4` (move pawn from e2 to e4)
- Example: `e1 g1` (castle kingside)
- The board is displayed in the terminal with piece symbols

## Two-Player Setup
1. Start the server
2. Open two terminal windows for two clients
3. Each player registers/logs in
4. Player 1 creates a game and joins as WHITE
5. Player 2 lists games, joins the same game as BLACK
6. Play alternates between players via WebSocket

## Features
- Full chess rules including castling, en passant, and pawn promotion
- Check and checkmate detection
- Turn-based play enforced by server
- Real-time updates via WebSocket
- Game state persistence (in-memory or MySQL)

## Requirements
- Java 21 or higher
- Network connectivity between server and clients

## Architecture
- **Shared**: Chess game logic, piece movement rules
- **Server**: REST API + WebSocket for real-time updates, Spark framework
- **Client**: Terminal UI with ANSI colors, WebSocket client
