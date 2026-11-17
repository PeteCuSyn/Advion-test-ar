Meet Your New Employee – AR card prototype
==========================================

Files
  index.html          the WebAR page (MindAR + three.js, loaded from jsDelivr)
  inspector.glb       the cockroach inspector, optimised (435k -> 51k triangles, 19.4 MB -> 1.7 MB)
  target.png          the image the camera recognises (also what goes on the card)
  card.png            hi-res card artwork
  print-card-a4.pdf   two cards at 85 x 55 mm – print at 100%

Put it online (camera needs HTTPS)
  Easiest: go to https://app.netlify.com/drop and drag this whole folder onto the page.
           You get an https link in a few seconds – open it on your phone.
  Vercel:  in this folder run  npx vercel  (or npx vercel --prod)

First run on a phone
  The page "learns" the card in the browser (~10 s) and caches it.
  To skip that for everyone: tap "Download targets.mind" (top-left, once AR is running),
  drop targets.mind into this folder and redeploy. The page uses it automatically.

Swap things out
  New model:   replace inspector.glb (keep it under ~3 MB; it is auto-scaled and centred).
  New card:    replace target.png, delete targets.mind if present, redeploy.
               Busy, high-contrast artwork tracks best; avoid big flat areas and repeating patterns.
  Tap-to-open: write the deployed URL to an NTAG213/215 sticker (e.g. NFC Tools app) and stick it
               behind the card; add a QR code of the same URL as a fallback.
