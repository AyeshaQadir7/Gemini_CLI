# Gemini CLI Complete Guide


**Gemini CLI** is a powerful, developer-friendly **command-line interface** designed to help you **build, deploy, and manage modern web applications** with speed and simplicity. Whether you're a solo developer or part of a large engineering team, Gemini CLI streamlines your workflow — from project creation to production deployment — in just a few commands.

---

## Overview

Gemini CLI is built for **efficiency, flexibility, and automation**. It eliminates repetitive setup steps and unifies your build and deploy workflows across environments.

### Key Features

- **Zero-config project initialization** — spin up a new app in seconds.  
- **Unified build & deploy pipeline** — consistent results locally and in CI/CD.  
- **Plugin system** — extend functionality with custom integrations.   
- **Cross-platform support** — works on macOS, Linux, and Windows.

What makes Gemini CLI unique:
> 🔧 **Developer-centric design** — every command is built around real developer workflows, with intuitive defaults and smart error handling.

---

## Installation & Setup

Before installing, ensure the following prerequisites are met:

### Prerequisites

- **Node.js version** `>= 20 or higher`
- **npm** or **yarn**


### Installation

#### macOS / Linux


### Using npm
```bash
npm install -g @gemini/cli
```

### Using yarn
```bash
yarn global add @gemini/cli
```

#### Windows (PowerShell)

```bash
npm install -g @gemini/cli
```

Verify installation:

```bash
gemini --version
```

Expected output:

```
Gemini CLI v1.0.0
```

---

## Getting Started

Create your first project with Gemini in seconds.

### Start Gemini CLI:

```
gemini
```


## Understanding the Interface

Gemini CLI follows a **modular command structure** for clarity and extensibility.

### Command Structure

```
gemini <command> [options]
```

### Core Commands

| Command  | Subcommands / Options           | Description                                      |
| -------- | ------------------------------- | ------------------------------------------------ |
| `create` | `--template <name>`             | Scaffold a new app from a template               |
| `build`  | `--prod`, `--watch`             | Build your project for production or development |
| `deploy` | `--env <name>`, `--token <key>` | Deploy to a specific environment                 |
| `config` | `--set`, `--get`, `--list`      | Manage configuration values                      |

Example:

```bash
gemini deploy --env staging
```

---

## 🛠️ Practical Example: Building a Web App

Let’s walk through building and deploying a simple React app with Gemini CLI.

### 1. Create the Project

```bash
gemini create my-react-app --template react
```

### 2. Configure Environment

```bash
cd my-react-app
gemini config set API_URL=https://api.example.com
```

### 3. Build the App

```bash
gemini build --prod
```

You’ll see:

```
✓ Optimized assets
✓ Built for production
✓ Output: dist/
```

### 4. Deploy to Production

```bash
gemini deploy --env production
```

Expected output:

```
Deploying to production...
✓ Deployment complete!
App available at: https://my-react-app.gemini.cloud
```

### Troubleshooting

* **Build fails**: Ensure Node.js version ≥ 18 and dependencies are installed.
* **Deployment errors**: Verify your API token using `gemini config --list`.
* **Environment issues**: Run `gemini env sync` to refresh environment variables.

---

## 💡 Tips & Best Practices

* **Use `.env.local`** for local overrides without committing sensitive data.
* **Automate builds** via CI pipelines using `gemini build --ci`.
* **Use templates** to speed up repetitive project setups:

  ```bash
  gemini create my-app --template vue
  ```
* **Stay updated**:

  ```bash
  npm update -g @gemini/cli
  ```

---

## 🤝 Contributing

Contributions are always welcome! 💬

1. Fork the repository.
2. Create your feature branch:

   ```bash
   git checkout -b feature/my-feature
   ```
3. Commit your changes:

   ```bash
   git commit -m "Add new feature"
   ```
4. Push and open a pull request.

Report bugs or request features through the [Issues](https://github.com/gemini/cli/issues) page.

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](./LICENSE) file for details.

---

## 🌐 Credits

Gemini CLI is developed and maintained by the **Gemini Open Source Team**.
Special thanks to all community contributors for making Gemini better every day.

> “Build fast. Deploy smarter. Manage effortlessly.” — *Gemini CLI Team*

```
```
