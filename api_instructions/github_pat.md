# **GITHUB API — PERSONAL ACCESS TOKEN (PAT) PROTOCOL**  
### *Identity‑bound. Permission‑controlled. Required for repo‑level automation.*

---

## **0. PURPOSE**
This protocol creates and maintains the **GitHub Personal Access Token (PAT)** used for:

- GitHub Actions requiring elevated permissions  
- Forking repositories  
- Accessing private repos  
- Automated scripts interacting with GitHub’s API  

PATs are identity‑linked and must be created **inside your GitHub account**, not inside any repo.

---

## **1. NAVIGATE TO THE PAT CREATION PANEL**
Go to:

```
GitHub → Profile (top right) → Settings
```

Then:

```
Developer settings → Personal access tokens → Fine-grained tokens
```

Click:

**Generate new token**

---

## **2. NAME THE TOKEN**
Use a clear, system‑aligned name:

```
GHHarvestScanner-PAT
```

Or any name tied to the automation node it powers.

---

## **3. SET EXPIRATION**
Choose:

```
No expiration
```

(Or a long duration if you prefer rotation discipline.)

---

## **4. SELECT RESOURCE OWNER**
Set:

```
Your GitHub account (samsivaji1297-byte)
```

This ensures the token carries your identity for repo operations.

---

## **5. SELECT REPOSITORY ACCESS**
Choose:

```
All repositories
```

Or select specific repos if you want strict scoping.

---

## **6. ASSIGN REQUIRED PERMISSIONS**
Under **Repository permissions**, set:

```
Contents → Read and write
Metadata → Read-only
Administration → Read and write
```

These three permissions enable:

- Forking  
- Reading repo metadata  
- Writing content (commits, logs, JSON outputs)  

---

## **7. GENERATE THE TOKEN**
Click:

**Generate token**

GitHub will display the PAT **once**.  
Copy it immediately.

---

## **8. STORE THE TOKEN IN GITHUB SECRETS**
Go to the repo that requires the PAT:

```
Repository → Settings → Secrets and variables → Actions → New repository secret
```

Create or update:

```
GH_PAT
```

Paste the PAT.  
Save.

This secret is now available to all workflows in that repo.

---

## **9. UPDATE WORKFLOWS TO USE THE PAT**
In your workflow file (example):

```
.github/workflows/harvest.yml
```

Replace:

```
GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

with:

```
GITHUB_TOKEN: ${{ secrets.GH_PAT }}
```

This ensures the workflow uses **your identity**, not GitHub’s default restricted token.

---

## **10. VERIFY FUNCTIONALITY**
Trigger a manual workflow run.

Confirm:

- Forking works  
- Commits succeed  
- No “403 Resource not accessible by integration” errors  

If all pass, the PAT is correctly configured.

---

## **11. LOG THE CREATION / UPDATE**
In your maintenance file:

- Record the PAT creation date  
- Record the scopes used  
- Note the repos it powers  
- Add a reminder for periodic review  

---

## **END OF PROTOCOL**

---
