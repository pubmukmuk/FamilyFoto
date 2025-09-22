# 🧭 CLI Overview – `cli.py`

The `cli.py` file serves as the **main entrypoint for the entire FamilyFoto CLI suite**. It defines a unified command-line interface to run all tools and agents, and routes each command to the appropriate logic module.

## ✅ Primary Responsibilities

| Responsibility                  | Description                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| 🔧 CLI Parser Setup              | Creates the main `argparse.ArgumentParser` instance                        |
| 🧩 Subcommand Registration       | Calls `register()` from each `commands/*.py` module to hook into the CLI   |
| ⚙️ Config Support                | Adds global `--config` option (applies to all commands)                    |
| 🔌 DB Connection Lifecycle       | Registers `atexit` hook to close DB connection on shutdown                 |
| 🗂 CLI Dispatching               | After parsing, calls `args.func(args)` (each command sets this)           |
| 📝 Logging                       | Initializes logging system using `get_standard_logger()`                   |
| ❓ Help & Fallback Handling      | If no command is given, prints full help summary                           |

## 🔁 Lifecycle Flow

```
Start CLI
   ↓
Parse arguments (--config + command + options)
   ↓
Register all subcommands via register(subparsers, parent_parser)
   ↓
If no command: print_help()
   ↓
Else:
    → Load config
    → Set up logger
    → Call args.func(args)
```

## 🔌 Supported Modules

As of `v1.1.1`, `cli.py` supports:

### 📷 Tool Commands
- `fotonamer`, `fotomover`, `fotocontact`
- `fotofinder`, `fotomenu`, `summarize`

### 🤖 Agent Commands
- `batch_agent`
- `watcher_agent`
- `geo_agent`
- `name_agent`
- `summary_agent`

Each is implemented in `familyfoto.commands.*` and exposes:
```python
def register(subparsers, parent_parser)
def run(args)
```
