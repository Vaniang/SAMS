# SAMS GitHub Ready - Configured v3

This version adds **Employee Self-Service Profile Editing** to the dashboard.

## New feature

Every authenticated employee can click:

**Dashboard -> My Profile -> Edit My Profile**

Editable fields:
- Display Name
- Preferred Name / How the employee wants to be addressed
- Office / Unit
- Position / Designation
- Contact Number (optional)

Locked security/account fields:
- Email
- Firebase UID
- SAMS Role
- Active/Inactive status

Those locked fields cannot be changed through the Employee dashboard.

## Why this is safe

The included Firestore Rules allow a user to update his/her own `users/{UID}` document only if these security fields do not change:
- `uid`
- `email`
- `role`
- `active`

The Administrator still controls roles and account status.

## Deploy

Replace the files in the GitHub repository root with:
- index.html
- firestore.rules
- README.md
- .nojekyll

Then publish the included `firestore.rules` in:

Firebase Console -> Firestore Database -> Rules -> Publish

After GitHub Pages redeploys, use Ctrl+F5 to refresh the site.

## Firebase project already configured

Project ID:
`sams-e149a`
