# Harry — Personal AI Assistant

### A Voice-Enabled, Multimodal AI Assistant with Desktop Automation, Persistent Memory and an Interactive Holographic Interface

Harry is a Python-based personal AI assistant designed to bring together conversational AI, real-time voice interaction, computer automation, visual awareness and persistent memory in a unified desktop application.

Built around a modular architecture, Harry integrates cloud-based and local language models with a PyQt6 graphical interface, extensible action modules and a plugin system. The project explores how AI models can interact with a user's digital environment through natural language while retaining user control over sensitive operations.

## Overview

Harry is designed to go beyond conventional text-based chatbots by combining AI-powered conversations with practical desktop capabilities.

The system includes:

* Real-time voice-based AI interaction
* Gemini Live integration and configurable local LLM support
* Animated holographic avatar with speech-driven lip synchronization
* Persistent memory and session continuity
* Desktop, browser and file automation
* Screen and webcam-based visual awareness
* Modular action discovery and plugin architecture
* Remote dashboard for interacting with the assistant
* Confirmation and undo mechanisms for selected operations

## Key Features

### 1. Conversational AI

* Real-time conversational interaction using the Gemini Live API.
* Configurable local language model support through Ollama and OpenAI-compatible endpoints.
* Context-aware responses and session continuity.
* Agent-based execution of multi-step tasks.
* Support for multilingual conversations.

### 2. Voice Interaction

* Real-time microphone input and audio responses.
* Push-to-talk interaction.
* Optional local wake-word detection.
* Speech-to-text and text-to-speech modules.
* Audio device selection and echo handling.
* Voice-driven execution of supported actions.

### 3. Interactive Holographic Avatar

* Animated human-like avatar integrated into the desktop HUD.
* Software-rendered facial geometry.
* Speech-driven lip synchronization.
* Animated facial expressions, blinking and gaze movement.
* Dynamic visual status feedback for listening, thinking and speaking.
* Customizable interface colors.

### 4. AI Memory System

* Persistent local memory across sessions.
* Memory organization for identity, preferences, projects, relationships and notes.
* On-demand memory retrieval.
* Session summaries and conversation continuity.
* Memory management interface with the ability to inspect and remove stored information.

### 5. Intelligent Desktop Automation

Harry provides a collection of modular tools for supported desktop operations, including:

* Application launching and window management.
* Browser navigation and web search.
* File processing and document assistance.
* System monitoring and selected computer settings.
* Clipboard assistance.
* Reminders and scheduled operations.
* YouTube playback and supported messaging workflows.
* Code assistance and development-related tasks.

### 6. Visual Awareness

* Screen capture and screen-content processing.
* Webcam input and visual analysis.
* Visual information supplied to the conversational AI.
* Contextual interaction using available visual input.

### 7. Agent and Plugin Architecture

* Automatically discovered action modules.
* Self-describing tool declarations.
* Modular plugin registration and dispatch.
* Plugin enable/disable controls.
* Support for adding new capabilities without embedding every action in the main application.
* Error handling for unavailable or failed plugins.

### 8. Safety and User Control

* Explicit confirmation for selected sensitive or irreversible operations.
* Undo support for selected file and system changes.
* Modular action execution.
* Configurable capabilities and plugin controls.

These controls apply to supported operations and should not be interpreted as a guarantee that every action is reversible or requires confirmation.

### 9. Remote Dashboard

* FastAPI-based dashboard.
* Browser-accessible interface on a local network.
* QR-based pairing workflow.
* Encrypted dashboard communication mechanisms.

Remote access should be configured only after reviewing authentication, transport security, network exposure and firewall permissions.

## System Architecture

```text
                  HARRY AI ASSISTANT
                           |
           +---------------+---------------+
           |               |               |
       PyQt6 UI         AI Engine       Audio Engine
           |               |               |
       Holographic     Gemini Live      Speech Input
         Avatar        Local LLM         Speech Output
           |               |               |
           +---------------+---------------+
                           |
                    Intent / Tool Routing
                           |
           +---------------+---------------+
           |               |               |
       Action Loader   Plugin Registry   Memory System
           |               |               |
       Desktop         Custom Tools     Persistent Store
       Browser         Extensions       Session Recall
       Files           Integrations     Memory Search
       Vision
           |
      User Confirmation
           |
      Supported Actions

       FastAPI Remote Dashboard
```

## Technology Stack

