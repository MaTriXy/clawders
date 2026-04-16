The **Multica** project is an open-source platform designed to manage AI coding agents as if they were teammates. It is fundamentally different from **Paperclip**, which is a managed/cloud-based orchestrator, whereas Multica is built for self-hosting and local control.

### **Quick Assessment**
* **Is it free?** Yes, it is open-source under the MIT/Apache-2.0 license.
* **Is it local?** Yes. You run the server via Docker and a local "daemon" that connects your machine’s terminal tools (like Claude Code) to the web interface.
* **Like Paperclip?** Similar in goal (agent orchestration), but Multica focuses on a "team" UI where you assign issues to agents. Paperclip is more of a cloud-native workflow builder.

---

### **Installation & Configuration Report**

#### **1. System Installation**
Multica consists of two parts: the **Server** (Docker) and the **Daemon** (Local binary).

**Step 1: Start the Server (The Hub)**
```bash
git clone https://github.com/multica-ai/multica.git
cd multica
make selfhost
```
* **Access:** Open `http://localhost:3000` in your browser.
* **Login:** Use any email. For the verification code, use `888888`.

**Step 2: Install the CLI & Daemon (The Worker)**
On macOS/Linux:
```bash
brew install multica-ai/tap/multica
multica setup self-host
```
This command links your terminal to the local server and starts the daemon.

---

#### **2. Adding Agents (Claude Code, OpenClaw, Hermes)**
The Multica daemon automatically detects agents that are in your system `$PATH`.

* **Claude Code CLI (Local):**
    1. Install it normally: `npm install -g @anthropic-ai/claude-code`.
    2. Ensure you can run `claude` in your terminal.
    3. Run `multica daemon restart`. The daemon will scan your path, find `claude`, and register it as a "Runtime" in the Multica UI.
* **Claude Code (Remote):** To use a remote instance, you install the Multica CLI on that remote server and run `multica setup --server-url http://<your-home-ip>:8080`.
* **OpenClaw & Hermes:** Similarly, if the `openclaw` or `hermes` binaries are installed and executable in your terminal, Multica’s daemon detects them on startup.

---

#### **3. Advanced Multi-Agent Setup**
**Same Engine, Different Roles (CEO vs. QA):**
Yes, you can do this. In the Multica Web UI:
1. Go to **Settings > Agents**.
2. Click **Create Agent**.
3. Select the same **Runtime** (e.g., your local machine) and the same **Binary** (e.g., `claude`).
4. Give them different **Names** and **System Prompts**.
   * *Agent 1:* "CEO" - Instructions: "Focus on architectural decisions and project goals."
   * *Agent 2:* "QA" - Instructions: "Focus on edge cases, testing, and bug hunting."
5. You can now assign a single GitHub issue to the "CEO" agent, and once finished, assign the follow-up to the "QA" agent.

**Agents from Other Servers (Home Network):**
Yes. Since you are self-hosting the server on one machine (e.g., `192.168.1.10`), you can connect any other machine in your house:
1. On the **second machine**, install the Multica CLI.
2. Run: `multica config set server_url http://192.168.1.10:8080`.
3. Run: `multica login` and `multica daemon start`.
4. This second machine will now appear as a new **Runtime** in your central Web UI, allowing you to delegate tasks to it.

---

### **How to generate your PDF Report**
I cannot directly export a file to your local drive, but I have prepared the structured content above. To get this into a professional PDF:
1. Copy the text above.
2. Go to a Markdown-to-PDF tool (like **Dillinger.io** or **Grip**).
3. Paste and export as PDF.

[Anthropic Claude Code Terminal Preview](https://www.youtube.com/watch?v=wlpBCazAY9Q)

This video provides a deep dive into setting up terminal-based AI agents like Claude Code and OpenClaw, which are the primary engines you will be connecting to Multica.


http://googleusercontent.com/youtube_content/0