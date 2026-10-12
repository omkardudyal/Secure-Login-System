# SecureGate — Secure Login System

A beginner-friendly Flask project demonstrating account registration, bcrypt password hashing, login/logout, protected sessions, validation, parameterized SQL, and CSRF protection.

## Requirements
- Python 3.10 or newer
- pip

## Run on Windows (PowerShell)

1. Open this folder in VS Code.
2. Create and activate a virtual environment:

   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

3. Install dependencies:

   ```powershell
   python -m pip install -r requirements.txt
   ```

4. Edit `.env` and replace `SECRET_KEY` with a long random secret. For example, generate one using:

   ```powershell
   python -c "import secrets; print(secrets.token_hex(32))"
   ```

   Copy the output into `.env` after `SECRET_KEY=`.

5. Start the app:

   ```powershell
   python app.py
   ```

6. Open http://127.0.0.1:5000 in your browser. Register a test account, log in, open the dashboard, and test logout.

The SQLite database `users.db` is created automatically on first start. It is intentionally excluded from Git.

## Security notes
- Never commit `.env`, real user data, or `users.db`.
- Debug mode is off by default.
- For deployment, use HTTPS, set `COOKIE_SECURE=1`, configure a strong secret, add login rate limiting, account recovery, logging/monitoring, and consider MFA.
- This educational sample does not implement two-factor authentication (2FA), rate limiting, email verification, or password reset.
- Do not use this demo as-is for a production service without a security review.

## GitHub upload

Create an empty repository on GitHub, then run these commands from this folder (replace the URL with your own repository URL):

```powershell
git init
git add .
git commit -m "Build secure login system"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/secure-login-system.git
git push -u origin main
```

If `origin` already exists, inspect it with `git remote -v`. Update it with `git remote set-url origin https://github.com/YOUR-USERNAME/secure-login-system.git` instead of adding it again.
