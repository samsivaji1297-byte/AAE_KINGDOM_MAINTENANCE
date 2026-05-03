# **THREADS API — LONG‑LIVED TOKEN REFRESH PROTOCOL**  
### *Cold. Mechanical. Repeatable. No‑thought execution.*

---

## **0. PURPOSE**
This protocol regenerates the **Threads Long‑Lived Access Token**, required for:

- Google Apps Script → Threads Poster  
- GitHub Actions → Threads Posting Engine  
- Any future automated distribution nodes  

Token lifespan: **30 days**.

---

## **1. ACCESS THE TOKEN GENERATOR**
Open the Meta Graph Explorer configured for the Threads App:

```
https://developers.facebook.com/tools/explorer/1323128692549775/
```

---

## **2. SWITCH THE GRAPH DOMAIN TO THREADS**
Inside the Explorer:

1. Locate the **GET** request field  
2. Replace:

```
graph.facebook.com → graph.threads.net
```

Example:

```
https://graph.threads.net/v1.0/me
```

---

## **3. GENERATE A SHORT‑LIVED TOKEN**
Click:

**Generate Access Token → Generate Threads Access Token**

Copy the **short‑lived token** produced.

---

## **4. INSERT SHORT TOKEN INTO THE EXCHANGE SCRIPT**
Navigate to:

**FM Media Enterprises Vault → Threads_Token.gs → `exchangeShortLivedForLongLived()`**

Locate:

```
var shortLivedToken = "YOUR_TOKEN_HERE";
```

Paste the new short‑lived token.  
Save the script.

---

## **5. RUN THE EXCHANGE FUNCTION**
Execute:

```
exchangeShortLivedForLongLived()
```

The function returns a **new long‑lived token**.  
Copy the output.

---

## **6. UPDATE ALL TOKEN STORAGE LOCATIONS**

### **A. Google Sheets**
Location:

```
Config sheet → Cell B9
```

Paste the new long‑lived token.

### **B. GitHub Repository**
Navigate:

```
Repo: FMMedia-TextOutput_Engine
Settings → Secrets → Actions
```

Update:

- `THREADS_ACCESS_TOKEN`

Save.

---

## **7. CONFIRM SYSTEM INTEGRITY**
Perform both checks:

- Manual GitHub Action run  
- Manual Apps Script post  

Verify:

- 200 OK response  
- Post appears on Threads  
- No authentication errors  

---

## **8. LOG THE REFRESH**
Update your maintenance file:

- New “Last Updated” date  
- Next refresh date (+30 days)  
- Any anomalies or notes  

---

