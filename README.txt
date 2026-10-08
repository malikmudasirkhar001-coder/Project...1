PWA SETUP — INSTRUCTIONS
========================

FILES:
1. manifest.json
2. sw.js
3. offline.html
4. icon-192.png
5. icon-512.png

INDEX.HTML MEIN 2 CHANGES:

CHANGE 1 — <head> tag ke andar ye lines add karein:
---------------------------------------------------
<link rel="manifest" href="/manifest.json" />
<meta name="theme-color" content="#2196F3" />
<link rel="apple-touch-icon" href="/icon-192.png" />
---------------------------------------------------

CHANGE 2 — </body> tag se pehle ye script add karein:
---------------------------------------------------
<script>
  if ('serviceWorker' in navigator) {
    window.addEventListener('load', () => {
      navigator.serviceWorker.register('/sw.js')
        .then((reg) => console.log('✅ SW registered:', reg.scope))
        .catch((err) => console.log('❌ SW failed:', err));
    });
  }
</script>
---------------------------------------------------

TEST KARNE KA TAREEQA:
1. Website kholein
2. Saare pages kholay (cache hone ke liye)
3. Internet band karein
4. Page refresh karein
5. Agar chalta hai to sab sahi hai ✅
