# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file Tic Tac Toe web game (`tictactoe.html`). No build system, package manager, or external dependencies — open the file directly in a browser to play.

## Git Workflow

After creating or significantly changing any file, commit with a clean, descriptive, present-tense imperative message and push to the `dadekdigital/claude-projects` remote on GitHub. Never leave work uncommitted.

## Development

To run: open `tictactoe.html` in any browser (no server required).

## Architecture

Everything lives in `tictactoe.html`:

- **CSS** (inline `<style>`): dark-themed UI with a 3×3 CSS Grid board, cell hover/win animations, and a scoreboard.
- **HTML**: static 9-cell board (`data-i` attributes for indexing), status line, scoreboard spans, and a restart button.
- **JS** (inline `<script>`): vanilla JS, no frameworks.
  - `WINS`: hardcoded array of all 8 winning index triplets.
  - `board[]`: flat 9-element array (`''`, `'X'`, or `'O'`).
  - `init()`: resets board state and DOM.
  - `checkWinner()`: iterates `WINS`; returns winner+line, draw object, or `null` (game ongoing).
  - Click handler on each cell drives all game logic; score persists across rounds in the `score` object.