| Category             | Technologies                                     |
| -------------------- | ------------------------------------------------ |
| Programming Language | Python                                           |
| Desktop Interface    | PyQt6, Qt                                        |
| Generative AI        | Google Gemini Live API                           |
| Local AI             | Ollama, OpenAI-compatible LLM endpoints          |
| Computer Vision      | OpenCV, MSS, Pillow                              |
| Speech and Audio     | NumPy, SoundDevice, configurable STT/TTS engines |
| Backend              | FastAPI, Uvicorn                                 |
| Networking           | HTTP, WebSocket-based dashboard communication    |
| Automation           | PyAutoGUI, PyGetWindow, PyWin32, Pywinauto       |
| Data and Memory      | JSON, local persistent storage                   |
| Plugin System        | Python dynamic module discovery                  |
| Security             | Cryptography, confirmation workflows             |
| Development          | Git, Python virtual environments                 |

## Project Structure

```text
Harry/
├── actions/
│   ├── background_monitor.py
│   ├── browser_control.py
│   ├── code_helper.py
│   ├── computer_control.py
│   ├── computer_settings.py
│   ├── desktop.py
│   ├── dev_agent.py
│   ├── file_controller.py
│   ├── file_processor.py
│   ├── open_app.py
│   ├── proactive.py
│   ├── reminder.py
│   ├── screen_processor.py
│   ├── system_monitor.py
│   ├── web_search.py
│   └── ...
├── config/
├── core/
│   ├── action_loader.py
│   ├── avatar.py
│   ├── avatar_mesh.py
│   ├── confirm.py
│   ├── gemini.py
│   ├── installer.py
│   ├── llm_client.py
│   ├── plugin_loader.py
│   ├── stt.py
│   ├── tts.py
│   ├── undo.py
│   ├── viseme.py
│   └── wake_word.py
├── dashboard/
│   ├── server.py
│   └── static/
├── memory/
│   ├── config_manager.py
│   └── memory_manager.py
├── plugins/
│   ├── __init__.py
│   └── _template.py
├── main.py
├── ui.py
├── setup.py
├── requirements.txt
├── LICENSE
└── README.md
```

## Installation

### Prerequisites

* Python 3.11–3.13 (the versions targeted by the setup script)
* Git
* A microphone and speaker for voice interaction
* Internet access for cloud AI and initial dependency/model downloads
* An API key for the configured cloud AI provider, when using Gemini

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Create a virtual environment

**Windows (PowerShell)**

```powershell
py -3.12 -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux**

```bash
python3.12 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
python setup.py
```

The setup script installs the declared dependencies and configures the required Playwright browser components for the current platform.

### 4. Configure AI credentials

Open the application's settings and configure the required AI provider and credentials according to the project's configuration flow.

Keep API keys and other credentials outside source control. Do not commit personal configuration files or secrets to GitHub.

For local LLM usage, install and configure Ollama or another supported OpenAI-compatible server, and select a compatible model.

### 5. Launch Harry

```bash
python main.py
```

Follow the application interface to configure audio devices, AI connectivity, optional wake-word functionality and supported plugins.

## Configuration

Harry supports configuration of:

* AI provider and model
* Local LLM endpoint
* Audio input and output devices
* Assistant name, voice and interface colors
* Optional wake-word functionality
* Plugin settings and availability
* Memory management
* Dashboard and remote-access settings

Some capabilities require additional optional dependencies, external credentials or operating-system permissions.

## Security and Privacy

Harry can interact with the local desktop, process files, capture visual input and communicate with external AI services. These capabilities require careful configuration.

* Store credentials securely and exclude local secrets from version control.
* Review permissions before enabling automation and third-party plugins.
* Understand that data sent to a cloud AI provider is subject to that provider's processing and privacy policies.
* Enable remote access only on appropriately secured networks.
* Review confirmation requirements before performing sensitive operations.
* Keep local memory and uploaded files protected from unauthorized access.

## Current Scope

Harry is a personal AI assistant project with a working codebase and modular implementations for its documented capabilities. Actual feature availability depends on configuration, installed dependencies, hardware, operating system and external service access.

The repository should be tested on a clean installation before publishing a release or claiming production readiness.

## Future Development

Potential areas for further development include:

* More extensive automated testing and continuous integration.
* Advanced hand-gesture-based desktop interaction.
* Improved multimodal intent routing.
* More granular permissions and plugin sandboxing.
* Expanded offline voice and vision capabilities.
* More robust cross-platform packaging.
* Detailed API documentation and reproducible deployment.

## Skills Demonstrated

This project brings together several practical software engineering and AI domains:

* Python application development
* Generative AI and LLM integration
* Real-time audio processing
* Desktop GUI development
* Computer vision and visual input processing
* Desktop automation
* Agent and tool orchestration
* Persistent memory design
* API and dashboard development
* Modular architecture and plugin systems
* User confirmation and action safety design

## License

See the repository's `LICENSE` file for licensing terms. Retain any required original project attribution and third-party notices when distributing modified code.

## Author

**Shivam (Shiv)**

AI Development | Python | Generative AI | Automation | Computer Vision



---

*Harry is an evolving personal AI assistant project exploring the integration of conversational intelligence, multimodal interaction, memory and desktop automation into a single application.*
