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

---

## Step 2 — Research Project: Cold Outreach Pipeline for B2B SaaS

### Topic & Why It Was Chosen

**Topic**: Cold Outreach Pipeline for B2B SaaS

Cold outreach was chosen because it's the core growth engine for B2B SaaS companies — and directly relevant to 100Hires' own business model. Understanding what works in cold outreach (for both email and LinkedIn) applies immediately to the kind of outbound hiring and sales motions 100Hires runs. Choosing a topic the company lives every day demonstrates contextual awareness, not just research ability.

---

### Experts Researched (10 Total)

#### Group A — YouTube Experts (transcripts collected)

| # | Name | Channel | Why Selected |
|---|------|---------|-------------|
| 1 | Alex Hormozi | [@AlexHormozi](https://www.youtube.com/@AlexHormozi) | $100M+ in sales; cold outreach frameworks used by thousands of B2B companies |
| 2 | Patrick Dang | [@patrickdang](https://www.youtube.com/@patrickdang) | 300K+ subscribers; ex-Oracle SDR; most-watched cold outreach channel |
| 3 | Alex Berman | [@AlexBerman](https://www.youtube.com/@AlexBerman) | Founder of $10M/yr agency built entirely on cold email |
| 4 | 30 Min to President's Club | [@30MPC](https://www.youtube.com/@30MPC) | #1 sales podcast; 60K+ newsletter subscribers; tactical cold call/email breakdowns |
| 5 | Alex Vacca (ColdIQ) | [@AlexVacca](https://www.youtube.com/@AlexVacca) | $7M ARR cold outreach agency; publishes exact sequences and toolstacks used for clients |

#### Group B — LinkedIn Experts (posts collected)

| # | Name | LinkedIn | Why Selected |
|---|------|---------|-------------|
| 6 | Josh Braun | [josh-braun](https://www.linkedin.com/in/josh-braun) | Author of *Outbound*; psychology-driven cold messaging frameworks |
| 7 | Jason Bay | [jasondbay](https://www.linkedin.com/in/jasondbay) | Founder of Blissful Prospecting; daily LinkedIn poster; REPLY method creator |
| 8 | Belal Batrawy | [belbatrawy](https://www.linkedin.com/in/belbatrawy) | Founder of Death to Fluff; viral anti-manipulation cold outreach posts |
| 9 | Justin Michael | [michaeljustin](https://www.linkedin.com/in/michaeljustin) | Author of *Tech-Powered Sales*; 20+ years at Salesforce/LinkedIn |
| 10 | Jack Reamer | [jackreamer](https://www.linkedin.com/in/jackreamer) | CEO SalesBread; publishes reply-rate data from 1M+ analyzed emails |

---

### How Content Was Collected

**YouTube transcripts**:
- Tool: `youtube-transcript-api` Python library (`pip install youtube-transcript-api`)
- Method: `YouTubeTranscriptApi().fetch(video_id)` → joined transcript segments into full text
- 5 videos per expert → 25 transcript files total
- Files saved as `research/youtube-transcripts/[author]/[video-slug].md`

**LinkedIn posts**:
- Tool: `WebFetch` on public LinkedIn profile activity pages and individual post URLs
- Supplemented with Google search to surface high-engagement posts where profile pages were blocked
- ColdIQ official guide fetched from `coldiq.com/cold-email-guide` via WebFetch
- SalesBread content fetched from `salesbread.com` (Jack Reamer's primary publishing platform)
- Files saved as `research/linkedin-posts/[name].md`

---

### Repo Structure

```
research/
  sources.md                          ← all 10 experts annotated with why they were selected
  youtube-transcripts/
    alex-hormozi/                     ← 5 transcript files
    patrick-dang/                     ← 5 transcript files
    alex-berman/                      ← 5 transcript files
    30mpc/                            ← 5 transcript files
    alex-vacca/                       ← 5 files (4 transcripts + official ColdIQ guide)
  linkedin-posts/
    josh-braun.md
    jason-bay.md
    belal-batrawy.md
    justin-michael.md
    jack-reamer.md
  other/                              ← reserved for future additions
README.md
```

---

### Commit History

Each expert's content was committed individually (not in one giant push) to show incremental progress:

1. `scaffold: research folder structure and sources`
2. `research: add Alex Hormozi transcripts (5 cold outreach videos)`
3. `research: add Patrick Dang transcripts (5 cold outreach videos)`
4. `research: add Alex Berman transcripts (5 cold email videos)`
5. `research: add 30 Minutes to President's Club transcripts (5 videos)`
6. `research: add Alex Vacca / ColdIQ transcripts (4 videos + official guide)`
7. `research: add Josh Braun linkedin posts (cold outreach psychology)`
8. `research: add Jason Bay linkedin posts (REPLY method, mobile email)`
9. `research: add Belal Batrawy linkedin posts (Death to Fluff methodology)`
10. `research: add Justin Michael linkedin posts (JMM tech-powered outbound)`
11. `research: add Jack Reamer linkedin posts (CCQ method, Fibonacci cadence)`
12. `docs: update README with Step 2 research`
