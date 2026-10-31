# Who Wrote That? 🦃

A Kahoot-style Friendsgiving party game. Everyone secretly answers prompts on their phone, then the group guesses who wrote each answer.

- **Host screen (TV/laptop):** shows the room code + QR code, the answers, a countdown, and the leaderboard.
- **Phones:** everyone joins by scanning the QR code, then writes answers and taps their guesses.
- **Scoring:** a correct guess earns 500–1,000 points (faster is more). The author earns 150 for every person they fool.
- **No server, no accounts.** It's one static `index.html`. Phones connect peer-to-peer to the host screen using [PeerJS](https://peerjs.com/).

## Play

1. Open the deployed site on the TV/laptop → **Host on this screen**.
2. Friends scan the QR code (or open the site and enter the 4-letter code).
3. Press **Start game** once 3+ people are in. Space/Enter advances screens on the host.

Settings in the lobby: answers per player (1–3), seconds per guess, and your own custom prompts.

## Deploy

It's a static site, so any static host works:

- **Netlify:** connect this repo (no build command, publish directory `.`), or drag the folder onto https://app.netlify.com/drop
- **GitHub Pages:** Settings → Pages → deploy from `main`, root folder

It must be served over **https** for phones to join. Opening the file directly from your computer won't work.

## Tips for party night

- Keep the host tab open and don't refresh it, because refreshing ends the game.
- If a phone locks, it reconnects automatically with the same name and score.
- If someone can't connect on Wi-Fi, have them switch to cellular (or the reverse).
- With about 10 people and 2 answers each, a game is about 20 rounds (~12–15 min).

## Tech

- Vanilla HTML/CSS/JS in a single file
- [PeerJS](https://peerjs.com/) (WebRTC) for host ↔ phone messaging via the free public PeerJS broker
- [qrcodejs](https://github.com/davidshimjs/qrcodejs) for the join QR code
