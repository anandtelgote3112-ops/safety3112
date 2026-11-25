# SAFETY360 Cloud Starter

This is the next cloud-enabled SAFETY360 build for the existing repository.

## Included
- English responsive web app / installable PWA foundation
- Firebase Authentication (email/password)
- Firestore cloud records
- Multiple projects
- Sole Super Admin email: anandtelgote3112@gmail.com
- User registration with Pending status; Super Admin assigns role and project access
- Work Permits, Observations, Incidents, TBT, Inspections, Projects, Users & Roles, CSV report export
- Firestore security rules for project-scoped access

## Important current limits
- Firebase Storage attachment upload is not wired in this starter yet; the attachment selector is a placeholder.
- Email/password sign-in must be enabled in Firebase Authentication.
- Paste the existing Firebase Web App config into `firebase-config.js`.
- This bundle does not publish to GitHub automatically. Upload/replace these files in the existing repository.

## Setup
1. In Firebase Console, open project `safety-360-48243`.
2. Authentication > Sign-in method > enable Email/Password.
3. Build > Firestore Database > create database if not already created.
4. In Firestore > Rules, paste `firestore.rules` and Publish.
5. Open Project settings > Your apps > Web app config. Copy `apiKey`, `messagingSenderId`, and `appId` into `firebase-config.js`. The other values are prefilled for the known project; confirm the storage bucket in Firebase.
6. Upload `index.html`, `firebase-config.js`, `manifest.json`, `sw.js`, `icon.svg`, and `firestore.rules` to the repository root.
7. In GitHub repository Settings > Pages, select Deploy from branch > `main` > `/ (root)`.

## First login / Super Admin bootstrap
1. Open the deployed site.
2. Create/sign in with `anandtelgote3112@gmail.com`.
3. The app recognizes this exact email as the sole Super Admin and initializes the user profile.
4. Create projects in Projects.
5. Ask each staff member to create an account. In Users & Roles, assign their role, project IDs and Active status.

## Security notes
- Never publish Firebase service-account JSON or private keys.
- The Firebase web config is not a private key; Firestore Rules are the security boundary.
- Test with a second non-admin account before entering live site records.
- For stronger production security, add server-side Cloud Functions for privileged workflows and Firebase App Check.
