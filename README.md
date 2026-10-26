# Shaik CamWatch (test build)

Turns spare phones into live security cameras and shows them all on one monitor phone. First step towards the Shaik Security camera app.

## Try it
1. Turn on GitHub Pages: Settings → Pages → Deploy from a branch → `main`, `/ (root)`.
2. On the **monitor phone**, open the link and tap **View cameras**. Note the 6-digit site code (it stays the same on that phone).
3. On each **camera phone**, open the link, tap **Add as a camera**, enter the site code and a name (e.g. "Front gate"). Or tap **Invite camera** on the monitor to send a ready-made link.
4. Every camera appears as a tile on the monitor. Cameras keep retrying, so they reconnect by themselves if the monitor reloads or drops.

Start with both phones on the same Wi-Fi. On different networks (e.g. mobile data) some connections need a relay (TURN) server, which comes in the next step.

## How it works
- Each camera phone streams straight to the monitor with WebRTC (peer-to-peer, nothing stored).
- PeerJS's free public server only helps the two phones find each other. Video is video-only, no audio.
- It's a web app (PWA): "Add to home screen" installs it like a normal app. No Android Studio needed.

## Next steps
- [ ] Own Cloudflare Worker for connecting phones (replace PeerJS cloud) + TURN relay for mobile data
- [ ] Login (Cloudflare Access) so only approved users can watch
- [ ] Real cameras: on-site Pi/mini PC running go2rtc + Cloudflare Tunnel
- [ ] Motion alerts and saved snapshots/clips (Cloudflare R2)
- [ ] POPIA: consent, access control, retention rules
