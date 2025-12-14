PKI-Based 2FA Microservice

This project implements a PKI-based Two-Factor Authentication (2FA) microservice using FastAPI. It securely generates and verifies OTPs (One-Time Passwords) using a seed encrypted with public key cryptography.

Features :

Health Check: GET /health → Check service status.
Seed Decryption: POST /decrypt-seed → PKI decryption of the stored seed.
OTP Generation: GET /generate-2fa → Generates a 6-digit TOTP.
OTP Verification: POST /verify-2fa → Verifies the generated OTP.

Technology Stack :

Python 3.10+
FastAPI (REST API framework)
PyOTP (Time-based OTP generation)
Cryptography (Public Key Infrastructure for seed encryption/decryption)
Uvicorn (ASGI server for FastAPI)
Installation & Setup :

1. Clone the repository:

git clone https://github.com/dhaminikathula/PKI-Based-2FA-Microservice.git
cd PKI-Based-2FA-Microservice

2. Create a virtual environment and activate:

python -m venv .venv
.venv\Scripts\activate   

3. Install dependencies:

pip install -r requirements.txt

4. Run the server:

uvicorn app.main:app --reload

5. Open Swagger UI:
Go to http://127.0.0.1:8000/docs
 to test all endpoints.

Usage :

1. Generate OTP:

Open GET /generate-2fa in Swagger UI → Click Execute → Copy the 6-digit OTP.

2. Verify OTP:

Open POST /verify-2fa in Swagger UI → Click Try it out → Paste the OTP in JSON format:
{
  "otp": "123456"
}
Click Execute → Expected Response:
{
  "status": "success",
  "message": "OTP verified"
}

Screenshots :

Server Running: uvicorn terminal screenshot
Swagger UI: Endpoint documentation screenshot
OTP Success: OTP verification screenshot

Key Learning :
 1. Implemented a secure PKI-based 2FA system.
 2. Learned FastAPI endpoint development and TOTP integration.
 3. Worked with public/private key encryption in Python.

Submission Notes :
 1. This microservice is fully functional and tested.
 2. OTP generation and verification are working correctly.
 3. Ready for deployment or integration with other systems.