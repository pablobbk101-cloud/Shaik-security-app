# Shaik CamWatch (test build)

Turns one phone into a live security camera you can watch from another phone. First step towards the Shaik Security camera app.

## Try it
1. Turn on GitHub Pages: Settings → Pages → Deploy from a branch → `main`, `/ (root)`.
2. On the **camera phone**, open the Pages link and tap **Be the camera**. Allow camera access. Note the 6-digit code.
3. On the **viewer phone**, open the same link, tap **Watch a camera** and enter the code (or use **Share link** on the camera phone).

Start with both phones on the same Wi-Fi. On different networks (e.g. mobile data) some connections need a relay (TURN) server, which comes in the next step.

## How it works
- The camera phone streams straight to the viewer with WebRTC (peer-to-peer, nothing stored).
- PeerJS's free public server only helps the two phones find each other. Video is video-only, no audio.
- It's a web app (PWA): "Add to home screen" installs it like a normal app. No Android Studio needed.

## Next steps
- [ ] Own Cloudflare Worker for connecting phones (replace PeerJS cloud) + TURN relay for mobile data
- [ ] Login (Cloudflare Access) so only approved users can watch
- [ ] Real cameras: on-site Pi/mini PC running go2rtc + Cloudflare Tunnel
- [ ] Motion alerts and saved snapshots/clips (Cloudflare R2)
- [ ] POPIA: consent, access control, retention rules
