# SAMS — GitHub Ready

This package combines the Phase 1 and Phase 2 frontend into **one `index.html`** for easy GitHub Pages deployment.

## Files to upload to GitHub

- `index.html` — complete web app (HTML + CSS + JavaScript + Firebase imports/config placeholder)
- `firestore.rules` — security rules to publish in Firebase Console
- `.nojekyll` — keeps GitHub Pages from applying Jekyll processing

## 1. Configure Firebase in `index.html`

Open `index.html` and search for `PASTE_YOUR_API_KEY_HERE`. Replace the complete Firebase config values with the Web App config from:

**Firebase Console → Project Settings → Your Apps → Web App**

Do not paste any Firebase service-account JSON/private key into `index.html`.

## 2. Enable Firebase Authentication

**Firebase Console → Authentication → Sign-in method → Email/Password → Enable**

For this phase, create school user accounts from Firebase Console instead of allowing public self-registration.

## 3. Create Firestore

**Firebase Console → Firestore Database → Create database**

Then open **Firestore → Rules**, paste the contents of `firestore.rules`, and click **Publish**.

## 4. Create the first Administrator

1. Firebase Console → Authentication → Users → Add user.
2. Copy that user's UID.
3. Firestore → create collection `users`.
4. Create a document whose Document ID is the same UID.
5. Add:

```text
uid          string   <same Authentication UID>
email        string   <administrator email>
displayName  string   <administrator name>
office       string   <school/admin office>
role         string   Administrator
active       boolean  true
```

## 5. Upload to GitHub

Create a repository and upload the three files in this package to the **repository root**.

Then:

**Repository → Settings → Pages → Deploy from a branch → main → /(root) → Save**

Your website will normally be:

```text
https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/
```

## 6. Authorize the GitHub Pages domain in Firebase

**Firebase Console → Authentication → Settings → Authorized domains**

Add:

```text
YOUR-USERNAME.github.io
```

## Roles included

- Employee
- Supply Officer
- Property Custodian
- HR/Admin
- School Head
- Administrator

## Current modules

- Dashboard
- Supply Request / approval / issuance / RIS printing
- Equipment borrowing / return with PCMS Asset ID linkage
- DTR monitoring
- Leave monitoring
- Users & Roles
- Audit Trail
- School Settings

## Architecture

**PCMS = master property/equipment database**

**SAMS = request, approval, issuance, borrowing/return, DTR, leave and administrative workflow**

The next recommended phase is supply stock/item master, stock cards and balances, PCMS asset lookup, QR scanning, reports and server-side audit functions.
