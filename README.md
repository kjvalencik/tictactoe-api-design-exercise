# API Design Exercise

> 👋🏻 This repo is designed as a starting point for practicing API design. It's intended to go along with a talk I gave and may not make much sense without it.

## Problem

We would like to build the world's best Ultimate Tic-Tac-Toe SDK. Our users will build beautiful apps on top of the SDK with amazing UX, but it's our responsibility to handle the game rules and state.

Build an easy to use, but flexible, API for managing the state of an Ultimate Tic-Tac-Toe Game.

### Ultimate Tic-Tac-Toe Rules

Ultimate Tic-Tac-Toe is a variation on traditional tic-tac-toe. To recap traditional [tic-tac-toe][tic-tac-toe-wiki]:

1. Each player is assigned either "X" or "O"
2. Players alternate placing their letter on a grid
3. A player wins when they have three of their letter in a column, row, or diagonal
4. If no player has one and there are no remaining empty spaces, the game ends in a draw

```
 X | O |
---|---|---
   | X |
---|---|---
   | O | X
```

Ultimate Tic-Tac-Toe is a [variant of tic-tac-toe][ultimate-wiki] played on nested boards. Try playing an [interactive version here][ultimate-game].

![Incomplete Ultimate Tic-Tac-Toe][ultimate-img]
> https://en.wikipedia.org/wiki/Ultimate_tic-tac-toe#/media/File:Incomplete_Ultimate_Tic-Tac-Toe_Board.png \
> CC BY-SA 4.0

#### Winning

A player wins Ultimate-Tic-Toe by getting three in a row on the outer board.

Inner games are played with traditional tic-tac-toe rules.

#### Taking turns

1. The first player places their letter on any space of an inner board.
2. The next player finds the game in the outer board that corresponds to the same position the previous player played on the inner board. For example, if the previous player placed their mark on the middle space of the inner board, this player *must* pick a space in the middle board.
3. If there are no empty spaces on the assigned board, the player may pick a space on any game.
4. If the move results in winning the inner game, the outer space is marked with the players letter.
5. Game play repeats until there is a winner or a draw.

[tic-tac-toe-wiki]: https://en.wikipedia.org/wiki/Tic-tac-toe
[ultimate-wiki]: https://en.wikipedia.org/wiki/Ultimate_tic-tac-toe
[ultimate-game]: https://ultimate-t3.herokuapp.com/
[ultimate-img]: assets/ultimate-board.png

## Exercise

Design an API for managing the state of a game. Some things to consider:

* How will the UI maintain the latest view of the game?
* How does the UI know available moves for the player?
* Which players turn is it?
* Can multiple games be supported?
* Can the SDK support networked games or only local games?

It is encouraged to provide as much information as possible to make it easy for a UI developer to integrate with the library (API docs, examples, etc.). However, it is *not* necessary to provide any implementations.

## Usage

This package uses TypeScript and is bootstrapped with a few tools, but don't feel obligated to use them! If you prefer to use a different toolset (e.g., `rustdoc`), go for it!

### `npm run check`

Check the TypeScript compiles.

### `npm run doc`

Build documentation.

```sh
open docs/index.html
```

## Tip

It's not necessary to pull this down locally. You can type `.` and GitHub will open an instance of VSCode in the browser!
