## Prerequisites

- [Ollama](https://ollama.com) (runs the local LLM that narrates predictions)
- [uv](https://docs.astral.sh/uv/) (Python package and project manager)

## Installing Ollama

**macOS / Linux**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

**Windows**

Download and run the installer from [ollama.com/download](https://ollama.com/download).

## Starting Ollama

After installation, start the Ollama server in a terminal:

```bash
ollama serve
```

Then pull the model used by the notebook (one-time download, ~4 GB):

```bash
ollama pull llama3.1
```

You can verify it's ready:

```bash
ollama list
```

You should see `llama3.1` in the output.

## Python Setup

Install uv if you don't have it:

```bash
# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

The installer adds `uv` to your PATH, but your current terminal won't pick that up automatically.  Close and reopen your terminal (on macOS/Linux you can instead run `source ~/.bashrc` or `source ~/.zshrc`) before continuing, otherwise `uv` will come back as "command not found".

Then create the environment and install dependencies:

```bash
uv sync
```