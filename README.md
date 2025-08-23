# Role Login — Mobile App + Flask API (Starter Project)

This zip contains:
- `server/` — Flask JWT API (login and "me" endpoints)
- `mobile/` — Expo React Native app (login screen + dashboard showing id, name, role)

## Quick Start (Android/iOS phone + same Wi‑Fi)

1) **Start the API**
```bash
cd server
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
# optional: set secrets
# PowerShell:  $env:APP_SECRET_KEY="secret"; $env:JWT_SECRET="jwt-secret"
# bash/zsh:    export APP_SECRET_KEY=secret JWT_SECRET=jwt-secret
python app.py
```
Find your PC LAN IP (e.g., `192.168.1.50`). The API lives at `http://<LAN-IP>:5000`.

2) **Run the mobile app**
```bash
cd ../mobile
npm install
# Edit src/api.ts -> set BASE_URL to http://<LAN-IP>:5000
npm run start
```
Open **Expo Go** on your phone and scan the QR. Login using:
- `admin / admin123` (role: admin)
- `manager / manager123` (role: manager)
- `user / user123` (role: user)

## Notes
- For production, enable HTTPS and lock CORS to your domain/app.
- Consider refresh tokens and a revoke list for stricter security.
- You can add role-protected screens by calling `/api/me_jwt` and checking `role`.
