# AAE KINGDOM MAINTENANCE
### *Sovereign Life‑Admin Registry*  
Cold. Methodical. Repeatable. Permanent.

---

## 1. TOKEN DIRECTORY
| Token Name | Storage Location | Expiry Cycle | Systems Using It | Refresh Protocol | Last Updated | Notes |
|------------|------------------|--------------|------------------|------------------|--------------|-------|
| **Threads Long‑Lived Token** | Google Sheets → `Config!B9` | 30 Days | Google Apps Script Threads Poster | Protocol 1 | 01/05/2026 | — |
| **Threads Long‑Lived Token — `THREADS_ACCESS_TOKEN`** | GitHub Repo → `FMMedia-TextOutput_Engine` | 30 Days | GitHub Actions Threads Poster | Protocol 1 | 01/05/2026 | Mirrors Sheets token; required for GH Actions |
| **Google Service Account Key — `CONTENT_REPO_PAT`** | GitHub Repo → `FMMedia-VisualOutput_Engine` | Rare | Sheets → GitHub pipelines | Protocol 2 | 12/02/2026 | Used to pull GSheets content into basic reel format |
| **GHHarvestScanner-PAT** | Main GitHub Account → PAT | No Expiry | GitHub Public Repo Harvest | Protocol 3 | 14/04/2026 | Experimental token for harvesting public repos |
| **Instagram Publishing Token** | Google Apps Script | Not Used | IG Reels pipeline | Protocol Unknown | — | Will need re‑establishing when IG pipeline is revived |
| **YouTube OAuth Token** | GitHub Secret | Variable | YouTube Shorts pipeline | Protocol Unknown | — | Currently non‑existent |

---

## 2. GITHUB ACTIONS TRACKER
A central log of all automated workflows across the empire.  
Tracks purpose, triggers, dependencies, and operational status.

| Workflow Name | Repo | File Path | Trigger | Purpose | Tokens Required | Frequency | Last Run / Setup | Status |
|---------------|------|-----------|---------|---------|-----------------|-----------|------------------|--------|
| **Module 001 — Post to Threads (Every 4 Hours)** | FMMedia-TextOutput_Engine | `.github/workflows/module_001_post.yml` | Schedule | Posts content from repo to Threads via API | Threads Token | Every 4 Hours | 03/05/2025 | Passing |
| **Post to Threads (Every 4 Hours)** | FMMedia-TextOutput_Engine | `.github/workflows/post_to_threads.yml` | Schedule | Posts content from repo to Threads via API | Threads Token | Every 4 Hours | 03/05/2025 | Passing |
| **Post to Threads (Reservoir Mode)** | FMMedia-TextOutput_Engine | `.github/workflows/post_to_threads_engine.yml` | Schedule | Reservoir‑based posting engine | Threads Token | Every Hour | 03/05/2025 | Passing |
| **Render Video** | FMMedia-VisualOutput_Engine | `.github/workflows/render_video.yml` | Schedule / Manual | Generates reels using GSheets content | Google Sheets SA Key | Variable | 03/05/2025 | Passing |
| **GHHarvestScanner** | GHHarvestScanner | `.github/workflows/harvest.yml` | Manual | Scans repos + forks targets | PAT | Manual | 13/04/2025 | Passing |

---

### ACTIONS HEALTH NOTES
- Any workflow marked **Failing** must be reviewed within 48 hours.  
- Any workflow requiring a token must be re‑tested after token refresh.  
- All workflows should have a **manual trigger** for dry‑run testing.  
- If a workflow is unused for > 60 days, evaluate for decommissioning.

---

### ACTIONS AUDIT CHECKLIST
- [ ] All workflows have clear triggers  
- [ ] All workflows have documented token dependencies  
- [ ] All workflows have manual dispatch enabled  
- [ ] All workflows have a passing dry‑run in the last 30 days  
- [ ] All workflows are still relevant to current architecture  


---

## 3. API PLATFORM HUB
A central index of all external platforms used across the kingdom.  
Tracks API sources, purpose, and where credentials are stored.

