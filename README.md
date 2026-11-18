# ProCV – ATS Resume + Visiting Card Maker (PWA)

Run: `python3 -m http.server 8080` → open http://localhost:8080 (works offline after first load, installable on Android).

## Built
- CV builder: experience, education, projects, skills, certs, photo (auto-cropped), 3 templates (2 ATS-safe, 1 two-column), colour/font, A4 print → "Save as PDF" (real selectable text = ATS-readable)
- Import old CV (PDF/TXT/paste) → AI fills + improves wording (no invented facts)
- ATS score (local rules) + job-description keyword match; AI: summary, bullets, tailor-to-job, career coach (Gemini or Claude, user's API key)
- Visiting card: 3 styles, 10-up A4 print sheet

## Play Store path
1. Host on HTTPS (Netlify/Cloudflare/Firebase Hosting).
2. Wrap: `npx @bubblewrap/cli init --manifest https://YOURDOMAIN/manifest.webmanifest` → `bubblewrap build` → AAB (TWA). Or Capacitor.
3. Play Console ($25 one-time), privacy policy, data-safety form.
4. Money: free = 1 template + watermark; paid (₹99–299/mo or one-time) = all templates, AI, no watermark. Use Play Billing (via TWA Digital Goods API / RevenueCat).
5. BEFORE selling: move AI calls to your own backend proxy (Cloud Function) holding the API key + per-user quota. Never ship your key inside the app.

## Next phases
Canva-style graphic editor (Fabric.js/Konva), more templates, cover letter, DOCX export, cloud sync/login (Firebase), PNG export of cards.
