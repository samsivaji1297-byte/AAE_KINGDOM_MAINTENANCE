# AAE KINGDOM MAINTENANCE
### *Sovereign Life‑Admin Registry*  
Cold. Methodical. Repeatable. Permanent.

---

## 1. TOKEN DIRECTORY
| Token Name | Storage Location | Expiry Cycle | Systems Using It | Refresh Protocol | Last Updated | Notes |
|-----------|------------------|--------------|------------------|------------------|---------------|-------|
| **Threads Long‑Lived Token** | Google Sheets → `Config!B9` | 30 Days | Google Apps Script Threads Poster | Protocol 1 | 01/05/2026 |
| **Threads Long‑Lived Token** | GitHub Repo → `FMMedia-TextOutput_Engine` | 30 Days | GitHub Actions Threads Poster | Protocol 1 | 01/05/2026 |
| **GHHarvestScanner-PAT** | Main GitHub A/C → Repo Secrets | ~No Expiry Date | GitHub Public Repo Harvest | Protocol Unknown | 14/04/2026 | This was done to see if I could harvest public GH Repos |
| **Google Service Account Key** | GitHub Secret `GSHEETS_KEY` | Rare | Sheets → GitHub pipelines | Protocol 3 | YYYY‑MM‑DD | Need to figure out what is being done here |
| **YouTube OAuth Token** | GitHub Secret | Variable | YouTube Shorts pipeline | Protocol 4 | YYYY‑MM‑DD | Non-existent |
| **Instagram Publishing Token** (if used) | GitHub Secret | 60 days | IG Reels pipeline | Protocol 5 | YYYY‑MM‑DD | Non-existent |

---

## 2. MONTHLY MAINTENANCE CHECKLIST
| Task | Description | Location | Frequency | Status |
|------|-------------|----------|-----------|--------|
| Threads Token Refresh | Replace token in Sheets + GitHub | Meta Dev Tools | Monthly | Pending / Done |
| GitHub PAT Audit | Check expiry window | GitHub | Monthly | Pending / Done |
| Pipeline Dry‑Run | Trigger test run of all automations | GitHub Actions | Monthly | Pending / Done |
| Calendar Reminder Audit | Ensure all reminders exist | Google Calendar | Monthly | Pending / Done |
| Sheets Integrity Check | Confirm config values + ranges | Google Sheets | Monthly | Pending / Done |

---

## 3. PIPELINE MAP
| Pipeline | Inputs | Outputs | Tokens Required | Repo |
|----------|--------|---------|----------------|------|
| **Sheets → Apps Script → Threads** | Google Sheets content | Threads posts | Threads Token | `threads-poster` |
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