| Platform | Purpose | API Type | Where Used | Credential Location | Notes |
|----------|---------|----------|------------|---------------------|-------|
| **Meta / Threads API** | Posting text content to Threads | Long‑Lived User Token | GSheets: FM Media Enterprises Vault, GH: FMMedia-TextOutput_Engine | Google Sheets (`Config!B9`), GitHub Secret (`THREADS_ACCESS_TOKEN`) | Requires monthly refresh |
| **Google Cloud / Google Sheets API** | Pulling content for reels | Google Service Account Key | FMMedia-VisualOutput_Engine | GitHub Secret (`CONTENT_REPO_PAT`) | Rare refresh |
| **GitHub API** | Repo harvesting, automation | PAT | GHHarvestScanner | GitHub PAT | Used for public repo scanning |
| **Instagram Publishing API** | IG Reels publishing (future) | IG Publishing Token | VisualOutput Engine (future) | Apps Script / GitHub Secret | Currently inactive |
| **YouTube Data API** | Shorts publishing (future) | OAuth Token | VisualOutput Engine (future) | GitHub Secret | Not yet established |

---

## 3.5 API ACCESS INSTRUCTIONS INDEX
Detailed instructions for generating and refreshing API keys.  
Each platform has its own dedicated `.md` file inside `/api_instructions/`.

| Platform | Instruction File | Contents |
|----------|------------------|----------|
| **Meta / Threads API** | `/api_instructions/threads_token_api.md` | How to generate long‑lived token, refresh steps, scopes |
| **Google Sheets API** | `/api_instructions/google_sheets_api.md` | How to create service account, generate JSON key, assign permissions |
| **GitHub API (PAT)** | `/api_instructions/github_pat.md` | How to create PAT, scopes needed, where to store it |
| **Instagram Publishing API** | `/api_instructions/instagram_api.md` | How to re‑establish IG publishing token (future) |
| **YouTube OAuth Token** | `/api_instructions/youtube_oauth.md` | OAuth flow, token storage, refresh logic (future) |

---

## 4. REFRESH PROTOCOLS
Step‑by‑step operational procedures for refreshing each token.  
These are short, repeatable, and designed for quick execution.

---

### Protocol 1 — Threads Long‑Lived Token
1. Open Meta Developer Tools  
2. Generate a new long‑lived user token  
3. Replace token in Google Sheets → `Config!B9`  
4. Replace GitHub Secret → `THREADS_ACCESS_TOKEN`  
5. Trigger manual dry‑run of all Threads workflows  
6. Update “Last Updated” in Token Directory  

---

### Protocol 2 — Google Service Account Key (Google Sheets API)
1. Open Google Cloud Console  
2. Navigate to IAM → Service Accounts  
3. Select the service account used for Sheets access  
4. Create a new JSON key  
5. Replace GitHub Secret → `CONTENT_REPO_PAT`  
6. Trigger manual dry‑run of the VisualOutput Engine  
7. Update “Last Updated” in Token Directory  

---

### Protocol 3 — GHHarvestScanner PAT
1. Go to GitHub → Settings → Developer Settings → PATs  
2. Generate a new PAT with `public_repo` read permissions  
3. Replace PAT in GHHarvestScanner repo secrets  
4. Run manual harvest scan to confirm validity  
5. Update “Last Updated” in Token Directory  

---

### Protocol Unknown — Instagram Publishing Token (Future)
1. Re‑establish IG Publishing App  
2. Generate new IG Publishing Token  
3. Store token in Apps Script or GitHub Secret  
4. Trigger IG pipeline dry‑run  
5. Update “Last Updated” in Token Directory  

---

### Protocol Unknown — YouTube OAuth Token (Future)
1. Run OAuth flow to generate new token  
2. Replace GitHub Secret  
3. Trigger YouTube Shorts pipeline dry‑run  
4. Update “Last Updated” in Token Directory  

---

## 5. PIPELINE MAP
A high‑level map of all automated pipelines across the kingdom.  
Shows inputs, processing engines, outputs, required tokens, and repo locations.

| Pipeline | Inputs | Processing Engine | Outputs | Tokens Required | Repo |
|----------|--------|-------------------|---------|-----------------|------|
| **Threads Text Engine** | GitHub Repo Content | Threads Posting Workflows | Threads Posts | Threads Token | FMMedia-TextOutput_Engine |
| **Threads Reservoir Engine** | Reservoir Folder (TextOutput Engine) | Reservoir Posting Workflow | Threads Posts | Threads Token | FMMedia-TextOutput_Engine |
| **Reels Visual Engine** | Google Sheets Content | Render Video Workflow | IG / YouTube Reels | Google Sheets SA Key | FMMedia-VisualOutput_Engine |
| **GH Harvest Scanner** | Public GitHub Repos | Harvest Workflow | Harvested Repo Data | PAT | GHHarvestScanner |
| **FM Media Vault (Manual)** | FM Media Enterprises Content | Manual Curation | Multi‑platform Content | None | FM-MediaEnterprises |

