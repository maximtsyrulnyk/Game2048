🎮 2048 Game

Show Image Show Image Show Image Show Image Show Image

A classic 2048 puzzle game built with vanilla JavaScript using an object-oriented approach. Slide numbered tiles on a 4×4 grid, merge equal values and reach the 2048 tile before the board fills up.

The project is intentionally framework-free: all game logic lives in a standalone Game class that knows nothing about the DOM, while the UI layer only renders its state and forwards user input.

📸 Preview

Replace the paths below with your own screenshots / GIF (docs/ folder).

Gameplay	Win state	Game over
Show Image	Show Image	Show Image

🔗 Live demo: [DEMO_LINK](https://maximtsyrulnyk.github.io/js_2048_game/) 🎨 Design reference: Figma layout (insert the direct link to the specific frame)

📚 Table of Contents
Features
How to Play
Tech Stack
Architecture
Project Structure
Getting Started
Available Scripts
Deployment
Roadmap
Author
License
✨ Features
Classic 2048 mechanics — tiles slide in four directions, equal tiles merge once per move, a new tile (2 or 4) spawns after every valid move.
Score tracking — points are added for every merge.
Game status detection — the game automatically switches between idle, playing, win and lose states.
Keyboard controls — arrow keys for movement.
Start / Restart buttons — a clean way to begin and reset a session.
Clear separation of concerns — game logic (Game class) is fully decoupled from rendering (main.js).
Responsive layout — styled with SCSS, based on the Figma design.
🕹 How to Play
Action	Control
Move tiles	← ↑ → ↓ arrow keys
Start the game	Start button
Reset the board	Restart button

Rules

Press Start — two random tiles appear.
Use the arrow keys to slide all tiles in one direction.
When two tiles with the same number collide, they merge into one with their sum.
You win when a 2048 tile appears.
You lose when the board is full and no merges are possible.
🛠 Tech Stack
Layer	Technology
Markup	HTML5
Styling	CSS3, SCSS
Logic	JavaScript (ES6+), OOP, ES Modules
Bundler / dev server	Parcel
Deployment	GitHub Pages (gh-pages)
🧩 Architecture

The project follows a simple model–view split:

┌──────────────────┐   user events   ┌─────────────────┐
│     main.js      │ ──────────────▶ │   Game (class)  │
│  (DOM + events)  │ ◀────────────── │  (pure logic)   │
└──────────────────┘   state/score   └─────────────────┘
Game — owns the board matrix, score and status. It has no access to document, so it can be unit-tested in isolation.
main.js — subscribes to keyboard/button events, calls Game methods and re-renders the board, score and messages from the returned state.

Typical public API of the Game class

Method	Description
start()	Fills the board with two initial tiles and sets status to playing.
restart()	Resets board, score and status.
moveLeft() / moveRight() / moveUp() / moveDown()	Slide and merge tiles; spawn a new tile only if the board changed.
getState()	Returns the current 4×4 board.
getScore()	Returns the current score.
getStatus()	Returns idle, playing, win or lose.

Game status flow

start()
2048 tile reached
no moves left
restart()
restart()
restart()
idle
playing
win
lose

⚠️ Adjust method names and statuses to match your actual implementation.

📁 Project Structure
js_2048_game/
├── docs/                # screenshots and GIFs for the README
├── src/
│   ├── index.html
│   ├── scripts/
│   │   ├── main.js      # UI layer: DOM updates, event listeners
│   │   └── modules/
│   │       └── Game.class.js   # core game logic
│   └── styles/
│       └── main.scss
├── package.json
└── README.md
🚀 Getting Started
Prerequisites
Node.js v18+
npm (bundled with Node.js) or Yarn
Installation
bash
# 1. Clone the repository
git clone https://github.com/maximtsyrulnyk/js_2048_game.git

# 2. Go to the project folder
cd js_2048_game

# 3. Install dependencies
npm install      # or: yarn install

# 4. Start the dev server
npm start        # or: yarn start

After that the app will be available at http://localhost:1234 (the port may differ — check your terminal output).

📜 Available Scripts
Command	Description
npm start	Runs the development server with hot reload.
npm run build	Creates an optimized production build.
npm run lint	Checks JS/SCSS code style.
npm run deploy	Publishes the build to GitHub Pages.

Keep only the scripts that actually exist in your package.json.

🌐 Deployment

The game is hosted on GitHub Pages. To redeploy after changes:

bash
npm run build
npm run deploy
🗺 Roadmap
 Persist the best score in localStorage
 Touch / swipe controls for mobile devices
 Tile slide and merge animations
 Undo last move
 Unit tests for the Game class (Jest)
 Keyboard accessibility and ARIA labels
👨‍💻 Author

Maksym Tsyrulnyk Junior Full-Stack Developer · Master's student in Computer Science

GitHub: @maximtsyrulnyk
LinkedIn: maksym-tsyrulnyk-994892201
Email: maximtsyrulnyk@gmail.com
📄 License

This project is licensed under the MIT License.
