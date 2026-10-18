# Nasher CLI

**Nasher v1: the command-line tool that emailed a job seeker's CV to a list of company HR addresses over Gmail.**

> This is the first version of **[Nasher](https://github.com/Abdullah-Albariqi/nasher)**. It proved people would pay for the service, and it was then rebuilt as a self-service web app.

## The problem

Sending a CV to hundreds of companies by hand takes days and is easy to get wrong: the wrong attachment, a typo in an address, or Gmail flagging you for sending too fast.

## The solution

An interactive Python script I ran for each early client:

- **Guided prompts.** Asks for the applicant's details, the Gmail address and app password (hidden input), the CV file, and how many companies to send to.
- **Email list loading.** Reads company emails from CSV or Excel, detects the email column, and validates addresses.
- **Connection test first.** Checks the SMTP login before sending anything.
- **Individual emails.** One personal message per company with the PDF CV attached, plus a live progress bar.
- **Long-run safety.** Keeps Windows awake during long runs and logs every send and failure.

## How it works

```
Terminal prompts (name · job title · Gmail + app password · CV · list size)
        │
        ▼
Load emails from CSV / Excel  →  validate addresses
        │
        ▼
Test SMTP connection  →  send one email per company (CV attached)
        │
        ▼
Progress bar + log file
```

## What came next

v1 meant I had to run every client by hand. **[Nasher v2](https://github.com/Abdullah-Albariqi/nasher)** replaced the terminal with a web app that has activation codes, client self-onboarding, a live status page and an admin panel, connected end-to-end to the Salla/n8n payment flow.

## Tech stack

Python · smtplib (Gmail SMTP) · openpyxl · csv

## Status

🗄️ **Superseded by [Nasher v2](https://github.com/Abdullah-Albariqi/nasher)**

---

Source code is private and available on request. More about me: [Abdullah-Albariqi](https://github.com/Abdullah-Albariqi)
