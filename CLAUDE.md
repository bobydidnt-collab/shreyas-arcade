# Shreyas Arcade

`index.html` is the source of truth: edit it directly (all games, site UI and account code live in that one file).

Static site on Vercel (auto-deploys from GitHub main; old GitHub Pages URL redirects via the NEW_HOME script in _migrate) (https://shreyas-arcade.vercel.app/) with Firebase Auth + Firestore.

- Every time an update is pushed, add an entry at the TOP of the `UPDATES` list in `index.html`
  (search for `const UPDATES`). Use a new unique `id`, the date, a short title, and plain-language bullet points
  players will understand. The Updates button shows a red dot until players open the newest entry.
- Leaderboards: `scores/<gameId>/entries/<uid>`; game ids must be lowercase letters/digits (rules enforce it).
- Feedback lands in Firestore `feedback` (owner reads it in the Firebase console). One message per account every 3 minutes, enforced by `firestore.rules`.
- If `firestore.rules` changes, the owner must paste it into Firebase console → Firestore → Rules → Publish.
- Username rules live in two places that must match: `nameProblem()` / `NAME_*` lists in `index.html` and `nameAllowed()` in `firestore.rules`.
  Login emails are `<username lowercased, underscores removed>@players.shreyas-arcade.game`, so names differing only by case/underscores collide.
