# superbot ad gallery: the muse meme spot

The Gemini muse meme spot (`animations/gemini-muse-meme-superbot-6fbc38f8/`), every variant, published on its own
GitHub Pages site because the main gallery (`singularitystudiosdev/superbot-ad-gallery`) outgrew Pages: at about 2 GB its
builds fail, so new work on this spot is published here.

**Live:** https://singularitystudiosdev.github.io/superbot-ad-gallery-muse/ opens the hotel call cut
(`?variant=hotelcall`); the variant pill top right switches to any other cut, and the Ratio select reframes it at 16:9,
9:16, 4:5, 1:1 or 4:3.

## What is here

- `animations/gemini-muse-meme-superbot-6fbc38f8/`: the spot, copied whole from the main gallery's `main` (static, no
  build, no dependencies).
- `manifest.json`: the main gallery's entries for this spot (thumbs left out). The Export button at the end of the Speed
  pill reads it to find a variant's offline render, `assets/video/<entry id>.<ratio>.mp4`.
- `assets/video/`: the offline renders published here. The hotel call has all five ratios with its sound (the call and
  its score as AAC LC, 48 kHz stereo) at X's listed sizes: 9:16 1080x1920, 4:5 1440x1800, 1:1 1200x1200, 16:9 1920x1080,
  4:3 1440x1080; 34.7 s at 30 fps, H.264 High 4:2:0 at a constant 6 Mbps (X's recommended 1080p bitrate), about 26.6 MB
  each. They are the spot's own frame-exact renderer (`export.64039673.js` `window.__EXPORT.render()`, which muxes the
  soundtrack a variant registers in `window.__EXPORT_AUDIO`), re-encoded with ffmpeg. Any other variant's Export reads
  "No render" here until its renders are added. `assets/thumbs/` holds a JPEG poster per ratio (a mid-call frame) for
  the ad's thumbnail.
- The hotel call is cut for X: large captions of the call so it reads with the sound off (about 18pt on a phone), and
  Superbot's opener as superbot.gg/features#calls has it ("I'm Superbot, an AI assistant calling for Sam Rivera. This
  call is transcribed."). The call is staged (AI-generated voices; the hotel, names and number fictional) and, since
  2026-10-17, nothing on screen says so: the on-screen disclosure was taken out on request, so a post running it has to
  carry that disclosure itself. For X, upload the 9:16
  (Vertical Video Ads) or the 4:5 or 1:1 (timeline); the 16:9 and 4:3 read too small on a phone, so they stay for
  desktop and the gallery. Run it as a standalone video ad, with no website card: superbot.gg's pages list Grok among
  the supported models, which X's Unauthorized References policy can read as a claimed integration.
- `index.html`: forwards to the hotel call.

## Updating

Copy the spot folder from the main gallery's `main` over `animations/gemini-muse-meme-superbot-6fbc38f8/`, add renders under
`assets/video/` named after the variant's `manifest.json` entry id, and push `main`; Pages serves the branch root. Keep the
site well under GitHub's 1 GB Pages limit.
