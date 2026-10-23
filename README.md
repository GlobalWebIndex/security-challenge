# Desk Ledger — Security challenge

The desk ledger service crashed during a health-check storm and our password manager is in maintenance. Security has asked you to find the credentials and log in the admin app to assess the running container, understand weaknesses, and deliver remediated source code.

You are given a **pre-built ledger service binary** (no source code). Your job is to run it, explore the application, and abuse **weaknesses** that unlock the next phase of the interview. The second phase includes the patching of the source. You must find a way to download the source.

## Run the service

Pick the binary that matches your OS/CPU under `bins/` (or use the macOS binary in this folder if provided).

```bash
chmod +x ./bins/ledger-linux-arm64   # example
./bins/ledger-linux-arm64
```

The server listens on **http://127.0.0.1:9181** by default.

It writes logs under `./logs/` and data under `./data/` in the directory where you start the process (create them or let the app create them).

## Guide

1. **Recon**: Run the service and explore it. Check the logs and find out how many endpoints exist.
2. **Find weaknesses**: Look for vulnerabilities such as input validation issues, XSS, CSRF, race conditions, and so on. This list is examples, not exhaustive.
3. **Goal**: Exploit what you find to log in as an authenticated user and get access to the application’s source code.
4. **Fix it**: Patch the vulnerabilities in that source code.
5. **Present**: Present your solution to the team in whatever format you prefer (slides, a live demo, a document). Walk us through how you found and exploited each issue and how you fixed it, then be ready for technical questions. Plan for about 30 minutes.
6. **What to send us**: the patched source code and any notes you took. We suggest spending about 4 hours.

## Rules

- Use only the binary, the running process, and normal tools (browser, `curl`, log files, hash crackers, reverse engineeing tools etc.).
- Document (or try to understand) how you reproduced each finding.
- The use of AI tools is allowed