---
## 6. WORKFLOW DEPENDENCY GRAPH
A vertical lineage map showing how tokens, secrets, workflows, and outputs interconnect.  
This reveals upstream → downstream dependencies across the entire automation ecosystem.

──────────────────────────────────────────────────────────────────────────────
                           THREADS POSTING SYSTEM
──────────────────────────────────────────────────────────────────────────────

                 ┌────────────────────────────────────────┐
                 │      Threads Long‑Lived Token          │
                 │  (Google Sheets → Config!B9)           │
                 └───────────────────────┬────────────────┘
                                         │
                                         ▼
                 ┌────────────────────────────────────────┐
                 │ GitHub Secret: THREADS_ACCESS_TOKEN    │
                 │ (Mirrors Sheets token)                 │
                 └───────────────────────┬────────────────┘
                                         │
                                         ▼
        ┌──────────────────────────────────────────────────────────────────┐
        │ FMMedia-TextOutput_Engine Workflows                              │
        │  • module_001_post.yml                                           │
        │  • post_to_threads.yml                                           │
        │  • post_to_threads_engine.yml (Reservoir Mode)                   │
        └───────────────────────┬──────────────────────────────────────────┘
                                │
                                ▼
                       Threads API (Publishing)
                                │
                                ▼
                         Threads Posts (Output)


──────────────────────────────────────────────────────────────────────────────
                           VISUAL REELS SYSTEM
──────────────────────────────────────────────────────────────────────────────

                 ┌────────────────────────────────────────┐
                 │ Google Service Account Key             │
                 │ (GitHub Secret: CONTENT_REPO_PAT)      │
                 └───────────────────────┬────────────────┘
                                         │
                                         ▼
                 ┌────────────────────────────────────────┐
                 │ FMMedia-VisualOutput_Engine            │
                 │  render_video.yml Workflow             │
                 └───────────────────────┬────────────────┘
                                         │
                                         ▼
                         IG / YouTube Reels (Output)


──────────────────────────────────────────────────────────────────────────────
                           HARVEST SCANNER SYSTEM
──────────────────────────────────────────────────────────────────────────────

                 ┌────────────────────────────────────────┐
                 │ GHHarvestScanner-PAT                   │
                 │ (GitHub PAT)                           │
                 └───────────────────────┬────────────────┘
                                         │
                                         ▼
                 ┌────────────────────────────────────────┐
                 │ GHHarvestScanner Repo                  │
                 │  harvest.yml Workflow                  │
                 └───────────────────────┬────────────────┘
                                         │
                                         ▼
                         Harvested Repo Data (Output)

──────────────────────────────────────────────────────────────────────────────



---


## 6. SYSTEMS OVERVIEW (KINGDOM MAP)

### Core Pillars
- **Text Output Engine**  
  - Generates and posts Threads content  
  - Powered by GitHub Actions + Threads API  

- **Visual Output Engine**  
  - Converts GSheets content into reels  
  - Outputs IG/YouTube content  

- **Harvest Scanner**  
  - Scans public GitHub repos  
  - Used for research, inspiration, and data gathering  

- **FM Media Vault**  
  - Central content repository  
  - Source of truth for long‑form and short‑form content  

---

### Token Dependencies
- Threads Token → TextOutput Engine  
- Google SA Key → VisualOutput Engine  
- PAT → Harvest Scanner  
- IG Token (future) → IG Reels  
- YouTube OAuth (future) → Shorts Engine  

---

### Automation Flow Summary
1. **Content Source Layer**  
   - GitHub repos  
   - Google Sheets  
   - FM Media Vault  

2. **Processing Layer**  
   - TextOutput Engine  
   - VisualOutput Engine  
   - Harvest Scanner  

3. **Distribution Layer**  
   - Threads  
   - IG Reels  
   - YouTube Shorts  

4. **Mapping Layer (This Repo)**  
   - Tokens  
   - Workflows  
   - Pipelines  
   - Dependencies  
   - Architecture  

---


---

## 5. CALENDAR AUTOMATION HOOKS
These are the triggers for future Google Calendar API automation:

- Token expiry < 7 days → auto‑create event  
- PAT expiry < 14 days → auto‑create event  
- Monthly checklist not completed by 25th → auto‑create event  
- Pipeline dry‑run failure → auto‑create event  

---

## 6. META‑LEVEL NOTES
- This registry is the *single source of truth* for all life‑admin tasks.  
- All updates must be reflected here before being considered “complete”.  
- This file is the cold administrative backbone of your empire’s infrastructure.
