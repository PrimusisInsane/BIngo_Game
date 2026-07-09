# Bingo with a Friend

A single-page, no-install Bingo game you can play live with a friend over the internet. Both players connect to a public MQTT-over-WebSocket relay ([broker.emqx.io](https://www.emqx.com/en/mqtt/public-mqtt5-broker)) — no backend, no database, and no account needed. This is a plain outbound connection (like loading any HTTPS page), so unlike direct WebRTC it isn't blocked by strict NATs or firewalls.

## Play locally

Just open `index.html` in a browser. One player clicks **Create Room** and sends the friend the 4-character code; the friend enters it under **Join a Game**.

## Play over the internet (recommended)

`file://` paths only work on your own machine, so to actually play with a friend you need this hosted somewhere with a real URL:

1. Push this folder to a GitHub repo.
2. In the repo, go to **Settings → Pages**, set the source to your main branch (root, or `/bingo-game` if this folder is nested in a larger repo).
3. GitHub will give you a URL like `https://<username>.github.io/<repo>/`. Share that link — both players open it, one hosts, one joins with the room code.

## How it works

- 5x5 card with the numbers 1-25 shuffled across it (no free space).
- The host draws numbers; both players' cards auto-mark matches.
- First to complete a row, column, or diagonal clicks **BINGO!** to claim the win.
- **New Round** deals fresh cards without needing to reconnect.
