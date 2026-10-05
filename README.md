# Game2048

## Introduction

**Game2048** is a browser version of the classic 2048 puzzle, built with vanilla JavaScript and an object-oriented design. The player slides numbered tiles across a 4x4 board, merging identical values to build up to the legendary **2048** tile. The game is intentionally framework-free and focuses on clean code and a clear separation between game logic and user interface.

### Key Features

- **Tile Sliding and Merging**: Tiles move in four directions, and equal neighbours combine into one tile with the doubled value.
- **Keyboard Controls**: The whole game is played with the arrow keys.
- **Live Score**: The score grows with every merge and is refreshed instantly on the screen.
- **Game Status Detection**: The game recognises the idle, playing, win and lose states and displays the matching message.
- **Start and Restart Buttons**: A session can be launched or reset at any moment without reloading the page.
- **Custom Favicon**: The browser tab shows a dedicated game icon.

## Challenges

The main difficulty of the project was building a reliable game engine rather than drawing the interface.

### Key Challenges:

1. **Move and Merge Algorithm**: Each row or column has to be compacted, merged and compacted again, while making sure a freshly merged tile cannot merge twice in a single move.
2. **Loss Detection**: A full board does not always mean defeat, so the game must also check that no adjacent tiles can still be combined.
3. **Valid Move Handling**: A new tile should appear only when a move really changed the board, otherwise blocked moves would give the player free tiles.
4. **Single Source of State**: The board, score and status live in the `Game` class only, and the UI layer simply reads and renders them without keeping its own copy.

## Technical Requirements

To run this project, you will need:

- Modern web browser (latest versions of Chrome, Firefox, Safari, or Edge)
- Node.js (version 16.x or newer)
- NPM (version 8.x or newer) or Yarn

## Installation and Setup

To get a local copy of the project up and running, follow these steps:

1. Clone the repository:
```bash
    git clone https://github.com/maximtsyrulnyk/Game2048.git
```

2. Move to the project folder:
```bash
    cd Game2048
```

3. Install the dependencies:
```bash
    npm install
```

4. Launch the development server:
```bash
    npm start
```

## Usage

After the server starts, open the address shown in your terminal (typically `http://localhost:1234`). Then:

- Press **Start** to begin a new game.
- Use the **arrow keys** (`←` `↑` `→` `↓`) to slide the tiles.
- Press **Restart** to reset the board and the score.

You win when the **2048** tile appears, and you lose when the board is full and no merges are possible.

## Example

- [LIVE DEMO](https://maximtsyrulnyk.github.io/Game2048/)
- [FIGMA DESIGN](https://www.figma.com/)

## Technologies Used

This project was built using the following technologies:

- **HTML5**: For the page structure and semantic markup.
- **CSS3 / SCSS**: For styling the board and tiles and for responsive layout.
- **JavaScript (ES6+)**: For the game logic, classes, modules and event handling.
- **Parcel**: For bundling the sources and running the dev server.
- **Git**: For version control.
- **GitHub / GitHub Pages**: For hosting the repository and the live demo.

## Design Specifications

- **Design Sizes**:
  - Desktop: 1280px
  - Tablet: 640px
  - Mobile: > 320px
- **Favicon**: `src/images/favicon.png`, connected in `index.html`.

## Project Structure

```
Game2048/
├── src/
│   ├── images/
│   │   └── favicon.png
│   ├── scripts/
│   │   ├── main.js            # DOM updates and event listeners
│   │   └── modules/
│   │       └── Game.class.js  # game rules and state
│   ├── styles/
│   │   └── main.scss
│   └── index.html
├── package.json
└── README.md
```

## Author

**Maksym Tsyrulnyk** — [GitHub](https://github.com/maximtsyrulnyk)
