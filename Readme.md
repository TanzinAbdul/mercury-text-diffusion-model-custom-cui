# Text Diffusion Chat Interface

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

A modern, self‑contained HTML/JavaScript client for the [Inception Labs](https://inceptionlabs.ai) text‑diffusion API (`mercury‑2`). It provides a clean chat interface with real‑time API responses, beautiful rendering of Markdown and LaTeX equations, conversation history, and a collapsible sidebar – all in a single HTML file.

## ✨ Features

- **Real API Integration** – Directly calls `https://api.inceptionlabs.ai/v1/chat/completions` with your prompt.
- **Markdown Rendering** – Supports headers, tables, lists, blockquotes, and code blocks.
- **LaTeX Math** – Renders both inline (`\(...\)`) and display (`\[...\]`) equations via KaTeX.
- **Conversation History** – Automatically saves prompts and responses in your browser’s localStorage. Click any past entry to reload it.
- **Collapsible Sidebar** – Toggle the history panel with a single click; a floating expand button appears when collapsed.
- **Dark / Light Theme** – Switch themes manually; preference is saved.
- **No External Dependencies (except CDN)** – Uses Font Awesome, Marked, and KaTeX loaded from CDN.
- **Zero‑Build, Single File** – Just open the HTML in your browser.

## 🚀 Getting Started

### 1. Obtain an API Key
Sign up at [Inception Labs](https://inceptionlabs.ai) to get your API key. The free tier is sufficient for testing.

### 2. Configure the Key
Open the HTML file and replace the placeholder `API_KEY` with your actual key:

```javascript
const API_KEY = 'sk_xxxx...';  // your key here
