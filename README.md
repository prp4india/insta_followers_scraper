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
├── requirements.txt
└── .env
```

These are the ONLY files present initially.

Everything else is automatically generated.

---

# 1. Clone Repository

```bash
git clone <repo_url>
cd insta_followers_scraper
```

---

# 2. Install Python

Install Python 3.10+:

https://www.python.org/downloads/

IMPORTANT:

During installation ENABLE:

```text
Add Python to PATH
```

Verify:

```bash
python --version
```

---

# 3. Create Virtual Environment

## Windows

```bash
python -m venv venv
```

Activate:

```bash
venv\Scripts\activate
```

You should now see:

```text
(venv)
```

in terminal.

---

# 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 5. Install Chromium

Install Playwright Chromium browser:

```bash
playwright install chromium
```

This downloads Chromium automatically.

NO manual Chrome installation required.

---

# 6. Configure `.env`

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

# 7. Run Scraper

```bash
insta_followers_scraper.exe
```

OR

```bash
.\insta_followers_scraper.exe
```

---

# 8. Login To Instagram

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

# 9. Scraping Starts Automatically

Example:

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

# 10. Output Files

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

# 11. JSON Format

```json
{
    "username": "straw__hat._",
    "full_name": "🦋BALA👀"
}
```

---

# 12. Auto Generated Files

These are created automatically during execution:

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

# 13. Resume Scraper

If scraper stops/crashes:

```bash
.\insta_followers_scraper.exe
```

It automatically resumes from previous checkpoint.

---

# 14. Stop Scraper

Press:

```text
CTRL + C
```

---

# 15. Common Errors

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

# 16. Recommended Settings

```env
FETCH_COUNT=200
BATCH_SIZE=5000
REQUEST_DELAY=0.3
```

---

# 17. Estimated Speed

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