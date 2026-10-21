# Desk Ledger — Security challenge (step 1)

The desk ledger service crashed during a health-check storm and our password manager is in maintenance. Security has asked you to find the credentials and log in the admin app to assess the running container, understand weaknesses, and deliver remediated source code.

You are given a **pre-built ledger service binary** (no source code). Your job is to run it, explore the application, and abuse **weaknesses** that unlock the next phase of the interview. This is an offensive first challenge. 

## Run the service

Pick the binary that matches your OS/CPU under `bins/` (or use the macOS binary in this folder if provided).

```bash
chmod +x ./bins/ledger-linux-arm64   # example
./bins/ledger-linux-arm64
```

The server listens on **http://127.0.0.1:9181** by default.

It writes logs under `./logs/` and data under `./data/` in the directory where you start the process (create them or let the app create them).

## Guide

1. **Recon** — Check the logs, find out how many endpoints exist.
2. **Inspect for vulnerabilities** — DDoS, input validation, XSS, CSRF, race conditions etc.
3. **Goals** — Reach to the source code as an authenticated user by exploiting the discovered vulnerabilities.
4. **Deliverables** - Patch the source and deliver it fixed. Be ready to present.

## Rules

- Use only the binary, the running process, and normal tools (browser, `curl`, log files, hash crackers, reverse engineeing tools etc.).
- Document (or try to understand) how you reproduced each finding.
- The use of AI tools is allowed