# ALVIS — Voice Intelligence System

ALVIS is a single-file, browser-based voice intelligence interface with a futuristic UI, an audio-reactive 3D orb, and support for connecting to either a Hermes Agent backend or a local Ollama instance.

It is built as a lightweight front end for conversational AI workflows. The app can monitor microphone input for live visual feedback, send messages to a backend, stream responses, and display session and runtime metrics directly in the browser.

## Features

* Single-file HTML app with no build step required
* Futuristic sci-fi dashboard interface
* Audio-reactive 3D orb powered by Three.js
* Real-time microphone level monitoring
* Chat mode with streaming responses
* Backend support for:

  * Hermes Agent
  * Ollama (local)
* Connection health checks and latency display
* Session metrics such as uptime, token count, and message stats
* Persistent browser settings
* Clean status panels for logs, backend state, and conversation

## Tech Stack

* HTML5
* CSS
* React 18
* Framer Motion
* Three.js
* Web Audio API
* Browser speech synthesis
* Fetch API with SSE/streaming

## What ALVIS Does

ALVIS acts as a voice-first front end for AI systems. The center orb reacts to microphone activity and system state, while the surrounding interface exposes backend configuration, chat history, tool availability, and runtime information.

This makes it useful for:

* local AI demos
* agent dashboards
* voice-enabled prototypes
* backend integration testing
* experimental AI interfaces

## Requirements

* A modern browser, preferably Chromium-based
* Microphone permission for live audio monitoring
* A running backend if you want chat responses:

  * Hermes Agent API server, or
  * Ollama running locally on `localhost:11434`

## Getting Started

1. Save the file as `index.html` or keep the existing filename.
2. Open it in a browser, or serve it from a local static server.
3. Allow microphone access when prompted.
4. Open the settings/API panel and configure the backend endpoint.

### Optional local server

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Backend Configuration

### Hermes Agent

Use Hermes mode when connecting to a Hermes Agent server.

Typical settings:

* API server URL: `http://localhost:8642`
* API key: optional, depending on your setup
* Session ID: stored locally and editable in the UI

Hermes mode is intended for:

* streaming chat
* agent-style runs
* backend-reported tool usage

### Ollama

Use Ollama mode for a local model server.

Typical settings:

* Endpoint: `http://localhost:11434`
* Model: a pulled Ollama model such as `qwen3.5:9b`

Ollama mode is chat-focused and does not use the Hermes agent/tooling surface.

## Usage

Once the page is open:

* Click the mic control to enable audio monitoring
* Type a message in the chat input to send a prompt
* Use the settings/API panel to switch backend modes
* Watch backend state, latency, and session stats update in real time

## Important Notes

* Microphone input is used for visual feedback and state changes.
* Speech-to-text is not fully wired in this file yet; there is a placeholder integration point for a local STT engine such as Whisper.
* Settings are stored in the browser so the app can restore your last configuration.
* No framework build pipeline is required because the app runs directly in the browser.

## Project Structure

This repository currently contains one file:

```text
ALVIS_V5_1test.html
```

That file includes:

* the styles
* the React components
* the Three.js orb renderer
* audio handling
* backend connection logic
* the full user interface

## Roadmap Ideas

* Add real speech-to-text support
* Add transcript capture
* Add conversation export
* Add model presets
* Split the prototype into reusable components
* Add theming and layout options

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Credits

Built as a browser-based voice intelligence interface using React, Three.js, and modern web APIs.
