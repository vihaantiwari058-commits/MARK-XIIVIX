JARVIS

### An intelligent desktop command center for voice, vision, and real-world automation.

> **JARVIS is a Windows-first personal AI assistant that turns natural language into useful computer actions.** It listens, reasons, observes the screen, remembers context, and coordinates tools—from launching an application to analysing a document or building a small software project.

![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Gemini](https://img.shields.io/badge/Google_Gemini-Live_AI-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows--first-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Interface](https://img.shields.io/badge/Interface-PyQt6-41CD52?style=for-the-badge&logo=qt&logoColor=white)

---

## Why JARVIS?

Most assistants stop at an answer. JARVIS is designed to continue into execution.

It combines a cinematic command-center interface with a practical tool layer: live voice interaction, screen understanding, browser operations, desktop control, file intelligence, persistent memory, and coding assistance. The goal is simple—make interaction with a computer feel less like operating software and more like delegating intent.

```text
Voice / Text / Files / Screen
             │
             ▼
      Gemini Live reasoning
             │
             ▼
  JARVIS tool orchestration layer
             │
             ▼
Desktop • Browser • Files • Search • Messages • Development
```

## Core capabilities

| Domain | What JARVIS can do |
|---|---|
| **Natural interaction** | Hold real-time voice conversations or accept typed commands through a futuristic desktop interface. |
| **Computer control** | Open applications, control desktop interactions, manage windows, take screenshots, and perform guided UI actions. |
| **Visual intelligence** | Inspect the active screen or webcam feed to explain what it sees, help troubleshoot, or answer visual questions. |
| **File intelligence** | Analyse, summarise, extract, convert, validate, or organise documents, images, PDFs, spreadsheets, code, media, and archives. |
| **Web intelligence** | Search the web, compare options, find flights, retrieve weather, and work with YouTube videos and transcripts. |
| **Personal productivity** | Create reminders, launch applications, organise files, and send messages through supported desktop messaging workflows. |
| **Developer mode** | Generate, explain, edit, run, debug, optimise, and iteratively build code projects from a plain-English request. |
| **Contextual memory** | Preserve useful preferences and project context so interactions can become more personalised over time. |

## Architecture

JARVIS is deliberately modular. The application core focuses on a live AI session and tool dispatch; each capability lives in an independent action module.

| Layer | Responsibility |
|---|---|
| `main.py` | Live voice session, model communication, function calling, and action orchestration. |
| `ui.py` | PyQt6 command-center interface, file drop support, visual feedback, and system metrics. |
| `actions/` | Focused capabilities for desktop control, search, files, browser tasks, media, messaging, development, and more. |
| `memory/` | Long-term preference and context management. |
| `agent/` | Planning, task queueing, execution, and error-handling foundations. |
| `core/prompt.txt` | The assistant’s behavioural and operational instructions. |
| `config/api_keys.json` | Local runtime configuration for API access and operating-system preference. |

## Quick start

### 1. Clone and enter the project

```bash
git clone <your-repository-url>
cd JARVIS
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv .venv
.venv\Scripts\activate
```

On macOS or Linux, activate it with `source .venv/bin/activate`.

### 3. Install dependencies

```bash
pip install -r requirements.txt
pip install PyQt6
playwright install
```

### 4. Configure your local keys

Create or update `config/api_keys.json` locally:

```json
{
  "gemini_api_key": "YOUR_GEMINI_API_KEY",
  "openrouter_api_key": "YOUR_OPENROUTER_API_KEY",
  "os_system": "windows"
}
```

Get a Gemini key from [Google AI Studio](https://aistudio.google.com/). OpenRouter is used by selected modules; a Gemini key is required for the live assistant.

> **Security note:** Never publish real API keys. Keep `config/api_keys.json` private and add it to `.gitignore` before pushing this project to a public repository.

### 5. Launch

```bash
python main.py
```

### Downloadable Windows app

To create a standalone Windows app, install PyInstaller and run the packaging script:

```powershell
python -m pip install PyInstaller
.\build_windows.ps1
```

This creates `JARVIS-App.exe` on your Desktop plus a `JARVIS` shortcut. You do not need to
extract an archive or open PowerShell. On first launch, enter your Gemini API key; an
OpenRouter API key is optional. The app intentionally does not contain API keys. Allow
microphone access in Windows and leave **MICROPHONE ACTIVE** enabled to talk to JARVIS.
An internet connection is required for the live AI conversation. Windows may display its
unknown-publisher warning because this local app build is not code-signed.

## Example commands

```text
“Open Visual Studio Code and create a Python project for a weather dashboard.”
“Look at my screen and explain this error.”
“Summarise this PDF in five bullet points.”
“Find the best flight options from Delhi to Moscow next month.”
“Organise the files on my desktop by type.”
“Search for recent research on computer vision and compare three sources.”
“Set a reminder for tomorrow at 09:00: submit the project proposal.”
```

## Technology stack

- **AI and voice:** Google Gemini Live API and Gemini Flash
- **Desktop interface:** PyQt6
- **Automation:** PyAutoGUI, PyGetWindow, PyWinAuto, Playwright
- **Vision and capture:** OpenCV, Pillow, MSS, NumPy
- **System layer:** PSUtil, PyCAW, COM interfaces, Windows Task Scheduler
- **Information and media:** Requests, Beautiful Soup, DuckDuckGo Search, YouTube Transcript API
- **Language:** Python

## Important notes

- JARVIS can perform actions on the computer. Review commands involving messages, files, settings, terminals, or browser activity before approving or running them.
- Several modules include Windows-specific integrations, such as Windows Task Scheduler, notification support, game launcher discovery, and desktop automation. Cross-platform support exists in selected modules, but **Windows is the primary tested target**.
- A microphone is required for live voice interaction. Typed interaction remains available through the interface.
- Internet access and valid API credentials are required for AI-powered and web-backed features.

## Project vision

JARVIS is an exploration of **human–computer interaction beyond menus and clicks**. Rather than building another chatbot, this project investigates an agent that can understand multimodal input, reason about a task, and act through the tools people already use every day.

It is a practical prototype of a more natural computing experience: one where the interface adapts to human intent—not the other way around.

---

### Built to make the computer feel like a collaborator.

If this project inspires you, consider starring the repository and sharing your ideas for the next generation of JARVIS.
