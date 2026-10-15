# DevOps Terminal Toolkit

**A reproducible, productivity-focused Windows terminal environment for DevOps engineers.**

A collection of modern CLI tools, PowerShell configurations, and practical workflows designed to improve navigation, Git operations, code inspection, and day-to-day DevOps productivity.

## Features

- Modern terminal prompt with Git branch and repository status
- Syntax highlighting for YAML, JSON, Groovy, Python, and Dockerfiles
- Interactive file search with live previews
- Predictive command history
- Visual Git management
- Smart directory navigation
- Reusable PowerShell functions
- Portable configuration templates

## Tech Stack

| Tool | Purpose |
|---|---|
| [Starship](https://starship.rs/) | Customizable cross-shell prompt |
| [Nerd Fonts](https://www.nerdfonts.com/) | Terminal fonts and icons |
| [eza](https://github.com/eza-community/eza) | Modern file and directory listing |
| [PSReadLine](https://github.com/PowerShell/PSReadLine) | Predictive command history |
| [fzf](https://github.com/junegunn/fzf) | Interactive fuzzy finder |
| [bat](https://github.com/sharkdp/bat) | Syntax-highlighted file viewer |
| [ripgrep](https://github.com/BurntSushi/ripgrep) | Fast recursive code search |
| [Lazygit](https://github.com/jesseduffield/lazygit) | Terminal UI for Git |
| [zoxide](https://github.com/ajeetdsouza/zoxide) | Smart directory navigation |

## Requirements

- Windows 10 or 11
- Windows PowerShell 5.1 or PowerShell 7
- Visual Studio Code
- WinGet package manager
- Git
- PSReadLine 2.2 or later for predictive ListView

## Quick Start

### 1. Clone the repository

```powershell
git clone https://github.com/GuillermoDiaz89/devops-terminal-toolkit.git
cd devops-terminal-toolkit
```

### 2. Install CLI tools

```powershell
winget install --id Starship.Starship -e
winget install --id eza-community.eza -e
winget install --id junegunn.fzf -e
winget install --id sharkdp.bat -e
winget install --id BurntSushi.ripgrep.MSVC -e
winget install --id JesseDuffield.lazygit -e
winget install --id ajeetdsouza.zoxide -e
```

Install JetBrains Mono Nerd Font separately and configure it as the VS Code terminal font.

### 3. Configure PowerShell

After the configuration templates are added to this repository, follow the setup instructions to configure Starship, PSReadLine, zoxide, and the custom PowerShell functions.

Do not overwrite an existing PowerShell profile without backing it up first.

## Everyday Commands

| Command | Description |
|---|---|
| `ll` | Detailed file listing with icons |
| `lt` | Directory tree |
| `ff` | Interactive file finder with preview |
| `bat config.yaml` | Inspect a YAML file |
| `rg "qualityGate"` | Search repository content |
| `lazygit` | Open Git terminal UI |
| `z project` | Jump to a frequently visited directory |
| `zi` | Interactive directory selection |

The `ll`, `lt`, and `ff` commands are custom PowerShell functions provided by the configuration templates.

## Example Workflow

Find a Jenkins Shared Library file:

```powershell
rg --files -g "*.groovy" | fzf
```

Inspect a configuration file:

```powershell
bat config.yaml
```

Review repository changes:

```powershell
lazygit
```

Navigate between frequently visited projects:

```powershell
z project-name
```

## Project Structure

```text
devops-terminal-toolkit/
├── README.md
├── LICENSE
├── .gitignore
├── install.ps1
├── config/
│   ├── powershell-profile.ps1
│   ├── starship.toml
│   └── vscode-settings.json
├── docs/
│   ├── installation.md
│   ├── commands.md
│   └── troubleshooting.md
└── screenshots/
```

Some files shown above are planned and will be added progressively.

## Roadmap

- [x] Document recommended tools
- [x] Provide manual installation commands
- [ ] Add portable PowerShell configuration
- [ ] Add Starship and VS Code templates
- [ ] Develop an idempotent PowerShell installer
- [ ] Add dependency and installation validation
- [ ] Add screenshots and troubleshooting examples
- [ ] Test on clean Windows PowerShell 5.1 and PowerShell 7 environments
- [ ] Publish the first stable release

## Security Considerations

- Review scripts before execution.
- Follow organizational software installation policies.
- Never commit credentials, access tokens, private keys, or internal configuration.
- Back up existing shell profiles before making changes.
- Review Git operations before pushing or rewriting history.

## Contributing

Contributions, bug reports, documentation improvements, and suggestions are welcome. Open an issue to propose a change.

## License

A license will be added before the first stable release.

---

Built for DevOps engineers who want a faster, more consistent, and maintainable terminal workflow.
