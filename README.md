# Dirsearch
Dirsearch is a popular web path scanner on Kali Linux. Here’s the step-by-step guide:
---

### 🔹 Step 1: Update Kali

```bash
sudo apt update && sudo apt upgrade -y
```

---

### 🔹 Step 2: Install Git (if not installed)

```bash
sudo apt install git -y
```

---

### 🔹 Step 3: Clone Dirsearch

```bash
git clone https://github.com/maurosoria/dirsearch.git
```

This will create a folder called `dirsearch`.

---

### 🔹 Step 4: Go to Dirsearch directory

```bash
cd dirsearch
```

---

### 🔹 Step 5: Run Dirsearch

You can run it directly with Python:

```bash
python3 dirsearch.py -u https://target.com/ -e php,html,js,txt
```

---

### 🔹 Step 6 (Optional): Create a Global Command

So you can run `dirsearch` from anywhere:

```bash
sudo ln -s $(pwd)/dirsearch.py /usr/bin/dirsearch
```

Now just run:

```bash
dirsearch -u https://target.com/
```

---

⚡ **Example usage:**

```bash
dirsearch -u https://example.com/ -w /usr/share/wordlists/dirb/common.txt -e php,html,js,txt
```

---

