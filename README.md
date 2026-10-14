# Shreyas Arcade

Free browser games starring Shreyas, with player accounts and leaderboards.

- `index.html`: the arcade (30 games, accounts, leaderboards, feedback, update log)
- `horror.html`: Shreyas Horror, the 3D escape game
- `firebase-config.js`: Firebase settings for accounts and leaderboards
- `firestore.rules`: database security rules (paste into Firebase → Firestore → Rules)

Hosted with GitHub Pages. Accounts use Firebase Authentication (username + password) and scores live in Cloud Firestore.
To remove a bad score: Firebase console → Firestore → `scores/<game>/entries/<player id>` → delete.

## Reading feedback
Firebase console → Firestore Database → Data → `feedback`. Each message has the player's username, topic, message and time.
