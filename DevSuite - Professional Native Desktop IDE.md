# DevSuite - Professional Native Desktop IDE

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Python](https://img.shields.io/badge/python-3.9+-green.svg)
![License](https://img.shields.io/badge/license-MIT-orange.svg)
![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)

**DevSuite** is a professional, native desktop Integrated Development Environment (IDE) built with Python and PySide6. It's designed to work **offline-first** with optional online features, providing developers with a comprehensive toolkit for modern software development.

## 🌟 Key Features

### Core Features
- ✨ **Native Qt Interface**: Built with PySide6 for true native look and feel
- 🌙 **Dark/Light Themes**: Professional themes with full customization
- 📝 **Advanced Code Editor**: QScintilla-based editor with syntax highlighting
- 🔌 **Offline-First**: All core features work without internet connection
- 🚀 **Fast & Lightweight**: Native performance, no web server required
- 💾 **Project Templates**: Create projects from local or GitHub templates
- 🎨 **Customizable Layout**: Drag-and-drop panels, save workspace layouts

### Development Tools

#### 📝 Code Editor
- Syntax highlighting for 50+ languages
- Code folding and auto-indentation
- Multiple cursors and selections
- Find and replace with regex support
- Line numbers and code minimap
- Bracket matching and auto-completion
- Code snippets library

#### 🔧 Integrated Tools
- **Terminal Emulator**: Multi-tab terminal with custom shells
- **Git Integration**: Visual diff, commit, push/pull, branch management
- **Database Client**: Connect to MySQL, PostgreSQL, SQLite, MongoDB
- **API Tester**: REST client for testing HTTP requests
- **Code Snippets Manager**: Organize and share code snippets
- **Diff Viewer**: Side-by-side file comparison and merge tool
- **Regex Tester**: Live regex testing with visual feedback
- **System Monitor**: CPU, RAM, disk usage monitoring

#### 🤖 AI Assistant (Optional)
- Code completion and suggestions
- Code explanation and documentation
- Bug fixing assistance
- Requires OpenAI API key (stored securely)

#### 🔌 Plugin System
- Extensible architecture
- Sandboxed plugin execution
- Built-in plugins included
- Easy plugin development API

## 📦 Installation

### Prerequisites
- Python 3.9 or higher
- pip package manager
- Git (for Git integration features)

### Quick Install

```bash
# Clone the repository
git clone https://github.com/devsuite/devsuite.git
cd DevSuite

# Create virtual environment (recommended)
python3 -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### Install as Package

```bash
# Install in development mode
pip install -e .

# Run DevSuite
devsuite
```

## 🚀 Running DevSuite

### From Source

```bash
# Navigate to source directory
cd src

# Run the application
python3 -m devsuite.main
```

### From Installed Package

```bash
# Simply run
devsuite
```

## 🏗️ Building Executables

### Using PyInstaller (One-File Executable)

#### Windows
```bash
# Install PyInstaller
pip install pyinstaller

# Build
pyinstaller --clean --onefile ^
    --name DevSuite ^
    --windowed ^
    --icon=assets/icons/app.ico ^
    --add-data "assets;assets" ^
    src/devsuite/main.py

# Output: dist/DevSuite.exe
```

#### macOS
```bash
# Install PyInstaller
pip install pyinstaller

# Build
pyinstaller --clean --onefile \
    --name DevSuite \
    --windowed \
    --icon=assets/icons/app.icns \
    --add-data "assets:assets" \
    src/devsuite/main.py

# Output: dist/DevSuite.app
```

#### Linux
```bash
# Install PyInstaller
pip install pyinstaller

# Build
pyinstaller --clean --onefile \
    --name DevSuite \
    --windowed \
    --add-data "assets:assets" \
    src/devsuite/main.py

# Output: dist/DevSuite
```

### Using Briefcase (Native Packages)

```bash
# Install Briefcase
pip install briefcase

# Create the application
briefcase create

# Build the application
briefcase build

# Run the application
briefcase run

# Package for distribution
briefcase package

# Output:
# - Windows: .msi installer
# - macOS: .dmg disk image
# - Linux: .deb or .rpm package
```

## 📁 Project Structure

```
DevSuite/
├── src/
│   └── devsuite/
│       ├── main.py                 # Application entry point
│       ├── __init__.py            # Package initialization
│       │
│       ├── core/                  # Core functionality
│       │   ├── config_manager.py  # Configuration management
│       │   ├── theme_manager.py   # Theme management
│       │   ├── plugin_manager.py  # Plugin system
│       │   └── project_manager.py # Project management
│       │
│       ├── ui/                    # User interface
│       │   ├── main_window.py     # Main application window
│       │   ├── widgets/           # Custom widgets
│       │   ├── dialogs/           # Dialog windows
│       │   └── panels/            # Side panels
│       │
│       ├── tools/                 # Development tools
│       │   ├── editor/            # Code editor
│       │   ├── terminal/          # Terminal emulator
│       │   ├── git/               # Git integration
│       │   ├── database/          # Database client
│       │   ├── api/               # API tester
│       │   ├── snippets/          # Code snippets
│       │   ├── diff/              # Diff viewer
│       │   ├── regex/             # Regex tester
│       │   └── monitoring/        # System monitor
│       │
│       ├── plugins/               # Plugin system
│       │   ├── builtin/           # Built-in plugins
│       │   └── user/              # User plugins
│       │
│       └── assets/                # Application assets
│           ├── icon.png
│           └── themes/
│
├── assets/                        # External assets
│   ├── monaco/                    # Monaco editor (local)
│   ├── icons/                     # Application icons
│   └── themes/                    # Theme files
│
├── tests/                         # Unit tests
├── docs/                          # Documentation
├── scripts/                       # Build scripts
│
├── requirements.txt               # Python dependencies
├── pyproject.toml                # Project configuration
├── README.md                     # This file
└── LICENSE                       # MIT License
```

## 🛠️ Configuration

### User Configuration

Configuration is stored in:
- **Windows**: `%APPDATA%\DevSuite\config.json`
- **macOS**: `~/.config/devsuite/config.json`
- **Linux**: `~/.config/devsuite/config.json`

### Default Configuration

```json
{
  "theme": "dark",
  "editor": {
    "font_family": "Consolas",
    "font_size": 12,
    "tab_size": 4,
    "word_wrap": false,
    "show_line_numbers": true
  },
  "terminal": {
    "shell": "bash",
    "font_size": 10
  },
  "ai": {
    "enabled": false,
    "api_key": "",
    "model": "gpt-3.5-turbo"
  }
}
```

### Environment Variables

For sensitive data, use environment variables:

```bash
# AI API Key
export DEVSUITE_AI_API_KEY="your-api-key-here"

# Git credentials
export DEVSUITE_GIT_USER="your-username"
export DEVSUITE_GIT_EMAIL="your-email@example.com"
```

Or create a `.env` file in the project root:

```env
DEVSUITE_AI_API_KEY=your-api-key-here
DEVSUITE_GIT_USER=your-username
DEVSUITE_GIT_EMAIL=your-email@example.com
```

## 🔌 Plugin Development

### Plugin Structure

```
my-plugin/
├── plugin.json          # Plugin metadata
├── main.py             # Plugin implementation
├── __init__.py
└── README.md
```

### plugin.json

```json
{
  "name": "my-plugin",
  "display_name": "My Awesome Plugin",
  "version": "1.0.0",
  "description": "Does something awesome",
  "author": "Your Name",
  "license": "MIT",
  "requires": ["requests"],
  "settings": {
    "option1": "default_value"
  }
}
```

### main.py

```python
from devsuite.core.plugin_manager import Plugin

class PluginClass(Plugin):
    def __init__(self):
        super().__init__("my-plugin", "1.0.0")
    
    def load(self) -> bool:
        """Load plugin resources"""
        print(f"[{self.name}] Loading...")
        return True
    
    def enable(self) -> bool:
        """Enable plugin"""
        print(f"[{self.name}] Enabled")
        return super().enable()
    
    def execute(self, action: str, **kwargs):
        """Execute plugin action"""
        if action == "do_something":
            return {"result": "success"}
        return {"error": "Unknown action"}
```

### Installing Plugins

1. Copy plugin folder to `~/.config/devsuite/plugins/`
2. Restart DevSuite
3. Enable plugin in Settings → Plugins

## 🧪 Testing

```bash
# Install test dependencies
pip install pytest pytest-qt pytest-cov

# Run all tests
pytest tests/ -v

# Run with coverage
pytest tests/ --cov=src/devsuite --cov-report=html

# View coverage report
open htmlcov/index.html
```

## 📚 Documentation

Full documentation is available in the `docs/` directory:

- [User Guide](docs/user-guide.md)
- [Developer Guide](docs/developer-guide.md)
- [Plugin API Reference](docs/plugin-api.md)
- [Architecture Overview](docs/architecture.md)
- [Contributing Guide](docs/contributing.md)

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Development Setup

```bash
# Fork and clone the repository
git clone https://github.com/your-username/devsuite.git
cd DevSuite

# Create a branch
git checkout -b feature/my-feature

# Make your changes and test
pytest tests/

# Format code
black src/
isort src/

# Commit and push
git add .
git commit -m "Add my feature"
git push origin feature/my-feature

# Create a pull request
```

## 🐛 Troubleshooting

### Common Issues

**Issue**: Application doesn't start
- **Solution**: Check Python version (3.9+), reinstall dependencies

**Issue**: Monaco editor not loading
- **Solution**: Ensure `assets/monaco/` directory exists with local files

**Issue**: Terminal not working
- **Solution**: Check shell path in settings, install `termqt` package

**Issue**: Plugins not loading
- **Solution**: Verify `plugin.json` format, check console for errors

### Getting Help

- 📖 [Documentation](docs/)
- 💬 [Discussions](https://github.com/devsuite/devsuite/discussions)
- 🐛 [Issue Tracker](https://github.com/devsuite/devsuite/issues)
- 📧 [Email Support](mailto:support@devsuite.dev)

## 📄 License

DevSuite is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## 🙏 Acknowledgments

- Built with [PySide6](https://www.qt.io/qt-for-python)
- Code editor powered by [QScintilla](https://www.riverbankcomputing.com/software/qscintilla/)
- Terminal emulator using [termqt](https://pypi.org/project/termqt/)
- Icons from [Font Awesome](https://fontawesome.com/)
- Inspired by [VSCode](https://code.visualstudio.com/), [PyCharm](https://www.jetbrains.com/pycharm/), and [Sublime Text](https://www.sublimetext.com/)

## 🗺️ Roadmap

### Version 1.1 (Q2 2025)
- [ ] Integrated debugger
- [ ] Docker integration
- [ ] Remote development support
- [ ] Collaborative editing

### Version 1.2 (Q3 2025)
- [ ] Mobile app preview
- [ ] Cloud sync
- [ ] Extension marketplace
- [ ] AI code generation

### Version 2.0 (Q4 2025)
- [ ] Multi-language support
- [ ] Advanced refactoring tools
- [ ] Performance profiler
- [ ] Visual UI builder

## 📊 Statistics

- **Lines of Code**: ~15,000
- **Supported Languages**: 50+
- **Built-in Tools**: 12+
- **Plugins**: 10+ (built-in)
- **Themes**: 2 (Dark, Light)
- **Platforms**: Windows, macOS, Linux

---

**Made with ❤️ by the DevSuite Team**

[Website](https://devsuite.dev) | [Documentation](https://docs.devsuite.dev) | [GitHub](https://github.com/devsuite/devsuite) | [Twitter](https://twitter.com/devsuite)

