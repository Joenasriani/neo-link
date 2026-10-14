# NEO-LINK // CHUNKED TRANSFER

A sleek, terminal-inspired, **peer-to-peer file transfer web app** built with React, WebRTC, and PeerJS. Send files directly from one browser to another—**no cloud uploads, no third-party storage**. Just enter a 6-digit code and transfer over an encrypted WebRTC data channel.

Designed for creatives, developers, and educators who need fast, private file sharing—ideal for workshops, on-set media exchange, or quick collaboration in environments like Dubai’s fast-paced production studios.

> **Note:** A signaling server is required for the initial peer-to-peer handshake. By default this uses PeerJS’s public server (`0.peerjs.com`). Once the WebRTC connection is established, all file data travels directly between browsers without touching any server.

>> https://joenasriani.github.io/neo-link/

---

## 🔧 How It Works

1. **Sender** selects a file → gets a unique 6-digit "frequency code".
2. **Receiver** enters the same code → establishes a direct P2P link.
3. File is **chunked into 16KB packets**, streamed securely via WebRTC.
4. Receiver **automatically downloads** the reassembled file.

File data is transferred **directly peer-to-peer** between browsers via WebRTC. A signaling server is needed only for the initial connection handshake—no file data ever passes through a server.

---

## 🌐 Tech Stack

- **Frontend**: React (18) + JSX (via Babel Standalone)
- **Styling**: Tailwind CSS + custom cyberpunk/terminal aesthetic
- **P2P Networking**: [PeerJS](https://peerjs.com/) + WebRTC
- **Icons**: Phosphor Icons
- **Font**: JetBrains Mono (monospace for code-like feel)
- **Hosting**: Fully static → deploys anywhere (GitHub Pages, Netlify, etc.)

---

## ⚠️ Important Notes

- **Uses PeerJS’s public signaling server** by default (`0.peerjs.com`) — **fine for demos**, but **not reliable for production**.
- For professional or public use, **[self-host your own PeerServer](https://github.com/peers/peerjs-server)** and update the `Peer()` config.
- Requires **HTTPS** (or `localhost`) due to WebRTC security policies — works perfectly on **GitHub Pages** (which provides free HTTPS).

---

## 🚀 Deploy to GitHub Pages (in 1 minute)

1. Fork or clone this repo.
2. Push your `index.html` to the `main` branch.
3. Go to **Repo Settings > Pages** → set source to `main` branch, root folder.
4. Visit: `https://<your-username>.github.io/<repo-name>`

✅ Ready to send files securely—no build step needed.

---

## 💡 Use Cases

- Transfer large media files (video, audio, design assets) on set or in studios
- Share work samples during client workshops (e.g., UAE government or luxury brand sessions)
- File sharing without cloud intermediaries for private, direct transfers
- Teaching WebRTC concepts in creative tech courses

---

## 🔒 Security

- Transport encrypted via **WebRTC (DTLS/SRTP)**
- No persistent storage — files exist only in memory during transfer
- No authentication by design (intentional for quick sharing); add end-to-end encryption if handling sensitive data

---

## 📄 License

This project is for demonstration and educational use.  
© Joe Nasr. All rights reserved.

> **Created by (c)Joe Nasr. All rights reserved.**

---

## 🙌 Credits

- [PeerJS](https://peerjs.com/) – WebRTC simplified
- [Google STUN](stun:stun.l.google.com:19302) – NAT traversal
- [JetBrains Mono](https://www.jetbrains.com/lp/mono/) – Typeface
- Inspired by terminal interfaces and cyberpunk aesthetics

---

> **Try it live**: [Deploy your own via GitHub Pages](#-deploy-to-github-pages-in-1-minute)  
> **Contact**: [joenasr@gmail.com](mailto:joenasr@gmail.com) | [LinkedIn](https://www.linkedin.com/in/joenasrprofile)

## Implementation and privacy caveats

The single-file `index.html` application uses PeerJS, WebRTC, React via browser scripts, and 16,384-byte file chunks. The six-digit pairing code is generated with `Math.random()`; it is a connection locator, **not strong authentication or a security credential**. Do not describe the app as an authenticated secure transfer service for sensitive material. WebRTC connection establishment relies on external signaling and network conditions; successful direct connections are not guaranteed on every network.

The browser-side demonstration has not been independently penetration-tested or validated for production use.

Credit: Joe Nasr

Portfolio: https://joe-nasr-signals.vercel.app/
