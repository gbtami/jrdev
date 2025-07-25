# JrDev - Built for developers who code.
![code-fast](https://github.com/user-attachments/assets/5efa7671-c2bd-4343-8338-bb2d482cb02f)

## Key Features

*   **Project Chat** - Persistent conversations with file context.
*   **Smart Project Indexing** - Scans codebase, infers conventions, creates a powerful overview of project and key files (`/init`)
*   **AI Code Generation** - Efficient and structured code agent uses multiple AI models to save on cost and produce better results (`/code`)
*   **Smart Controls** - Only let JrDev make the changes you want. Review code diffs, edit them directly, or reprompt for changes.
*   **Git Integration** - Speed up development with PR summaries, code reviews, and commit messages
*   **Model Flexibility** - Easily add new models on the fly
*   **File Context Control** - Let the agent figure out what files are needed for tasks, or add them to context manually
*   **Real-time Monitoring** - Streaming view of tokens, costs, and ability to cancel anytime

## Installation

Install JrDev directly from the Python Package Index (PyPI):
```bash
pip install jrdev
```

For developers or to get the very latest updates, you can install from the GitHub repository:
```bash
# Install from a cloned repository in editable mode
git clone https://github.com/presstab/jrdev
cd jrdev
pip install -e .

# Alternatively
pip install git+https://github.com/presstab/jrdev.git
```

# Code Generation

JrDev works with the context in your current working directory. Navigate to your project and type `jrdev`.

## 1. Initialize Project:

If this is the first time running JrDev for this project, you will need to run the initialization process to give JrDev a powerful overview of your project.

```
> /init
```

## 2. Launch Code Agent

For the most precise results it is recommended to use the `/code` command directly:
```
> /code update the "Save" button in the Settings Dialog to change to disabled if there are no changes to save
```

Or try out the JrDev intent agent which will process attempt to understand your natural language and launch the code agent task.
```
> update the "Save" button in the Settings Dialog to change to disabled if there are no changes to save
```

### What About Context?

JrDev collected some essential context about the project during the `/init` phase. This is passed on to the coding agent. The coding agent goes through up to 3 rounds of searching to find the right files and context to include.

To manually add your own context to a coding task, use the 'Project Files' window and click '+ Code Ctx' on a file or directory to add it to the code context for the next code task. When a code task is launched, it clears any staged code context.

For a detailed overview of the coding agent, see the [code documentation](docs/code.md).

For a detailed overview of the project context system, see the [project context documentation](docs/project_context.md).

## 3. (optional) Configure Smart Model Switching Profiles

JrDev uses different AI models for different tasks to balance performance and cost. It reserves powerful, expensive models for complex work while using faster, cheaper models for routine tasks.

*   **`advanced_reasoning`**: Uses a top-tier model for critical planning and review to ensure the highest quality output. (Try Sonnet, Opus, Gemini 2.5 Pro, DeepSeek R1)
*   **`advanced_coding`**: Employs a powerful, specialized model for generating accurate and high-quality code. (Try Sonnet, Opus, Gemini 2.5 Pro, DeepSeek R1/V3, GPT 4.1)
*   **`intermediate_reasoning`**: A cost-effective model for routine tasks like validating code syntax and summarizing files. (Try Gemini 2.5 Flash, Devstral, DeepSeek V3)
*   **`quick_reasoning`**: A fast, low-cost model for simple corrective actions, like fixing a malformed response. (Try Gemini 2.5 Flash, Devstral, DeepSeek V3)
*   **`intent_router`**: A highly efficient model that interprets natural language commands to quickly route them to the correct tool. (Try Gemini 2.5 Flash, DeepSeek V3, o4-mini, GPT 4.1)
*   **`low_cost_search`**: An inexpensive model for broad searches, like finding additional context files, to minimize costs. (Try Gemini 2.5 Flash, Devstral, DeepSeek V3)

These profiles are initialized to default values based on the API key you added. To customize them, hit the "Profiles" button, or use natural language in the terminal input field and instruct JrDev what to change.

## 🚨Early Access Software🚨

JrDev is in early development and may undergo rapid changes, including breaking changes and experimental features. This tool can modify your project files, and will prompt for confirmation unless placed in "Accept All" mode. **It is strongly recommended to use version control (e.g., Git) and commit your work before using JrDev.**

### Development Commands

```bash
# Run linting (example)
pylint src/

# Run type checking (example)
mypy src/

# Format code (example)
black src/

# Sort imports (example)
isort src/ tests/
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
