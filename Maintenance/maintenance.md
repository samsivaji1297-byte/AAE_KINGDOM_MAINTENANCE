# AAE KINGDOM MAINTENANCE
### *Sovereign Life‑Admin Registry*  
Cold. Methodical. Repeatable. Permanent.

---

## 1. TOKEN DIRECTORY
| Token Name | Storage Location | Expiry Cycle | Systems Using It | Refresh Protocol | Last Updated | Notes |
|-----------|------------------|--------------|------------------|------------------|--------------|-------|
| **Threads Long‑Lived Token** | Google Sheets → `Config!B9` | 30 Days | Google Apps Script Threads Poster | Protocol 1 | 01/05/2026 | — |
| **Threads Long‑Lived Token — `THREADS_ACCESS_TOKEN`** | GitHub Repo → `FMMedia-TextOutput_Engine` | 30 Days | GitHub Actions Threads Poster | Protocol 1 | 01/05/2026 | Mirrors Sheets token; required for GH Actions |
| **Google Service Account Key — `CONTENT_REPO_PAT`** | GitHub Repo → `FMMedia-VisualOutput_Engine` | Rare | Sheets → GitHub pipelines | Protocol 2 | 12/02/2026 | Used to pull GSheets content into basic reel format |
| **GHHarvestScanner-PAT** | Main GitHub Account → PAT | No Expiry | GitHub Public Repo Harvest | Protocol Unknown | 14/04/2026 | Experimental token for harvesting public repos |
| **Instagram Publishing Token** | Google Apps Script | Not Used | IG Reels pipeline | Protocol Unknown | — | Will need re‑establishing when IG pipeline is revived |
| **YouTube OAuth Token** | GitHub Secret | Variable | YouTube Shorts pipeline | Protocol Unknown | — | Currently non‑existent |

---

## 2. GITHUB ACTIONS TRACKER
A central log of all automated workflows across the empire.  
Tracks purpose, triggers, dependencies, and operational status.

| Workflow Name | Repo | File Path | Trigger | Purpose | Tokens Required | Frequency | Last Run / Setup | Status |
|--------------|------|-----------|---------|---------|-----------------|-----------|------------------|--------|
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

## 3. API Platforms
| Token Name | Platform | Use |
|------------|----------|-----|




---

## 2. MONTHLY MAINTENANCE CHECKLIST
| Task | Description | Location | Frequency | Status |
|------|-------------|----------|-----------|--------|
| Threads Token Refresh | Replace token in Sheets + GitHub | Meta Graph Dev Tools | Monthly | Pending + Done |
| Sheets Integrity Check | Confirm config values + ranges | Google Sheets | Monthly | Pending / Done |
| GHHarvestScanner-PAT Audit | No Expiry window | Main GitHub A/C → Repo PAT | Quarterly-Bi-Annually | Done |
| Pipeline Dry‑Run | Trigger test run of all automations | GitHub Actions | Monthly | Pending / Done |
| Calendar Reminder Audit | Ensure all reminders exist | Google Calendar | Monthly | Pending / Done |


---

## 3. PIPELINE MAP
| Pipeline | Inputs | Outputs | Tokens Required | Repo |
|----------|--------|---------|----------------|------|
| **Sheets → Apps Script → Threads** | Google Sheets  | Threads posts | Threads Token | `threads-poster` |
| **Sheets → GitHub → IG/YouTube** | Sheets content | IG Reels + YouTube Shorts | PAT, SA Key | `reels-pipeline` |
| **Receiver Summon Engine** | Scripts | Manifestation outputs | None | `sovereign-engine` |
| **FM Media Distribution Engine** | FM Vault content | Multi‑platform distribution | PAT | `fm-media-engine` |

---

## 4. REFRESH PROTOCOLS

### Protocol 1 — Threads Token Refresh
1. Open Meta Developer Tools  
2. Generate new long‑lived token  
3. Replace token in Google Sheets → `Config!B9`  
4. Replace GitHub Secret → `THREADS_TOKEN`  
5. Update “Last Updated” in Token Directory  
6. Mark Monthly Checklist item as “Done”

---

### Protocol 2 — GitHub PAT Refresh
1. Go to GitHub → Developer Settings → PATs  
2. Generate new token with required scopes  
3. Replace PAT in all relevant repo secrets  
4. Update “Last Updated”  
5. Trigger pipeline dry‑run to confirm validity

---

### Protocol 3 — Google Service Account Key Refresh
1. Open Google Cloud Console  
2. Create new JSON key for the service account  
3. Replace GitHub Secret → `GSHEETS_KEY`  
4. Update “Last Updated”  
5. Run Sheets → GitHub sync test

---

### Protocol 4 — YouTube OAuth Token Refresh
1. Run OAuth flow to generate new token  
2. Replace GitHub Secret  
3. Update “Last Updated”  
4. Trigger YouTube pipeline dry‑run

---

### Protocol 5 — Instagram Publishing Token Refresh
1. Open Meta Business Suite  
2. Refresh IG token  
3. Replace GitHub Secret  
4. Update “Last Updated”  
5. Trigger IG pipeline dry‑run

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
