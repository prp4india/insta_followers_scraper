# Instagram Followers Scraper

High-speed Instagram followers scraper using:

- Playwright
- Chromium
- Instagram internal API
- Persistent login session
- Batch-wise JSON saving
- Auto resume after crashes

---

# Files Present In Repo

```text
insta_followers_scraper/
│
├── insta_followers_scraper.exe
├── .env
└── README.md
```

These are the ONLY files initially present.

Everything else is automatically generated during execution.

---

# 1. Install Python

Install Python 3.10+:

https://www.python.org/downloads/

IMPORTANT:

During installation ENABLE:

```text
Add Python to PATH
```

Verify installation:

```bash
python --version
```

---

# 2. Install Playwright

Open terminal / PowerShell:

```bash
pip install playwright
```

---

# 3. Install Chromium

Install Playwright Chromium browser:

```bash
playwright install chromium
```

This downloads Chromium automatically.

NO manual Chrome installation required.

---

# 4. Configure `.env`

Edit `.env`

Example:

```env
PROFILE_URL=https://www.instagram.com/cockroachjantaparty/

HEADLESS=False

FETCH_COUNT=200
BATCH_SIZE=5000

REQUEST_DELAY=0.3
RATE_LIMIT_SLEEP=60

MAX_RETRIES=5

OUTPUT_FOLDER=followers_list
```

---

# 5. Run Scraper

## Windows PowerShell

```bash
.\insta_followers_scraper.exe
```

## CMD

```bash
insta_followers_scraper.exe
```

---

# 6. Login To Instagram

Chromium browser opens automatically.

Login manually.

If Instagram asks:
- CAPTCHA
- OTP
- suspicious login verification
- challenge verification

complete it manually.

The scraper automatically detects successful login.

---

# 7. Scraping Starts Automatically

Example output:

```text
[INFO] Launching browser
[INFO] Opening Instagram

[LOGIN] Login manually if needed...

[INFO] Instagram session detected
[INFO] USER_ID -> 30019079683

[REQUEST] Request #1
[STATUS] 200
[FETCHED] Requested=200 Actual=200

[USER 1] username1 | Full Name
[USER 2] username2 | 😎 Emoji Name
```

---

# 8. Output Files

The scraper automatically creates:

```text
followers_list/
```

Inside:

```text
followers_list/
├── batch_1.json
├── batch_2.json
├── batch_3.json
```

Each batch file is continuously updated while scraping progresses.

---

# 9. JSON Format

```json
{
    "username": "straw__hat._",
    "full_name": "🦋BALA👀"
}
```

---

# 10. Auto Generated Files

These are automatically created during execution:

```text
checkpoint.txt
instagram_profile/
followers_list/
```

DO NOT DELETE them if you want:
- auto resume
- persistent login
- session persistence

---

# 11. Resume Scraper

If scraper crashes/stops:

```bash
.\insta_followers_scraper.exe
```

It automatically resumes from previous checkpoint.

---

# 12. Stop Scraper

Press:

```text
CTRL + C
```

---

# 13. Common Errors

## playwright not found

Run:

```bash
pip install playwright
```

---

## chromium executable doesn't exist

Run:

```bash
playwright install chromium
```

---

## python not recognized

Reinstall Python and ENABLE:

```text
Add Python to PATH
```

---

## Rate Limited

If you see:

```text
401
429
Please wait a few minutes...
```

wait.

The scraper automatically retries.

---

# 14. Recommended Settings

```env
FETCH_COUNT=200
BATCH_SIZE=5000
REQUEST_DELAY=0.3
```

---

# 15. Estimated Speed

Approximate:

```text
35,000 followers ≈ 5 minutes
```

10M followers may take:

```text
1–5 days
```

depending on:
- Instagram throttling
- internet speed
- account trust
- session stability