# Mercury Diffusion Chat

A custom, single-file chat interface for [Mercury 2](https://www.inceptionlabs.ai/), Inception Labs' text diffusion model. Unlike autoregressive models that write left-to-right, Mercury generates by refining the whole response at once — so responses in this UI "resolve" onto the screen out of noise instead of typing out token by token, echoing how the model actually works.

![status](https://img.shields.io/badge/status-personal%20project-blueviolet) ![type](https://img.shields.io/badge/type-single%20HTML%20file-informational)

## Live Demo

**Try it directly in your browser:** [Click here to open](https://tanzinabdul.github.io/mercury-text-diffusion-model-custom-cui/)

No installation required — open the link, add your Inception Labs API key in settings, and start chatting right away.

## Features

- Real multi-turn conversations (full message history is sent with every request, not one-shot Q&A)
- Multiple saved threads/conversations in a sidebar, stored locally in your browser
- Proper LaTeX rendering — math is extracted and rendered *before* Markdown parsing runs, so formulas with underscores, asterisks, etc. no longer get mangled
- Diffusion-style message reveal animation
- Dark/light themes, mobile-responsive layout, reduced-motion support
- Your API key lives only in your browser's local storage — it is never hardcoded into the file

## Getting started

1. **Download `mercury-chat.html`** from this repo (or clone it).
2. **Open it in your browser** — just double-click the file, or run a tiny local server if your browser blocks local file requests:
   ```bash
   python3 -m http.server 8000
   # then visit http://localhost:8000/mercury-chat.html
   ```
3. Click the **gear icon** in the sidebar and paste in your Inception Labs API key (see below).
4. Start chatting.

No build step, no dependencies to install — it's a single HTML file.

## Getting an Inception Labs API key

Mercury is made by [Inception Labs](https://www.inceptionlabs.ai/), and their API is separate from Anthropic/Claude — you'll need your own key from them:

1. Go to **[platform.inceptionlabs.ai](https://platform.inceptionlabs.ai)** and create an account (this is separate from any Inception "playground" account you may already have).
2. Once signed in, go to **API Keys** in the dashboard and click **Create new key**.
3. New accounts are automatically granted **10 million free tokens** — no credit card required to get started.
4. Copy the generated key (it starts with `sk_`).
5. Paste it into this app's settings modal (gear icon → API key field). It's saved in your browser's local storage and used only to call `https://api.inceptionlabs.ai/v1/chat/completions` directly from your machine.
6. When your free tokens run low, add billing details under **Billing** in the same dashboard to keep going — current pricing is listed on Inception's [models page](https://www.inceptionlabs.ai/models).

> Keep your key private. Anyone with it can make API calls billed to your account. If you ever paste a key into a file you plan to share or commit to a public repo, revoke it from the dashboard and generate a new one.

## Notes

- This is a personal/community project and is not affiliated with or endorsed by Inception Labs.
- Reasoning effort (low/medium/high) can be changed in the settings modal — this maps to Mercury's `reasoning_effort` parameter.
- All conversation history is stored locally in your browser only; nothing is sent anywhere except directly to Inception Labs' API.
