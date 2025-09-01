# Dirsearch
Dirsearch is a popular web path scanner on Kali Linux. Here’s the step-by-step guide:
---

### 🔹 Step 1: Update Kali

```bash
sudo apt update && sudo apt upgrade -y
```

---

### Step 2: Install from GitHub

```bash
git clone https://github.com/maurosoria/dirsearch.git ~/tools/dirsearch
cd ~/tools/dirsearch
```

### Step 3: Run

```bash
python3 dirsearch.py -h
```
```bash
pip install -r requirements.txt --break-system-packages 
```
### Step 4 (Optional): Make it global

```bash
sudo ln -s ~/tools/dirsearch/dirsearch.py /usr/bin/dirsearch
```

---

# 🔥 Dirsearch Usage – 20 Examples with Details

👉 General syntax:

```bash
dirsearch -u <URL> [options]
```

---

## **1. Basic Scan**

```bash
dirsearch -u https://example.com/
```

➡ Scans `example.com` using the **default wordlist** that ships with Dirsearch.

---

## **2. Scan with Custom Wordlist**

```bash
dirsearch -u https://example.com/ -w /usr/share/wordlists/dirb/common.txt
```

➡ Uses a **custom wordlist** instead of the default. Great if you want more targeted fuzzing.

---

## **3. Scan Multiple Targets**

```bash
dirsearch -l targets.txt
```

➡ `targets.txt` contains a list of URLs. Dirsearch will scan them one by one.

---

## **4. Scan with Multiple Extensions**

```bash
dirsearch -u https://example.com/ -e php,asp,aspx,html
```

➡ Tries these file extensions (e.g., `index.php`, `login.asp`).

---

## **5. Recursive Scan**

```bash
dirsearch -u https://example.com/ -r
```

➡ Recursively scans discovered directories (e.g., finds `/admin/` → scans inside it too).

---

## **6. Limit Recursion Depth**

```bash
dirsearch -u https://example.com/ -r -R 2
```

➡ Recursively scans, but only **2 levels deep**.

---

## **7. Exclude Status Codes**

```bash
dirsearch -u https://example.com/ --exclude-status=403,404,500
```

➡ Hides unwanted responses like **Forbidden, Not Found, Server Errors**.

---

## **8. Include Only Certain Status Codes**

```bash
dirsearch -u https://example.com/ --include-status=200,301,302
```

➡ Shows only **valid and redirecting endpoints**.

---

## **9. Filter by Size**

```bash
dirsearch -u https://example.com/ --exclude-size=0,1234
```

➡ Excludes responses with a specific **size in bytes** (useful to avoid junk results).

---

## **10. Custom HTTP Method**

```bash
dirsearch -u https://example.com/ -X POST
```

➡ Uses **POST requests** instead of GET. Useful when testing APIs.

---

## **11. Set Request Headers**

```bash
dirsearch -u https://example.com/ -H "Authorization: Bearer <token>"
```

➡ Adds custom headers (e.g., JWT, cookies). Helpful for authenticated endpoints.

---

## **12. Add Cookies**

```bash
dirsearch -u https://example.com/ --cookie "sessionid=abcd1234"
```

➡ Sends cookies for authenticated sessions.

---

## **13. Change User-Agent**

```bash
dirsearch -u https://example.com/ -a "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
```

➡ Spoofs your **browser fingerprint**. Some sites filter requests by User-Agent.

---

## **14. Ignore TLS/SSL Errors**

```bash
dirsearch -u https://example.com/ --ignore-tls-errors
```

➡ Useful when scanning HTTPS sites with misconfigured SSL certs.

---

## **15. Use Proxy**

```bash
dirsearch -u https://example.com/ --proxy=http://127.0.0.1:8080
```

➡ Sends traffic through a proxy (e.g., **Burp Suite**).

---

## **16. Scan at Higher Speed (Threads)**

```bash
dirsearch -u https://example.com/ -t 50
```

➡ Runs with **50 threads** for faster scanning. Default is 10.

---

## **17. Timeout Settings**

```bash
dirsearch -u https://example.com/ --timeout=5
```

➡ Aborts requests that take more than **5 seconds**.

---

## **18. Save Results to File**

```bash
dirsearch -u https://example.com/ -o results.txt
```

➡ Saves output into a **text file**.

---

## **19. Save as JSON**

```bash
dirsearch -u https://example.com/ --json-report=report.json
```

➡ Saves findings in **JSON format** for automation.

---

## **20. Resume Scan**

```bash
dirsearch -u https://example.com/ --resume-from=admin
```

➡ If scan stops, resumes from the wordlist entry `admin`.

---

# ⚡ Pro Tips

* Use **big wordlists** from [SecLists](https://github.com/danielmiessler/SecLists) for better results:

  ```bash
  sudo apt install seclists -y
  ```
* Combine with **Burp Suite** to analyze requests.
* Always run with **recursive mode** for deep discovery.

---




