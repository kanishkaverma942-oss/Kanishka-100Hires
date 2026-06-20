# Kanishka – 100Hires Portfolio Task

Portfolio screening task assigned by Alex Kravets, CEO @ 100Hires.

---

## Tools Installed

| Tool | Version / Notes |
|------|----------------|
| **VS Code** | Used in place of Cursor IDE — same extension ecosystem, same workflow |
| **Claude Code** (VS Code extension) | AI coding assistant by Anthropic — logged in with Anthropic account |
| **Codex** (VS Code extension) | AI extension — logged in and configured inside VS Code |
| **GitHub CLI (`gh`)** | v2.89.0 — already installed on machine, used for auth and repo management |
| **Git** | v2.50.1 (Apple Git-155) |

---

## Steps Completed

1. **Received task brief** from Alex Kravets (CEO, 100Hires) via email — 48-hour deadline to complete and submit a GitHub README link.

2. **Chose VS Code over Cursor IDE** — already had VS Code installed and fully configured. Both share the same extension marketplace, so Claude Code and Codex extensions install identically in either editor.

3. **Installed Claude Code extension** in VS Code via the Extensions panel (search: "Claude Code") and logged in with my Anthropic account. This launched an interactive AI assistant directly inside the editor.

4. **Installed Codex extension** in VS Code via the Extensions panel (search: "Codex") and logged in.

5. **Created a public GitHub repository** named `Kanishka-100Hires` under `kanishkaverma942-oss`.

6. **Authenticated GitHub CLI** by running `gh auth login` — chose HTTPS protocol and browser-based login. Completed the one-time device authorization flow on GitHub.com.

7. **Cloned the repository** locally using `gh repo clone kanishkaverma942-oss/Kanishka-100Hires` and opened it in VS Code.

8. **Created this README.md** documenting the full process, with Claude Code assisting in drafting the content inside the editor.

9. **Committed and pushed** to the `main` branch on GitHub using:
   ```bash
   git add README.md
   git commit -m "Add portfolio README documenting setup process"
   git push origin main
   ```

---

## Issues Encountered & How I Solved Them

### 1. Git identity not configured
- **Problem:** `git config --global user.name` and `user.email` were not set — commits would fail or show blank authorship.
- **Fix:** Set both via:
  ```bash
  git config --global user.name "Kanishka Verma"
  git config --global user.email "kanishkaverma942@gmail.com"
  ```

### 2. SSH not set up for GitHub
- **Problem:** No `~/.ssh` directory existed. Running `ssh -T git@github.com` returned `Host key verification failed.`
- **Fix:** Switched to HTTPS instead of SSH for all git operations. Authenticated via `gh auth login` using the HTTPS protocol option, which handles credentials through the macOS keyring.

### 3. GitHub CLI not authenticated
- **Problem:** `gh` was installed but `gh auth status` showed "not logged into any GitHub hosts."
- **Fix:** Ran `gh auth login`, selected GitHub.com → HTTPS → browser login. Completed the device authorization flow and confirmed with `gh auth status`.

---

## Repository

**GitHub:** https://github.com/kanishkaverma942-oss/Kanishka-100Hires
