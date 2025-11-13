# Gemini CLI - Complete Guide

**Gemini CLI** is an open-source powerful, developer-friendly **command-line interface** designed to help you **build, deploy, and manage modern web applications** with speed and simplicity directly into your terminal.For example, you can ask Gemini CLI to generate or explain code, fix bugs, write tests, or automate tasks – all from the command line.


## Key Features

- **Zero-config project initialization** — spin up a new app in seconds.  
- **Unified build & deploy pipeline** — consistent results locally and in CI/CD.  
- **Plugin system** — extend functionality with custom integrations.  
- **Environment management** — handle `.env` files and secrets with ease.  
- **Cross-platform support** — works on macOS, Linux, and Windows.
- **Developer-centric design** — every command is built around real developer workflows, with intuitive defaults and smart error handling.

- **Native Gemini integration**: Connects to Gemini 2.5 Pro (with up to 1M token context) for powerful code understanding and generation.
- **Built-in tools**: Includes web search, file I/O, shell commands, and more to ground responses with real data.
- **Multimodal app generation**: Can create new apps from text descriptions, PDFs, images or sketches.
- **Extensibility**: Supports Model Context Protocol (MCP) for custom tools and media generation (e.g. Imagen).
- **Terminal-first and open-source**: Designed for developers who live in the CLI, and released under Apache 2.0.

Compared to traditional CLIs, Gemini CLI uses a **conversational REPL interface**. You interact with it by typing questions or commands (e.g. “Create a web server”) rather than memorizing dozens of subcommands.

## Installation & Setup

### Prerequisites
You’ll need **Node.js (version 20 or higher)**
#### Check Node.js version: 
```node -v```

If below 20, download from nodejs.org.

### Installation Methods

1. **Standard install (npm)**  
   ```bash
   npm install -g @google/gemini-cli
   ```
   This installs the `gemini` command globally.

2. **Run without install (npx)**  
   ```bash
   npx @google/gemini-cli
   ```
   This runs the latest CLI without installing it permanently.

3. **Homebrew (macOS/Linux)**  
   ```bash
   brew install gemini-cli
   ```
   (Available on Homebrew for quick setup.)


#### After installation, verify by running:
```bash
gemini --version
```

## Getting Started / Quick Start Guide

To start a Gemini session:
```bash
gemini
```

The CLI will launch an interactive REPL. On first run it will prompt you to authenticate (e.g. “Login with Google” or “Use Gemini API key”) and follow the instructions.

Once authenticated, you can ask questions or give commands. Example:
```bash
gemini "Generate a simple Express.js app with a /hello endpoint"
```

Gemini CLI will ask for permission before modifying files:
```
Gemini: Would you like to create the file server.js? (yes/no)
```
Select `yes` to allow.

### Sample Session
```bash
$ gemini
🔍 Gemini CLI  > Hello! What would you like me to do?

> "Create a Node.js API server with an endpoint /status"
Gemini: I will create `index.js`. Proceed? (yes/no)
> yes
Gemini: (writes files)
Gemini: Done. What next?
```

After files are generated, run normal project commands (`npm install`, `npm start`, etc.).

You can continue iterating:
```bash
gemini "Add user authentication to this Express app"
```

Save/resume sessions:
```bash
gemini /chat save myTest
gemini /chat resume myTest
```

Get help:
```bash
gemini /help
```

## Understanding the Interface

Gemini CLI runs as an **interactive terminal REPL**. You type requests or prompts in plain English, and Gemini replies or performs actions.

### Special Commands & Shortcuts

- **Slash commands (`/`)**:
  - `/clear` – Clears the terminal display
  - `/stats` – Shows session statistics (token usage, time)
  - `/memory add <text>` – Adds info to Gemini’s memory context
  - `/restore` – Revert project files to a previous state
  - `/help` – Display help
  - `/tools` – List available built-in tools
  - `/quit` – Quit the program 

- **Shell passthrough (`!`)** – Run local shell commands:
  ```bash
  !ls -la
  !npm test
  ```

- **File reference (`@`)** – Include file contents in prompt:
  ```
  @package.json Explain what this project does
  ```

- **Keyboard shortcuts**: `Ctrl+L` clears the screen (same as `/clear`)

Gemini CLI is **prompt-driven** — no need to memorize subcommands like `gemini create`.

Example:
```bash
gemini "Initialize a new React web app with user login functionality"
```

## Practical Example: Building a Web App

1. **Initialize a project directory**
   ```bash
   mkdir myapp && cd myapp
   npm init -y
   ```

2. **Generate the app structure**
   ```bash
   gemini "Generate a simple Express.js web server with a GET /status endpoint"
   ```
   Confirm file creation → creates `index.js`

3. **Install dependencies and run**
   ```bash
   npm install express
   node index.js
   ```
   Visit `http://localhost:3000/status`

4. **Add features interactively**
   ```bash
   gemini "Add a POST /login route that checks username/password"
   ```

5. **Write unit tests**
   ```bash
   gemini "Write unit tests for Login.js"
   ```

6. **Troubleshoot errors**
   ```bash
   gemini "Fix the ‘module not found’ error by installing any missing packages"
   ```

7. **Deployment hints (CI/CD)**
   ```bash
   gemini "Generate a Dockerfile for this Node.js app"
   ```
   ```bash
   gemini "Initialize a git repository and make the first commit"
   ```

To exit: `/quit` or `Ctrl+C`

## Tips & Best Practices

- Always review changes before confirming file edits
- Use `--sandbox` mode for extra safety (runs tools in Docker)
- Install latest (`@latest`), preview (`@preview`), or nightly (`@nightly`) via npm
- Create a `GEMINI.md` file in your project for persistent context
- Use `/memory add <text>` to give Gemini domain-specific info
- Monitor usage with `/stats`
- Revert mistakes with `/restore`
- For CI/headless: set `GEMINI_API_KEY` environment variable
- Keep updated — new features/fixes released weekly



### Links

- Documentation: https://docs.cloud.google.com/gemini/docs/codeassist/gemini-cli
- GitHub: https://github.com/google-gemini/gemini-cli
- Official site: https://geminicli.com
- Authentication: https://geminicli.com/docs/get-started/authentication/
- Examples: https://geminicli.com/docs/get-started/examples/
- CLI Commands: https://geminicli.com/docs/cli/commands/
