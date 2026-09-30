⚡ Webcraft based on bolt
An AI-powered, full-stack web development environment in the browser. This application allows users to prompt, build, execute, and deploy complete web applications directly in the browser using WebContainers and LLM orchestration.

🌟 Key Features
Full-Stack In-Browser Execution: Powered by Node.js running directly inside browser memory via WebContainers.

Natural Language to App: Describe what you want to build, and the AI streams, scaffolds, and edits code in real time.

Live Preview & Hot Reload: Instantly preview React, Vue, Svelte, or Next.js applications alongside your code.

Terminal & Dependency Management: Run shell commands, install npm packages, and execute scripts without local environment setup.

Interactive Code Editor: Multi-file code editor with syntax highlighting, auto-completion, and file tree management.

One-Click Deployment: Directly export or deploy your projects to cloud providers like Netlify or Vercel.

🛠️ Tech Stack
Frontend & UI
Framework: Next.js / React / Remix

Styling: Tailwind CSS + Shadcn UI

Code Editor: Monaco Editor / CodeMirror

Icons: Lucide React

Core Engine & In-Browser Runtime
Container Engine: @webcontainer/api (StackBlitz WebContainers)

Terminal: Xterm.js

AI & Backend Services
LLM Provider: Anthropic Claude 3.5 Sonnet / OpenAI GPT-4o

AI SDK: Vercel AI SDK

Database / Auth (optional): Supabase / Firebase

🏗️ Architecture Overview
┌─────────────────────────────────────────────────────────┐
│                    User Interface                       │
│  ┌─────────────────┬──────────────────┬──────────────┐  │
│  │   Chat Input    │   Code Editor    │ Live Preview │  │
│  └────────┬────────┴────────┬─────────┴──────┬───────┘  │
└───────────┼─────────────────┼────────────────┼──────────┘
            │                 │                │
            ▼                 ▼                ▼
┌──────────────────┐  ┌──────────────────────────────┐
│  LLM Orchestrator│  │      WebContainer Engine     │
│   (Vercel AI)    │  │  ┌────────────────────────┐  │
│   - System Prompt│──┼─►│ In-Memory File System  │  │
│   - Artifact parser │  │ ├────────────────────────┤  │
│                  │  │ │ Node.js Process / xterm│  │
└──────────────────┘  │ └────────────────────────┘  │
                      └──────────────────────────────┘
User Prompt: The user submits a natural language request.

AI Stream: The backend streams structured code blocks (artifacts/actions) to the client.

WebContainer Sync: Actions (creating files, executing terminal commands like npm install) are parsed and executed inside the WebContainer in real time.

Live Preview: WebContainer starts a dev server and exposes a internal URL embedded directly into an iframe preview.

🚀 Getting Started
Prerequisites
Ensure you have the following installed locally:

Node.js: v18.x or higher

Package Manager: npm, pnpm, or yarn

API Key: An Anthropic or OpenAI API key

⚠️ Note on Cross-Origin Isolation: WebContainers require specific headers (Cross-Origin-Embedder-Policy and Cross-Origin-Opener-Policy) to function properly.

Installation
Clone the repository:

Bash
git clone https://github.com/your-username/bolt-new-clone.git
cd bolt-new-clone
Install dependencies:

Bash
npm install
# or
pnpm install
Set up environment variables:
Create a .env.local file in the root directory and add your credentials:

Code snippet
ANTHROPIC_API_KEY=your_anthropic_api_key_here
# or
OPENAI_API_KEY=your_openai_api_key_here
Run the development server:

Bash
npm run dev
Open http://localhost:3000 with your browser to see the result.

🧪 Usage
Start a Prompt: Type your project requirements into the prompt box (e.g., "Create a real-time Kanban board with drag-and-drop support using React and Tailwind").

Watch the Generation: The system stream-scaffolds files and executes the initial package installation in the background.

Iterate & Refine: Use the side-by-side prompt chat to tweak existing components, fix errors, or add features.

Edit Code: Open any file in the built-in editor to make manual code adjustments.

Export: Download the project as a .zip file or push directly to GitHub.
