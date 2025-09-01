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

Nice 🔥 you want **50 real-world examples of how to use Dirsearch**. That’s a huge practical cheat sheet, so I’ll give you a **structured list** with commands + detailed explanations.

---

# 📌 Dirsearch 50 Examples with Details

General syntax:

```bash
dirsearch -u <URL> [options]
```

---

## 🎯 Basic Usage (1–5)

1. **Basic scan**

   ```bash
   dirsearch -u https://example.com/
   ```

   → Runs with the default wordlist.

2. **Custom wordlist**

   ```bash
   dirsearch -u https://example.com/ -w /usr/share/wordlists/dirb/common.txt
   ```

   → Uses `common.txt` wordlist.

3. **Multiple targets**

   ```bash
   dirsearch -l targets.txt
   ```

   → Scans all targets listed in `targets.txt`.

4. **Extensions**

   ```bash
   dirsearch -u https://example.com/ -e php,html,js
   ```

   → Appends `.php`, `.html`, `.js` to words.

5. **Recursive mode**

   ```bash
   dirsearch -u https://example.com/ -r
   ```

   → Follows found directories and scans deeper.

---

## ⚡ Recursion & Filtering (6–10)

6. Limit recursion depth

   ```bash
   dirsearch -u https://example.com/ -r -R 2
   ```

7. Exclude status codes

   ```bash
   dirsearch -u https://example.com/ --exclude-status=403,404
   ```

8. Include only certain codes

   ```bash
   dirsearch -u https://example.com/ --include-status=200,301
   ```

9. Exclude sizes

   ```bash
   dirsearch -u https://example.com/ --exclude-size=0,1234
   ```

10. Exclude words

```bash
dirsearch -u https://example.com/ --exclude-text "Forbidden,Not Found"
```

---

## 🔑 Authentication (11–15)

11. Add headers

```bash
dirsearch -u https://example.com/ -H "Authorization: Bearer <token>"
```

12. Add cookies

```bash
dirsearch -u https://example.com/ --cookie "sessionid=abcd123"
```

13. Load cookies from file

```bash
dirsearch -u https://example.com/ --cookie-file cookies.txt
```

14. Custom User-Agent

```bash
dirsearch -u https://example.com/ -a "Mozilla/5.0"
```

15. Spoof referrer

```bash
dirsearch -u https://example.com/ -H "Referer: https://google.com"
```

---

## 🚀 Performance (16–20)

16. Increase threads

```bash
dirsearch -u https://example.com/ -t 50
```

17. Limit rate

```bash
dirsearch -u https://example.com/ --max-rate 10
```

18. Timeout requests

```bash
dirsearch -u https://example.com/ --timeout=5
```

19. Retries on failure

```bash
dirsearch -u https://example.com/ --retries=3
```

20. Randomize agents

```bash
dirsearch -u https://example.com/ --random-agents
```

---

## 🖥️ Proxy & Network (21–25)

21. Use proxy

```bash
dirsearch -u https://example.com/ --proxy http://127.0.0.1:8080
```

22. SOCKS proxy

```bash
dirsearch -u https://example.com/ --proxy socks5://127.0.0.1:9050
```

23. Ignore TLS errors

```bash
dirsearch -u https://example.com/ --ignore-tls-errors
```

24. Set delay between requests

```bash
dirsearch -u https://example.com/ --delay=2
```

25. IPv6 target

```bash
dirsearch -u https://[2606:2800:220:1:248:1893:25c8:1946]/
```

---

## 📝 Output (26–30)

26. Save to file

```bash
dirsearch -u https://example.com/ -o results.txt
```

27. Save JSON

```bash
dirsearch -u https://example.com/ --json-report=report.json
```

28. Save CSV

```bash
dirsearch -u https://example.com/ --csv-report=report.csv
```

29. Save plain list of found paths

```bash
dirsearch -u https://example.com/ --plain-text-report=paths.txt
```

30. Save in HTML format

```bash
dirsearch -u https://example.com/ --html-report=report.html
```

---

## 🧪 Advanced Options (31–35)

31. Use custom HTTP method

```bash
dirsearch -u https://example.com/ -X POST
```

32. Random extensions

```bash
dirsearch -u https://example.com/ --suffix .bak,.old
```

33. Exclude responses by regex

```bash
dirsearch -u https://example.com/ --exclude-regex ".*error.*"
```

34. Scan only directories

```bash
dirsearch -u https://example.com/ --dirs-only
```

35. Scan only files

```bash
dirsearch -u https://example.com/ --files-only
```

---

## 🔍 Automation (36–40)

36. Resume scan

```bash
dirsearch -u https://example.com/ --resume-from=admin
```

37. Continue from wordlist offset

```bash
dirsearch -u https://example.com/ --resume
```

38. Multiple extensions & recursion

```bash
dirsearch -u https://example.com/ -e php,html,txt -r
```

39. Output + proxy combo

```bash
dirsearch -u https://example.com/ --proxy http://127.0.0.1:8080 -o log.txt
```

40. Multiple targets with recursion

```bash
dirsearch -l hosts.txt -r
```

---

## 🕵️ Recon Tricks (41–45)

41. Scan with big SecLists wordlist

```bash
dirsearch -u https://example.com/ -w /usr/share/seclists/Discovery/Web-Content/big.txt
```

42. Scan only common backup files

```bash
dirsearch -u https://example.com/ -w /usr/share/seclists/Discovery/Web-Content/common-backups.txt
```

43. API endpoint scan

```bash
dirsearch -u https://api.example.com/ -w /usr/share/seclists/Discovery/Web-Content/api-endpoints.txt
```

44. Find config files

```bash
dirsearch -u https://example.com/ -w /usr/share/seclists/Discovery/Web-Content/config-files.txt
```

45. Find admin panels

```bash
dirsearch -u https://example.com/ -w /usr/share/seclists/Discovery/Web-Content/admin-panels.txt
```

---

## ⚙️ Special Cases (46–50)

46. Scan without recursion (default)

```bash
dirsearch -u https://example.com/ --no-recursion
```

47. Show full URLs only

```bash
dirsearch -u https://example.com/ --full-url
```

48. Show only valid paths

```bash
dirsearch -u https://example.com/ --status=200
```

49. Verbose debugging

```bash
dirsearch -u https://example.com/ -v
```

50. Quiet mode

```bash
dirsearch -u https://example.com/ --quiet
```

---





