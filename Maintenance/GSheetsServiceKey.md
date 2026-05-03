Here is the **clean, minimal, correct outline** for the Google‑side credential that ends up inside GitHub Secrets for your Sheets integration. This is the one you used for the automation pipeline — **NOT** a PAT (GitHub PATs are separate). Google uses a **Service Account JSON key**, not a PAT.

Below is the exact workflow you want in your maintenance MD.

---

# **GOOGLE SHEETS → GITHUB SECRET WORKFLOW (SERVICE ACCOUNT KEY)**  
### *The permanent outline for regenerating the Google credential*

## **1. Create / Access the Google Cloud Project**
- Go to Google Cloud Console  
- Open the project used for automation  
  *(e.g., `video-reels-pipelinenode` or whatever you named it)*

## **2. Enable the Google Sheets API**
- Left sidebar → **APIs & Services**  
- **Enable APIs & Services**  
- Search **Google Sheets API**  
- Enable it

## **3. Create a Service Account**
- APIs & Services → **Credentials**  
- **Create Credentials → Service Account**  
- Name it something like:  
  **github-automation**

## **4. Generate a JSON Key**
- Click the service account  
- Go to **Keys**  
- **Add Key → Create new key → JSON**  
- This downloads a `.json` file  
  *(this file **is** the credential you store in GitHub)*

## **5. Copy the Service Account Email**
It looks like:

```
github-automation@<project-id>.iam.gserviceaccount.com
```
github-automation@video-reels-pipelinenode.iam.gserviceaccount.com
```


## **6. Share the Google Sheet With That Email**
- Open your Google Sheet (e.g., **FM Media Enterprises Vault**)  
- Click **Share**  
- Paste the service account email  
- Give **Editor** access  
- Save

*(This is the permission layer — without this, GitHub can authenticate but cannot read/write the sheet.)*

## **7. Add the JSON Key to GitHub Secrets**
- Go to your GitHub repo  
- Settings → **Secrets and variables** → **Actions**  
- **New repository secret**  
- Name it:

```
GOOGLE_CREDENTIALS
```

- Paste the **entire JSON file contents**  
- Save

## **8. GitHub Action Reads It**
Inside your workflow, Python accesses it via:

```
os.environ["GOOGLE_CREDENTIALS"]
```

This is the authentication payload used by the Sheets API client.

---


