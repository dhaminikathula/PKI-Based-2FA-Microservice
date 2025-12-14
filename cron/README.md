Student: Dhamini Sri Raja Jahnavi Kathula
GitHub: https://github.com/dhaminikathula/PKI-Based-2FA-Microservice

Project Overview

A PKI-based Two-Factor Authentication microservice built with FastAPI.
The project securely encrypts a TOTP seed using RSA 4096-bit encryption, decrypts it on the server, and validates OTPs. The microservice is Dockerized and includes a cron job to log OTPs every minute.

Key Functionalities:

GET /health → Service status

POST /decrypt-seed → Decrypt encrypted seed

GET /generate-2fa → Generate 6-digit OTP

POST /verify-2fa → Verify OTP

How It Works

Request Encrypted Seed – scripts/request_seed.py

Decrypt Seed – POST /decrypt-seed with encrypted seed

Generate OTP – GET /generate-2fa

Verify OTP – POST /verify-2fa with JSON { "otp": "<6-digit-code>" }

Cron Job – Logs OTP every minute in /cron/last_code.txt