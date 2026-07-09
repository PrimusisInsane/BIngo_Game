# Bingo with a Friend

A single-page, no-install Bingo game you can play live with a friend over the internet. Uses [PeerJS](https://peerjs.com/) (WebRTC) for direct peer-to-peer connection — no backend, no database.

## Play locally

Just open `index.html` in a browser. One player clicks **Create Room** and sends the friend the 4-character code; the friend enters it under **Join a Game**.

## Play over the internet (recommended)

`file://` paths only work on your own machine, so to actually play with a friend you need this hosted somewhere with a real URL:

1. Push this folder to a GitHub repo.
2. In the repo, go to **Settings → Pages**, set the source to your main branch (root, or `/bingo-game` if this folder is nested in a larger repo).
3. GitHub will give you a URL like `https://<username>.github.io/<repo>/`. Share that link — both players open it, one hosts, one joins with the room code.

## How it works

- Standard 75-ball, 5x5 card (B-I-N-G-O) with a free center space.
- The host draws numbers; both players' cards auto-mark matches.
- First to complete a row, column, or diagonal clicks **BINGO!** to claim the win.
- **New Round** deals fresh cards without needing to reconnect.
